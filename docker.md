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
