# Docker Commands

docker pull `image-name`

- To get the latest version of the existing image from your local docker desktop (if exists) or from the docker hub (like github cloning)

docker pull `image-name`:`version`

-To get the specific version of the existing image from your local docker desktop (if exists) or from the docker hub.

docker images

-To get the all the images there is in your docker desktop locally.

docker run `image-name`

- To run the image and now it will automatically create a container
that starts running and gives output

docker run -it `image-name`

-This command will helps us get the intericative output of the continer.
The image will run and it will create the container and then it will also
help us access the container terminal.

docker ps

-Tp see all the running containers in your docker desktop
-while <docker ps -a> to see all the existing containers in the docker desktop

docker stop `container-name` or `container-id`

- To stop the running container

docker start `container-name` or `container-id`

- To start the container running

docker rmi `image-name`

- To remove the image from the docker desktop

docker rm `container-name`

- To remove the container from the docker desktop

docker run -d `image-name`

- To run the image container in the detach mode basically run it in background. by default it runs in foreground

docker run -d --name `tag-name` `image-name`

- This will give your container a name which you chose. By default it
give a random name to the container

docker run -p 8080:3306 `image-name`

To run the image and also mapping the host machine port to the container
port. Basically binding (permanent attaching) host port to container port.

docker logs `container-id` or `container-name`

To check all the logs of the container. It is mainly used for
troubleshooting cause

docker exec -it `container-id` /bin/bash

or

docker exec -it `container-id` /bin/sh

This command is used to get the terminal of the container and run
commands in it. Not every container will have bash then we can use sh (shell)
To check the environment variables or to check the dependencies installed.
And when exit from the shell it won't stop the container, It will keep on running.

## Docker Network Commands

docker network ls

To list all the network exists in the docker system

docker network create `network-name`

To create a new network in your docker system with a name

docker network rm `network-name`

To remove the network from your docker system

Docker Compose commands

docker compose -f <compose.yaml-file> up -d

This command is to run the compose file in the project that contains
the docker image information and that will run and it will create the
containers automatically in a detach mode-(running in background)

docker compose -f <compose.yaml-file> down

To stop the containers and to delete the containers and network
which it created and run.

To dockerizing the app we need the dockerfile and this command

docker build -t `app-name`:`version-tag` .

to create the image of the docker container with the tag and app name

Now login into the docker account by

docker login

and then push your image into the docker hub by

docker push `account-username`/`image-name`

## Docker Volume

docker run -it -v `host-path`:`container-path` `image-name`

this command will run the image as a container in an interactive (terminal)
mode but this time it will also create a volume (storage drive) and attach to container and host machine

the path is to provide where to store data which directory. In host machine path and also in container path

docker volume ls

To list all the volumes exists in your docker desktop

docker volume create `volume-name`

To create a volume with a name of your choice
Now by default if you create a volume it will store it in your
machine at /var/lib/docker/volumes
which can be used to attach to a container

docker volume rm `volume-name`

To remove volume from your docker

there is another way to bind the volumes that was created by

docker run -v `volume-name`:`container-path` `image-name`

docker run -v `container-path` `image-name`

To create anonymous named volume in your docker
Docker will manage the volume and it will give name to it

docker volume prune

To remove any unused volume
