# Docker Templates
## Intro
Hacking-Lab 2.0 is a `CTF` and `Cyber Academy` education platform.  In HL 2.0 students can spin up their own and private docker service. A proprietary component called `docker-manager` takes care of spinning up the docker services. These docker instances (containers) can be started on-demand (multiple instances) or as singletons. The `docker manager` has many features and this repo will introduce the different  `use-cases`. This is important for HL 2.0 challenge developers. 

## Docker Manager 
There are many combinations how the `docker-manager` can spin up a service. In a CTF (capture-the-flag) environment, services may have a private flag or unique login credentials. May the docker shall be shared among other contestants or used as a single service per user. All these can be configured using the HL 2.0 `docker-manager`. 

Configuration Examples:
* docker with static or ctf flag
* docker with static or dynamci usernames and passwords
* docker instances running per user or once as a singleton
* docker instances inheriting flags from the docker or create and provide one to the docker
* docker instances via traefik load balancing or directly linked to a routeable ip address
* docker instances sharing a docker network or isolated

## Load Balancing
The so-called `idocker` instances in `HL 2.0` are started, stopped and maintanced using `traefik` labels. If you experience an url with `idocker` in the `url`, this docker has been deployed with `traefik`


## Direct Access
Some docker instances in `HL 2.0` can be run directly with a public routeable ip address. We use the ESX `macvlan` feature for this. However, if you see a `docker` with `rdocker` in the `url`, this docker has been started `without traefik` and is directly connected to a public ip address. This is required for all challenges with a direct tcp/udp port. 




