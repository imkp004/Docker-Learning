Docker Learning

Docker helps devlopers by containerizing the code and the dependiencies with the specific version 
used to make the application run on a comupter with any operating system (mac, linux, windows) and 
also helps with running on many computers just like it was running the first time in one computer.

It also helps with versions of the dependiencies, if the application runs with specific python version
and to update the version from old to new than to test the apllication by running on different version
docker container helps.

Docker containeers are isolated from the computer the person uses meaning that in the computer the 
python version 2 is installed but it won't matter because containeers are isolated it will only run app
as dependiencies in the containeer if the containeer has python3 then the app will run as python3 app.

It also helps creating muntiple copies of the smae project.

Docker has feature which is volumes. It can be attached to the containeer and now that containeer can 
communicate with the host machine usually it is a server or the computer a person uses. It can also be
used to communicate within different containeers by storing and sharing date in the volume. It is like
a storage disk that is attached to the container. If container is stopped then the data goes away by 
with volume attached if container stoped or deleted the data stays in the volume and that volume can
be attached to different container to get the same data back up and running. To access the data it needs
to be attached and mounted to the container


For example you downloaded the latest version of python and also python version 2. Then you can run two different application or same application with two different versions of python by creating container of each image of python versions.


Port binding for the docker container. Two different ports one for host machine (a user's computer) second is for the container. Now what matters
is that two different containers cannot run on same host machine port for example if port is like this container 1 8080:3000 and container 2 8000:3000
meaining the 8000 is the host machine port and the 3000 is the container port. The container 2 will not run in that case because the host maching port that it is using is already in use that's why it needs different 
port for host machine so, it could be 3000, 5000 etc 




Docker vs Virtual Machine

VM comes with its own kernal and its own operating system that's why the 
it is big in size and on top of that you have your own application running
in the system makes it even large.

while docker uses the host operating system kernal and hardware meaning
the computer and the operating system that the computer has which is going to be used by the docker, the only thing docker brings is its container 
that's why overall size of docker container is very light compare to VM.



Docker Network - Is used for muntiple contaniers to communicate between each others and also interact with each other. 
This can be done by creating the network around the containers that you want them to communicate with each other 

Docker helps connect the application and container running on local host to use an particular techonology like database from our application.
for example the the flask application using mongodb. The application running on your compiler and share the database that is running on container from ports, url, and database name (also enviroment variables)





Docker Compose - used to run, define multi-container application
for example if you have an application and you are using many containers
to run and test the application in your machine now everytime you run a container you have to write commands in specif way for each techonology to run the container so there comes docker compose it is used for writing all the container commands and run it all at once so you have all the containers running, those commands are in YAML file (compose.yaml) in yaml launguage.

By doing this it saves time to write all the commands one by one and it also 
saves the commands in file so you don't forget it.

quick analogy: At night you turn on the lights for kitchen, living room, bathroom, work room one by one but imagine having one swtich for every light
if you turn on that switch every room light will be on automatically.

In the yaml file you can define the image information in a specifc way 
but to run the image and to created the container out of it needs to be done by the docker compose commands 

Docker compose also creates the network for our containers so we don't need to define it. The yaml file does it automatically




Docker is also used to dockerizing the application meaning that if everything is runnning well in your computer and now you want to share it with team member or someone else they will download the docker image you created and run it by creating the container of their own and it will run same as it ran in your computer