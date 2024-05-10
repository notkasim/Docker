# Docker

| Command           | Description                             |
| :-----------------| ----------------------------------------|
| apt install -y docker.io          | Installs Docker            |
| Systemctl status docker           | Checks Docker status            |
| sudo docker run hello-world       | Runs the hellow-world container from the hello-world image|
| sudo usermod -aG docker kasim     | allows you to run docker without sudo  |
| docker images                     | shows all the downloaded images   |
| docker search <IMIGENAME>         | search for a image   |
| docker pull <IMIGENAME>           | download a docker image without running it  |
| docker ps                         | shows all the running containers  |
| docker ps -a                      | show all the running and previosly run containers  |
| docker run -it ubuntu /bin/bash  | runs a ubuntu container and the command /bind/bash  |
| docker run -it -d ubuntu          | run the container in the background  |
| docker attach <CONTAINER ID>      | allows you to interace with a container  |
| docker rename <CONTAINER NAME> NEWNAME  | allows you to rename a container  |
| docker attach <NAME>              | allows you to interact with a container  |
| <C-P & Q>                         | to send a container to the background hold Controll and press P then Q  |
| docker run -it -d -p 8080:80 nginx| creates and nginx container that is is listening for http connections  |
| docker run -it -d --restart unless-stopped -p 8080:80 nginx  | runs a nginx container wich will be running unless its stopped manually |
| docker commit <CONTAINER ID> <IMAGE NAME>  | allows you to create an image from a container  |
| docker commit nginx sahaltek-nginx:1.0   | creates an image named sahaltek-nginx:1.0 from the nginx images  |
| docker commit <CONTAINER NAME> <IMAGE NAME>  |allows you to create an image from a container using container name   |
| docker commit sahaltek-nginx:1.0 hudds-nginx:1.0  | creates a image named hudds-nginx:1.0 from a container  |
| docker commit --change='EXPOSE 80' festive_dubinsky test1 |creates docker image that has port 80 exposed|
docker exec -it <ID> /bin/bash -- allows you to attack to a running container
docke exec -it f34dc9323ac1 /bin/bash -- allows you to attach to a running container
docker exec -it <NAME> /bin/bash -- allows you to attach to a container using the container name
docker exec -it sahal-ubuntu /bin/bash -- allows you to attach to a container using the container name
docker rmi <IMAG ID> -- allow you to delete a docker image
docker rmi   f34dc9323ac1 -- allows you to delete docker images
docker rmi <IMAGE NAME> -- allows you to delete docker images based on names
docker rmi ubuntu -- allows you to delete docker images
docker exec -it <CONTAINER ID> bash / allows you to attach to a container
docker exec -it sahal-nginx bash | allows you to attach to a conatiner
docker run -it -d -p 80:80 --name <CONTAINER NAME> nginx | creates an nginx container with a custom name
docker run -it -d -p 80:80 --name sahal-nginx nginx | creates an nginx container named sahal

For docker installation follow the docker Docs: here on this link: 

Docker Volumes
Docker volmes in Vscode
What is docker Volmues, how you can use it



| docker run -it -d -p 8080:80 nginx| creates and nginx container that is is listening for http connections  |
the nginx container is listening on port 80, which is mapped to port 8080 on the virutal machine, meaning when someone connects to port 8080 on the VM, the VM send the trafik to port 80 on the docker.



By default container don't save changes. For example if you install Vim on a Ubuntu container and exit the container  vim will be deleted. Docker image is a blueprint that allows you to create a container, and what you are trying to run is not inside the image then it is not going to be inside the container.

Docker containers run as long as the have something to do. Once a container has nothing to do, it exits and deletes itsfel. Containers are not statful, changes made in a container are not safed the changes need to be in the image because the image is the blurprint for the container.

Running a container in the background.
if you have a command that you would like to run in a container then you can create a container and run that command. For example docker run -it ubuntu /bin/bash. Onnce a container has being sent to the background you interact it with the command: docker attack <container ID> 



in docker you can create an image out of containers. example command to create an image from a container.
docker commit <CONTAINER NAME> <IMAGE NAME>
docker commit <CONTAINER ID> <IMAGE NAME>
docker commit --change='EXPOSE 80' festive_dubinsky test1
When a container is create from an image that you created the service will not be running unless you set "An enry point", meaning what command should be run when a new container is created. Example command of creating an Nginx image from the orinal image that will have port 80 exposed. docker commit --change='EXPOSE 80' festive_dubinsky test1
docker commit --change='ENTRYPOINT ["nginxctl", "-DFOREGROUND"]' kind_easley n1.1 - entry point for Nginx running on a docker ubuntu.

The process of creating an image from a container can be automated using a Docker file.









