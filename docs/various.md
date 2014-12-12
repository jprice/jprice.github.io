#Various snipplets

* Push ssh key to remote host
```shell
jsmith@local-host$ ssh-copy-id -i ~/.ssh/id_rsa.pub remote-host
```

* install setup tools curl 
```
https://bitbucket.org/pypa/setuptools/raw/bootstrap/ez_setup.py | python -
```
* install pip
```
curl https://raw.github.com/pypa/pip/master/contrib/get-pip.py | python -
```

test