# Docker + Node.js

Dockerize a Node.js app. 


#Build
```
docker build -t deltadreams/demoapp:1.0 .
```

#create volume to be shared across containers
```
docker volume create shared-stuff
```

```
docker run --mount source=shared-stuff,target=/stuff
```


#Run
```
docker run -p 5001:8080 deltadreams/demoapp:1.0 
```

or
```
docker-compose up
```

```
docker-compose down
```


Debug using Docker Desktop or exec command
```
docker exec -it [DOCKER CONTAINER ID]] bash
```

#Stop and remove all containers at once
```
docker ps -aq | xargs docker stop | xargs docker rm
```

To Inspect network
```
docker network ls
docker network inspect <network name> 
docker network inspect docker_lab_backend1
```

To delete all images
```
docker rmi -f $(docker images -aq)
```

To view docker logs
```
docker logs [CONTAINER_ID]
```

To delete all containers including its volumes use,
```
docker rm -vf $(docker ps -aq)
```
Delete EVERYTHING
```
docker system prune -a --volumes
```