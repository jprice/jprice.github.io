xargs examples

For example following example will print 1 2 3 4 using xargs (echo command is default)

```
$ echo 1 2 3 4 | xargs echo
```

OR


```
$ echo 1 2 3 4 | xargs
```
You can force xargs to use at most max-args arguments per command line. For example following will use first two argument per command:

```
$ echo 1 2 3 4 | xargs -n 2
```

Find all .bak files in or below the current directory and delete them.

```
$ find . -name "*.bak" -type f -print | xargs /bin/rm -f
```

{} as the argument list marker

{} is the default argument list marker. You need to use {} this with various command which take more than two arguments at a time. For example mv command need to know the file name. The following will find all .bak files in or below the current directory and move them to ~/.old.files directory:

```
$ find . -name "*.bak" -print0 | xargs -0 -I {} mv {} ~/old.files
```
You can rename {} to something else. In the following example {} is renamed as file. This is more readable as compare to previous example:

```
$ find . -name "*.bak" -print0 | xargs -0 -I file mv file ~/old.files
```

Where,

* If there are blank spaces or characters (including newlines) many commands will not work. This option take cares of file names with blank space.
* I Replace occurrences of replace-str in the initial-arguments with names read from standard input. Also, unquoted blanks do not terminate input items; instead the separator is the newline character.
Dealing file names with blank spaces and newline

The following will work incorrectly if there are any filenames containing newlines or spaces (it will find out all .mp3 file located in current directory and play them using mplayer):

```
$ find . -iname "*.mp3" -print | xargs mplayer
```

To get rid of this problem use -0 option:

```
$ find . -iname "*.mp3" -print0 | xargs -0 -I mp3file mplayer mp3file
```

To find out all *.c file located in 100s of subdirectories and move them to another directory called ~/old.src, use:

```
$ find /path/to/dir -iname "*.c" -print0 | xargs -0 -I file mv file ~/old.src
```

Avoiding errors and resource hungry problems with xargs and find combo

To copy all media files to another location called /bakup/iscsi, you can use cp as follows:

```
$ cp -r -v -p /share/media/mp3/ /backup/iscsi/mp3
```

However, cp command may fail if an error occurs such as if the number of files is too large for the cp command to handle. xargs in combination with find can handle such operation nicely. xargs is more resource efficient and will not halt with an error:

```
$ find /share/media/mp3/ -type f -name "*.mp3" -print0 | xargs -0 -r -I file cp -v -p file --target-directory=/bakup/iscsi/mp3
```
Please note that all of the above commands are tested with GNU/xargs version. BSD and UNIX xargs command may not have options such as -r. Please refer to your local xargs man page for further info:
man xargs



---

<pre>$ xargs
Hi,
Welcome to TGS.</pre>

After you type something, press ctrl+d, which will echo the string back to you on stdout as shown below.
<pre>$ xargs
Hi,
Welcome to TGS.**Hi, Welcome to TGS.**</pre>

### 2. Specify Delimiter Using -d option

Delimiters can be applied so that each character in the input is taken literally using -d option in xargs.

In the previous example, even though the input contained a \n (newline) after &#8216;Hi,&#8217; but the echoed output did not contain the newline &#8216;\n&#8217; . So, the output in the previous example was combined into a single line.

In the following example, when you use the -d\n, it will preserve newline delimiter in the output, and display the output exactly as it was typed.
<pre>$ xargs -d\n
Hi,
Welcome to TGS.</pre>

After you type the above, press ctrl+d, which will echo the string back to you on stdout as shown below. But, this time it will preserve the newline.
<pre>$ xargs -d\n
Hi,
Welcome to TGS.**Hi,** 
**Welcome to TGS.**</pre>

### 3. Limit Output Per Line Using -n Option

By default as explained earlier, xargs displays whatever comes to its stdin as shown below.
<pre>
$ echo a b c d e f| xargs
a b c d e f
</pre>

But, the output of the xargs command can be split into multiple lines using -n option.

In the following example, we used -n 3, which will display only 3 items per line in the xargs output.
<pre>$ echo a b c d e f| xargs **-n 3**
a b c
d e f</pre>

In the same way, you can also split the output with 2 items per line as shown below using -n 2.
<pre>
$ echo a b c d e f| xargs -n 2
a b
c d
e f
</pre>

### 4. Prompt User Before Execution using -p option

Using option -p, you can confirm the execution of the xargs command from the user.

