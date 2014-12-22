#Various snipplets

Push ssh key to remote host
```shell
jsmith@local-host$ ssh-copy-id -i ~/.ssh/id_rsa.pub remote-host
```
---
---

Recursive chmod Tricks
Recursively chmod only directories

```shell
find . -type d -exec chmod 755 {} \;
```

Similarly, recursively set the execute bit on every directory

```shell
chmod -R a+X *
```

The +X flag sets the execute bit on directories only

Recursively chmod only files

```shell
find . -type f -exec chmod 644 {} \;
```

Recursively chmod only PHP files (with extension .php)

```shell
find . -type f -name '*.php' -exec chmod 644 {} \;
```

---
---