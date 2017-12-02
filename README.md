# swarm_fabric

change docker daemon setting on all node


Simple add this line into your Docker config file `/etc/default/docker`.

```sh
DOCKER_OPTS="$DOCKER_OPTS -H tcp://0.0.0.0:2375 -H unix:///var/run/docker.sock --api-cors-header='*' --default-ulimit=nofile=8192:16384 --default-ulimit=nproc=8192:16384"
```

Then restart the docker daemon with:

```sh
$ sudo service docker restart
```
