# Docker Instance per User
This template has the following properties
1. multiple docker instances (on-demand)
2. docker `behind` traefik load balancer
3. docker-managers takes care of credentials 
4. ctf flag is disabled


## Docker Service Configuration (used by `docker-manager`)
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
[Docker Manager Multi-Instances](https://raw.githubusercontent.com/Hacking-Lab/docker-templates/master/video/docker-manager-multi-instance-docker.mp4)


## PDF
[Docker-Manager Multi-Instances](docker-manager-per-user.pdf)


## API Response from Docker Manager after  `startup`
```
{
	"id": "2ce091f9-863f-4dde-9f79-ab5e39782840",
	"schema": "",
	"ipaddress": "",
	"protocol": "",
	"port": "",
	"userId": "Ivan",
	"expireTime": 1574168965463,
	"fqdn": "2ce091f9-863f-4dde-9f79-ab5e39782840.idocker.hacking-lab.com",
	"ipAccess": "nat",
	"singleton": false,
	"goldnugget": null,
	"userattributes": {
		"credentials": {
			"username": "hacker",
			"password": "compass"
		}
	}
}
``` 

## API Status Request
Status Request

```
curl -s --header "Authorization: Bearer <cut>" -k https://api.idocker.hacking-lab.com/api/v1/containers/2ce091f9-863f-4dde-9f79-ab5e39782840
```

Status Response 
```
{
	"id": "2ce091f9-863f-4dde-9f79-ab5e39782840",
	"schema": "",
	"ipaddress": "",
	"protocol": "",
	"port": "",
	"userId": "Ivan",
	"expireTime": 1574169083921,
	"fqdn": "2ce091f9-863f-4dde-9f79-ab5e39782840.idocker.hacking-lab.com",
	"ipAccess": "nat",
	"singleton": false,
	"userattributes": {
		"credentials": {
			"username": "hacker",
			"password": "compass"
		}
	},
	"goldnugget": null
}
```



