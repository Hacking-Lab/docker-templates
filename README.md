# Docker Templates
## Intro
This repo is hosting some docker templates for the `Hacking-La 2.0` platform.

## Why? 
Hacking-Lab 2.0 is a `CTF` and `Cyber Academy` education platform.  In HL 2.0 students can spin up their own and private docker service. But there are many options available, how to setup a docker. For example

* docker with static ctf flag
* docker with dynamic ctf flag
* docker with static usernames and passwords
* docker with dynamic usernames and passwords
* docker instances running per user
* docker instances running as singleton

Thus, this repo shall help challenge and docker service devlopers creating nice and cool `Challenge Dockers` for the `HL 2.0` platform. 

## Docker Manager
Hacking-Lab 2.0 is based on a proprietary docker-manager. This tool gives us the flexibility to run and start docker services in all sorts of combinations. 

## Traefik
Some docker instances in `HL 2.0` are started, stopped and maintanced using `traefik` labels. If you experience an url with `idocker` in the `url`, this docker has been deployed with `traefik`

## Direct Access
Some docker instances in `HL 2.0` can be run directly with a public routable ip address. We use the ESX `macvlan` feature for this. However, if you see a `docker` with `rdocker` in the `url`, this docker has been started `without traefik` and is directly connected to a public ip address. This is required for all challenges with a direct tcp/udp port. 


