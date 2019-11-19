# Docker Instance per User
This template has the following properties
1. multiple docker instances (on-demand)
2. docker `behind` traefik load balancer
3. docker-managers takes care of credentials 
4. ctf flag is disabled

## Docker Configuration
```
{
  "6f0ea069-da21-402d-bd3a-39115b0b9cf1": {
   "name": "alpine-ttyd-multi-instance",
   "type": "6f0ea069-da21-402d-bd3a-39115b0b9cf1",
   "dynFqdn": true,
   "fqdn": "",
   "expireTime": 10,
   "dockerType": "docker-compose",
   "singleton": false,
   "ipAccess": "nat",
   "port": 7681,
   "protocol": "http",
   "link": "tcp",
   "container": "hackinglab/alpine-ttyd",
   "containeryml": "6f0ea069-da21-402d-bd3a-39115b0b9cf1.yml",
   "vars": "",
   "network": "alpine-ttyd",
   "egonetwork": true,
   "challengeType": "noGN",
   "gnCreation": "docker-manager",
   "gnDeploy": "env",
   "goldNugget": "",
   "withCredentials": true,
   "dynUser": false,
   "dynPassword": false,
   "staticUsername": "hacker",
   "staticPassword": "compass"
 }
}
```

## Video 
[Video](../video/docker-manager-multi-instance-docker.mp4)


## Presentation in Video
[PDF](docker-manager-per-user.pdf)