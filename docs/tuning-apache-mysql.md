#Tuning Apache and MySQL for Best Performance in a Shared Virtual Hosting Environment


Web hosting has changed dramatically in the last few years. The majority of accounts are now running PHP scripts and MySQL, whereas in the past most accounts were only serving static HTML files. This presents challenges in security as well as performance tuning.

It is impossible to predict whether a certain configuration will work properly for a given server, unless the hardware, software, accounts, network and traffic are identical to a previously configured server… therefore it is impossible to give a configuration which will cover all applications.

#Firewall Unnecessary Traffic from Affecting the Server

Before you begin performance tuning, please consider using a stateful packet inspection (SPI) firewall & login failure daemon (LFD) for your server: ConfigServer Firewall is an excellent free firewall & LFD. This will help prevent brute force probes, port flooding, DDOS, etc. If you have 600 virtual hosts running on a server, it is very likely that the server is experiencing constant malicious exploits, especially if you are also running email servers on the same IP addresses.

If your host does not support ConfigServer (e.g. Amazon AWS and some VPS may not play well with CSF), you may use Fail2Ban.

#Tune Apache the Sane Way (Requires Basic Math Skills)

If you wish to tune your Apache MPM settings, you should consider following this method:
https://telvps.com/clients/knowledgebase/25/HOW-TO-Optimize-Apache-for-Low-Memory-Usage.html
(the formula works well as a basic guide… but does not take into account PHP memory requirements… see Ovidiu’s comment below).

#MySQL Tuning Is More Difficult: Trial and Error

To test your MySQL server performance, you may try:

mysqltuner: https://github.com/rackerhacker/MySQLTuner-perl (or http://mysqltuner.pl for the script only)
MySQL Tuning Primer: https://launchpad.net/mysql-tuning-primer
phpMyAdmin 3.5+: Status Monitor and Advisor are excellent tools, but require proper phpMyAdmin setup
These scripts will analyze MySQL performance and make suggestions regarding your my.cnf configuration. mysqltuner is now deprecated, but it still widely used and is very simple. Tuning Primer is the most up-to-date, and provides more complete recommendations.

If you are running MySQL 5 or later, the configuration statements can be in the following form (example from one of my servers):

```mysql
[mysqld]
datadir=/var/lib/mysql
socket=/var/lib/mysql/mysql.sock
user=mysql

symbolic-links=0
innodb_file_per_table = 1
thread_concurrency = 8
query_cache_size = 64M
query_cache_limit = 4M
thread_cache_size = 8
myisam_sort_buffer_size = 64M
read_rnd_buffer_size = 8M
read_buffer_size = 2M
sort_buffer_size = 2M
table_cache = 1600
table_definition_cache = 1600
max_allowed_packet = 4M
key_buffer = 1G
interactive_timeout = 2
wait_timeout = 5
long_query_time = 1
log_slow_queries = ON
open_files_limit = 3200
innodb_buffer_pool_size = 26M
join_buffer_size = 4M
tmp_table_size = 72M
max_heap_table_size = 72M
max_connections = 80

[mysqld_safe]
log-error=/var/log/mysqld.log
pid-file=/var/run/mysqld/mysqld.pid
```


This is for example only! table_cache should be set a little higher than the total number of tables (sum of MYISAM,INNODB,MEMORY etc.), as reported by mysqltuner. If you anticipate adding more virtual hosts, or clients adding more databases or tables, you will need to raise table_cache value.

Follow the recommendations from the Apache tuning, and then follow the recommendations of the tuning scripts. The apache tuning will give you the number of maxclients, and from this you will know the appropriate beginning value for [mysqld] max_connections. Begin with max_connections set slightly higher than Apache’s maxclients. If you are running database caching via APC, you may lower max_connections, because APC will serve the busiest queries directly from cache.

#Take Time to Get a Realistic Assessment of MySQL Performance

If you have a PHP opcode and database caching strategy (such as APC) implemented on your web server and for your PHP script packages, you will be able to lower maxconnections, based on the information you receive from mysqltuner after 24-48 hours of steady traffic. For example, I have a server with Apache set to 256 maxclients, but the MySQL maxconnections set to 200, because many web requests do not require direct interaction with the MySQL server.

Take a look at “Highest usage of available connections”, and lower maxconnections accordingly. It is safe to lower maxconnections to a number slightly above the reported highest usage. Doing so will allow you to set higher values for the individual cache settings which affect the thread cache size, because the total thread buffer memory size is multiplied by maxconnections. Feedback is available in the reports for “Total buffers” and “Highest usage of available connections”.

After you have the proper settings for maxclients and maxconnections, restart httpd and mysqld. Wait 1 hour, and run mysqltuner to see if there are any recommended changes. Mysqltuner will show you the maximum memory which will be used by mysql. You should adjust config variables to take up no more than 60% of total RAM. Wait 24-48 hours and run mysqltuner again.

#Example mysqltuner results:

