Creating the hello-world project

Go to docker hub and pull the hello-world image
and run it with docker run command.

Creating the ubuntu project

Go to docker hub and pull the ubuntu image
and run it with the docker run -it command
to access the terminal of the container.


Now delete the containers and the images


pull the mysql image
now pull the specific version of the mysql image
make container for each and give that containers a name
delete it


Now run the images and also specify the port and bind it with 
the container


create the docker network 
now attach the network with container

for example:
docker run -d -p 27017:27017 --name mongo --network mongo-network -e MONGO_INITDB_ROOT_USERNAME=admin -e MONGO_INITDB_ROOT_PASSWORD=qwerty mongo

-d for detach
-p for port binding
--name for giving container the name
--network To accah the existing network to the container
-e for enviroment variables


create a container and mount the voulme then delete the container but the data will still exists.