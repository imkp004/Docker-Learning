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