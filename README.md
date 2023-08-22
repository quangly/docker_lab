# Docker + Node.js

Dockerize a Node.js app. 


#Build
docker build -t deltadreams/demoapp:1.0 .

#Run
docker run -p 5001:8080 5257ff46e55c

#Stop and remove all containers at once
docker ps -aq | xargs docker stop | xargs docker rm