# Docker commands

Collection of docker commands.


*Docker Hub --> hub of docker images*


`docker pull <imageName>`

## Pull & run image

`docker run <imageName>`

## Create a new container from an image

`docker run <imageName>:<version>`

**detached mode**

`docker run -d <imageName>`

## Port binding -p<hostPort>:<containerPort>

`docker run -p6000:6379 <imageName>`

## Specify container name

`docker run -p6001:6379 --name <myName> <imageName>`


## Start stoped container
*(once the container is created)*

```
docker start <containerId>
docker stop <containerId>
```
## List downloaded images
`docker images`


## List running containers
`docker ps`

## History

`docker ps -a `
`docker ps -a | grep <name>`

## Terminal of container
```
docker exec -it <containerId or contairName> /bin/bash
docker exec -it <containerId or contairName> /bin/sh
```
## See environment variables
```
env
exit
```
## Logs
```
docker logs <containerId>
docker logs <conainerName> | tail
docker logs -f
```
## Docker network

```
docker network ls

docker network create <networkName>

docker run -p 27017:27017 -d \
	-e <envVariable>=<value> \
	--name <containerName> \
	--network <networkName> \
	<imageName>

docker logs <containerId>
```
## Docker compose
```
docker-compose -f <fileName.yml> up
docker-compoer -f <fileName. yml> down
```
## Dockerfile
```
docker build -t <appName:version> <Dockerfile location>
docker images
dokcer run
```
## Stop/remove all containers
```
# only active
docker stop $(docker ps -q)
docker rm $(docker ps -q)
# all history
docker stop $(docker ps -aq) 
docker rm $(docker ps -aq)

```

## Delete container or image
```
docker stop <containerId>
docker rm <containerId>
docker rmi <imadeId>
```

## Rename image
```
docker tag <oldName> <newName>
```
## Docker Registry (private repo)

Amazon ECR

+ registry options

+ build & tag an image

+ docker login

+ docker push


## Push image
```
docker push <tagName>
```
## Docker volumes for data persistence


+ Host volumes

+ Anonymous volumes

+ Named volumes **(preferred way)**

## Docker and Mongo

```
docker pull mongo

docker run -p 27017:27017 -d --mount type=bind,source=$PWD/data/bin,destination=/data/bin mongo

# Ensure that there is an existing /data/bin folder in your $PWD
```

## Docker for splash

```
docker pull scrapinghub/splash

docker run -p 8050:8050 -d scrapinghub/splash
```

