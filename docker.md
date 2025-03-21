### list all docker containers
```
docker ps -a
```
### list docker images
```
docker images
```
### stop a docker container
```
docker stop <container-id>
```
### remove a docker container
```
docker rm <container-id>
```
### remove a docker image
```
docker rmi <image-id>
```
or
```
docker rmi <image-name>
```
### force delete an image
```
docker rmi -f <image-id>
```
### delete all docker images
```
docker rmi $(docker images -q)
```
### if images are still in use by containers, first remove all containers
```
docker rm -f $(docker ps -aq)
docker rmi -f $(docker images -q)
```

### accessing a container's shell

```
docker exec -it <container-name-or-id> <shell-executable>
docker exec -it nginx sh
docker exec -it nginx bash
docker exec -it 7d6cd739b951 /bin/bash
```

### access docker container logs

```
docker logs <conatiner-name>
```

follow logs

```
docker logs -f <container-name>
```

follow last 10 lines

```
docker logs -f --tails 10 <container-name>
```