Considering the previous example, if we want to confirm each execution of the /bin/echo command by the user, use the -p option along with -n option as shown below.
<pre>$ echo a b c d e f| xargs **-p** -n 3
**/bin/echo a b c ?**...y
**/bin/echo d e f ?**...a b c
y
d e f</pre>

In the following output, I said &#8220;n&#8221; to all the echo output. So, xargs did not execute anything.
<pre>
$ echo a b c d e f| xargs -p -n 3
/bin/echo a b c ?...n
/bin/echo d e f ?...n
/bin/echo ?...n
</pre>

Note: This is helpful when you are combining xargs with commands that are disruptive like rm. In those cases, you may want to see what xargs does.

### 5. Avoid Default /bin/echo for Blank Input Using -r Option

When there is a blank input (i.e no input was given to xargs command), it will execute a /bin/echo command which will display a new line as shown below.
<pre>$ xargs -p
</pre>

Press ctrl-d after typing &#8220;xargs -p&#8221;, which will indicate that it executed a /bin/echo as shown below.
<pre>$ xargs -p
                      **/bin/echo ?...y**

$</pre>

### 6. Print the Command Along with Output Using -t Option

In the following example, type &#8220;abcd&#8221; as the input for the xargs -t command.
<pre>
$ xargs -t
abcd
</pre>

Press ctrl-d to complete the above xargs -t command, which will display the command that xargs really executes before displaying the output. In this case, the command that xargs executes is &#8220;/bin/echo abcd&#8221;, which is displayed here.
<pre>
$ xargs -t
abcd
/bin/echo abcd
abcd
</pre>

### 7. Combine Xargs with Find Command

It is one of the most important usage of xargs command. When you need to find certain type of files and perform certain actions on them (most popular being the delete action).

The xargs command is very effective when we combine with other commands.

In the following example, we took the output of the [find command](http://www.thegeekstuff.com/2009/03/15-practical-linux-find-command-examples/), and passed it as input to the xargs command. But, instead of executing the default /bin/echo command, we are instructing xargs command to execute the rm -rm command on the input.

So, in this example, the output of the find command is all the files with *.c extension, which is given as input to the xargs command, which in-turn execute &#8220;rm -rf&#8221; command on all the *.c files.
<pre>$ ls
one.c  one.h  two.c  two.h

$ **find . -name "*.c" | xargs rm -rf**

$ ls
one.h  two.h
</pre>

### 8. Delete Files that has White-space in the Filename

So we see that despite of running the rm command on the .c files in this directory, the file &#8216;The Geek Stuff.c&#8217; was not deleted. This is because this file contains white space characters in its name.

As shown in the following example, it deleted all the files with the *.c extension except one. i.e the file that has white space in the filename (i.e &#8220;The Geek Stuff.c&#8221;) was not deleted by the rm command.
<pre>$ touch "The Geek Stuff.c"

$ ls
one.c  one.h  two.c  two.h The Geek Stuff.c

$ find . -name "*.c" | xargs rm -rf

$ ls
one.h  two.h  **The Geek Stuff.c**</pre>

In this situation, use the -print0 option with find command and -0 option with xargs command to delete files including those that has space in the filenames as shown below.
<pre>$ ls
one.c  one.h  two.c  two.h The Geek Stuff.c

$ find . -name "*.c" **-print0** | xargs **-0** rm -rf

$ ls
one.h  two.h</pre>

### 9. Display System Limits on xargs using &#8211;show-limits option

See the example below:
The following example displays all the limits set by the OS that will have an impact on the way how xargs command works.
<pre>$ xargs **--show-limits**
Your environment variables take up 1203 bytes
POSIX upper limit on argument length (this system): 2093901
POSIX smallest allowable upper limit on argument length (all systems): 4096
Maximum length of command we could actually use: 2092698
Size of command buffer we are actually using: 131072

Execution of xargs will continue now, and it will try to read its input and 
run commands; if this is not what you wanted to happen, please type the 
end-of-file keystroke.

Warning: /bin/echo will be run at least once.  If you do not want that to happen, 
then press the interrupt keystroke</pre>

### 10. Combine Xargs with Grep command

The xargs command can be combined with [grep command](http://www.thegeekstuff.com/2009/03/15-practical-unix-grep-command-examples/) to filter particular files from the search results of the find command.

In the following example, find command provided all the .c files as input to xargs.

The xargs command executes the grep command to find all the files (among the files provided by find command) that contained a string &#8216;stdlib.h&#8217;.
<pre>