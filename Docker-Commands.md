docker pull <image-name>

-To get the latest version of the existing image from your local docker desktop (if exists) or from the docker hub (like github cloning)

docker pull <imahe-name>:<version>

-To get the specific version of the existing image from your local docker desktop (if exists) or from the docker hub.


docker images

-To get the all the images there is in your docker desktop locally.


docker run <image-name>

-To run the image and now it will automatically create a container
that starts running and gives output 


docker run -it <image-name>

-This command will helps us get the intericative output of the continer. 
The image will run and it will create the container and then it will also
help us access the container terminal.


docker ps

-Tp see all the running containers in your docker desktop 
-while <docker ps -a> to see all the existing containers in the docker desktop


docker stop <container-name> or <container-id>

-To stop the running container

docker start <container-name> or <container-id>

-To start the container running



docker rmi <image-name>

-To remove the image from the docker desktop 

docker rm <container-name>

-To remove the container from the docker desktop



docker run -d <image-name>

-To run the image container in the detach mode beasically run it in backgroung. by default it runs in foreground


docker run -d --name <tag-name> <image-name>

-This will give your container a name which you chose. By default it
give a random name to the container




docker run -p 8080:3306 <image-name>

To run the image and also maping the host machine port to the container
port. Bacisally binding (permanant attaching) host port to container port.




docker logs <conatiner-id> or <container-name>

To check all the logs of the container. It is mainly used for 
troubleshooting cause


docker exec -it <container-id> /bin/bash

or

docker exec -it <container-id> /bin/sh

This command is used to get the terminal of the container and run
commands in it. Not every container will hvae bash then we can use sh (shell)
To check the envirement variables or to check the dependiencies installed.
And when exit from the shell it won't stop the container, It will keep on running. 




Docker Network Commands

docker network ls

To list all the network exists in the docker system

docker network create <network-name>

To create a new network in your docker system with a name

docker network rm <network-name>

To remove the network from your docker system




Docker Compose commands

docker compose -f <compose.yaml-file> up -d

This command is to run the compose file in the project that contains
the docker image information and that will run and it will create the 
containers automatically in a detach mode-(running in background)


docker compose -f <compose.yaml-file> down

To stop the containers and to delete the containers and network
which it created and run.