```mysql
------- Performance Metrics -------------------------------------------------
[--] Up for: 13d 2h 34m 16s (1M q [1.561 qps], 67K conn, TX: 81B, RX: 449M)
[--] Reads / Writes: 91% / 9%
[--] Total buffers: 298.0M global + 6.4M per thread (151 max threads)
[OK] Maximum possible memory usage: 1.2G (61% of installed RAM)
[OK] Slow queries: 0% (0/1M)
[OK] Highest usage of available connections: 6% (10/151)
[OK] Key buffer size / total MyISAM indexes: 256.0M/9.7M
[OK] Key buffer hit rate: 99.6% (3M cached / 13K reads)
[OK] Query cache efficiency: 75.2% (1M cached / 1M selects)
[!!] Query cache prunes per day: 1360
[OK] Sorts requiring temporary tables: 0% (4 temp sorts / 13K sorts)
[!!] Temporary tables created on disk: 38% (6K on disk / 16K total)
[OK] Thread cache hit rate: 99% (13 created / 67K connections)
[OK] Table cache hit rate: 51% (115 open / 223 opened)
[OK] Open file limit used: 20% (212/1K)
[OK] Table locks acquired immediately: 99% (408K immediate / 409K locks)
-------- Recommendations -----------------------------------------------------
General recommendations:
Add skip-innodb to MySQL configuration to disable InnoDB
Run OPTIMIZE TABLE to defragment tables for better performance
Enable the slow query log to troubleshoot bad queries
When making adjustments, make tmp_table_size/max_heap_table_size equal
Reduce your SELECT DISTINCT queries without LIMIT clauses
Variables to adjust:
query_cache_size (> 16M)
tmp_table_size (> 16M)
max_heap_table_size (> 16M)
```

I suggest you NOT enable the slow query log unless the Slow Queries result is very high. Slow Queries result % will be somewhat high if MySQL has run for less than 24 hours.

#Example MySQL Tuning Primer results:

```mysql
SLOW QUERIES
The slow query log is NOT enabled.
Current long_query_time = 10.000000 sec.
You have 0 out of 1768137 that take longer than 10.000000 sec. to complete
Your long_query_time seems to be fine

BINARY UPDATE LOG
The binary update log is NOT enabled.
You will not be able to do point in time recovery
See http://dev.mysql.com/doc/refman/5.1/en/point-in-time-recovery.html

WORKER THREADS
Current thread_cache_size = 8
Current threads_cached = 7
Current threads_per_sec = 0
Historic threads_per_sec = 0
Your thread_cache_size is fine

MAX CONNECTIONS
Current max_connections = 151
Current threads_connected = 1
Historic max_used_connections = 10
The number of used connections is 6% of the configured maximum.
You are using less than 10% of your configured max_connections.
Lowering max_connections could help to avoid an over-allocation of memory
See "MEMORY USAGE" section to make sure you are not over-allocating

INNODB STATUS
Current InnoDB index space = 0 bytes
Current InnoDB data space = 0 bytes
Current InnoDB buffer pool free = 96 %
Current innodb_buffer_pool_size = 8 M
Depending on how much space your innodb indexes take up it may be safe
to increase this value to up to 2 / 3 of total system memory

MEMORY USAGE
Max Memory Ever Allocated : 345 M
Configured Max Per-thread Buffers : 962 M
Configured Max Global Buffers : 282 M
Configured Max Memory Limit : 1.21 G
Physical Memory : 2.00 G
Max memory limit seem to be within acceptable norms

KEY BUFFER
Current MyISAM index space = 9 M
Current key_buffer_size = 256 M
Key cache miss rate is 1 : 247
Key buffer free ratio = 80 %
Your key_buffer_size seems to be fine

QUERY CACHE
Query cache is enabled
Current query_cache_size = 16 M
Current query_cache_used = 12 M
Current query_cache_limit = 1 M
Current Query cache Memory fill ratio = 77.74 %
Current query_cache_min_res_unit = 4 K
MySQL won't cache query results that are larger than query_cache_limit in size

SORT OPERATIONS
Current sort_buffer_size = 1 M
Current read_rnd_buffer_size = 4 M
Sort buffer seems to be fine

JOINS
Current join_buffer_size = 132.00 K
You have had 0 queries where a join could not use an index properly
Your joins seem to be using indexes properly

OPEN FILES LIMIT
Current open_files_limit = 1024 files
The open_files_limit should typically be set to at least 2x-3x
that of table_cache if you have heavy MyISAM usage.
Your open_files_limit value seems to be fine

TABLE CACHE
Current table_open_cache = 256 tables
Current table_definition_cache = 256 tables
You have a total of 97 tables
You have 115 open tables.
The table_cache value seems to be fine

TEMP TABLES
Current max_heap_table_size = 16 M
Current tmp_table_size = 16 M
Of 10325 temp tables, 37% were created on disk
Perhaps you should increase your tmp_table_size and/or max_heap_table_size
to reduce the number of disk-based temporary tables
Note! BLOB and TEXT columns are not allow in memory tables.
If you are using these columns raising these values might not impact your
ratio of on disk temp tables.

TABLE SCANS
Current read_buffer_size = 1 M
Current table scan ratio = 199 : 1
read_buffer_size seems to be fine

TABLE LOCKING
Current Lock Wait ratio = 1 : 2405
You may benefit from selective use of InnoDB.
If you have long running SELECT's against MyISAM tables and perform
frequent updates consider setting 'low_priority_updates=1'
If you have a high concurrency of inserts on Dynamic row-length tables
consider setting 'concurrent_insert=2'
```