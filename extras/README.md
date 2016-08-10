### confd

`confd` directory contains haproxy template files for the [confd](https://github.com/kelseyhightower/confd) -- lightweight configuration management tool
You need to copy content of `confd` directory into /etcd/confd and run confd service:
```bash
$ confd -prefix=/service/$PATRONI_SCOPE -backend etcd -node $PATRONI_ETCD_HOST -interval=10
```
It will periodically update haproxy.cfg with the actual list of Patroni nodes from `etcd` and "reload" haproxy when it is necessary.


### startup-scripts

`startup-scripts` directory contains startup scripts for various OSes and management tools for Patroni.