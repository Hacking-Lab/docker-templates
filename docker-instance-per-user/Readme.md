# Multi-Instance Docker Services
## Description
Docker services may not be shared among a group of students. May you want to start the same application per user? This is what we call the "multi-instance" docker service. See an example below. 


## Service Configuration
1. multi-instance docker service (singleton set to `false`)
2. docker `behind` traefik load balancer (ipAccess set to `nat`)
3. docker-managers takes care of credentials (withCredentials set to `true`) 
4. ctf flag is disabled (challengeType set to `noGN`)
5. docker-manager changes credentials in the docker service (withCredentials set to `true`)

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



## API Request "start container"
```
curl -X PUT 'https://api.docker-manager/api/v1/containers'
{
  "containerName": "6f0ea069-da21-402d-bd3a-39115b0b9cf2",
  "clientId": "<cut>",
  "userId": "e1@hacking-lab.com",
  "file": ""
}
```

## API Response "start container"
```
{
	"id": "2ce091f9-863f-4dde-9f79-ab5e39782840",
	"schema": "",
	"ipaddress": "",
	"protocol": "",
	"port": "",
	"userId": "e1@hacking-lab.com",
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

## API Request (status container)
This is a `curl` request asking for the status of a running docker contaner

```
curl -s --header "Authorization: Bearer <cut>" -k https://api.idocker.hacking-lab.com/api/v1/containers/2ce091f9-863f-4dde-9f79-ab5e39782840
```

## API Response (status container)
This is the json response if the docker container is up and running

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



## Download
* [Docker Manager Multi-Instances](https://raw.githubusercontent.com/Hacking-Lab/docker-templates/master/video/docker-manager-multi-instance-docker.mp4)
* [Docker-Manager Multi-Instances](docker-manager-per-user.pdf)