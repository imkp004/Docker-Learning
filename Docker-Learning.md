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