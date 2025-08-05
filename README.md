# DevOps
First task: run and connect the both application using docker network


## You have to create docker network first:

docker network create application

docker network ls 

## Backend 
 docker build -t api-image -f Dockerfile.api .

 docker run -it --name api-container -p 8080:8080 --network application api-image:latest   

## Frontend
docker build -t frontend-image -f Dockerfile.frontend .

docker run -it --name frontend-container -p 8081:8081 --network application frontend-image:latest

* Note: the value of backendURL in frontend settings.yaml should be point to backend container name which is `api-container`