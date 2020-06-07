# igou-docker

## Why I have a swarm host in addition to a Kubernetes cluster in my lab

* My Kubernetes cluster is deleted/rebuilt very frequently
** This makes running applications that require storage require a lot of overhead. I have tasks in my backlog to design a solution to manage that. But I would rather make that something I can work on in parralel to other things, since it is quite ambitious.

* I can use Traefik in swarm to proxy applications that aren't ran a container.
** For example my NAS is a swarm agent with OpenMediaVault (And other services I really don't want to containerize)  exposed to the docker network, which allow me to reverse proxy to them.

* Raspberry Pi Zeros cannot run k3s-agent


## What am I running

Currently:

* Traefik 2.0
* MinIO
* Mariadb
* Influxdb
* OpenMediaVault + Pihole are proxied from my NAS

## Future plans

It is possible that down the road I'll look into something besides swarm (Possibly Hashicorp Nomad) but until then, this setup allows me to work on many things in parralel instead of blocking a ton of stuff behind tackling a big storage endeavor. But ideally, one day I can just add these nodes to my k8s cluster and support frequently redeploying and keeping my storage intact.
