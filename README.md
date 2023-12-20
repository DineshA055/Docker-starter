# Docker-starter

Docker Architecure

![image](https://github.com/DineshA055/Docker-starter/assets/101075223/83b4bb87-3521-41dd-92d3-26489e6378a8)


What is Docker ?


 Docker is an open source platform that enables developers to build, deploy, run, update and manage containers—standardized, executable components 
that combine application source code with the operating system (OS) libraries and dependencies required to run that code in any environment.

Docker in simple term


Docker provides the ability to package and run an application in a loosely isolated environment called a container. 
The isolation and security lets you run many containers simultaneously on a given host.

Docker is a set of platform as a service (PaaS) products that use OS-level virtualization to deliver software in packages called containers

Docker is a tool designed to make it easier to create, deploy, and run applications by using containers.


https://docs.docker.com/get-started/overview/   - Docker Overview 


Docker architecture explained :-  
`

Docker uses a client-server architecture.
The Docker client talks to the Docker daemon, which does the heavy lifting of building, running, and distributing your Docker containers. 
The Docker client and daemon can run on the same system, or you can connect a Docker client to a remote Docker daemon. 
The Docker client and daemon communicate using a REST API, over UNIX sockets or a network interface. 
Another Docker client is Docker Compose, that lets you work with applications consisting of a set of containers.

https://docs.docker.com/get-started/images/docker-architecture.webp

The Docker daemon

The Docker daemon (dockerd) listens for Docker API requests and manages Docker objects such as images, containers, networks, and volumes. A daemon can also communicate with other daemons to manage Docker services.
The Docker client

The Docker client (docker) is the primary way that many Docker users interact with Docker. When you use commands such as docker run, the client sends these commands to dockerd, which carries them out. The docker command uses the Docker API. The Docker client can communicate with more than one daemon.
Docker Desktop

Docker Desktop is an easy-to-install application for your Mac, Windows or Linux environment that enables you to build and share containerized applications and microservices. Docker Desktop includes the Docker daemon (dockerd), the Docker client (docker), Docker Compose, Docker Content Trust, Kubernetes, and Credential Helper. For more information, see Docker Desktop.
Docker registries

A Docker registry stores Docker images. Docker Hub is a public registry that anyone can use, and Docker looks for images on Docker Hub by default. You can even run your own private registry.

When you use the docker pull or docker run commands, Docker pulls the required images from your configured registry. When you use the docker push command, Docker pushes your image to your configured registry.
Docker objects

When you use Docker, you are creating and using images, containers, networks, volumes, plugins, and other objects. This section is a brief overview of some of those objects.
Images

An image is a read-only template with instructions for creating a Docker container. Often, an image is based on another image, with some additional customization. For example, you may build an image which is based on the ubuntu image, but installs the Apache web server and your application, as well as the configuration details needed to make your application run.

You might create your own images or you might only use those created by others and published in a registry. To build your own image, you create a Dockerfile with a simple syntax for defining the steps needed to create the image and run it. Each instruction in a Dockerfile creates a layer in the image. When you change the Dockerfile and rebuild the image, only those layers which have changed are rebuilt. This is part of what makes images so lightweight, small, and fast, when compared to other virtualization technologie

Docker -COMMANDS :- 

  DOCKER COMMANDS


1. To install docker from internet

sudo apt-get install docker.io

2. To find version for docker

docker -v    or docker --version

3. Docker service status check

service docker status

if docker is working show status if not in workin status shows ->docker is stopped

4. cmd :- docker info

if docker have any error on connecting it will show [ can’t connect to the Docker daemon ]

5. To start docker service

service docker start

6. To check whether it started

service docker status

o/p -> docker is running

7. Now check same command of 4 one docker info

docker info                    -> gives complete information of docker 

8. If you want to what are the images was created

docker images

9. If you want to check docker process status
 
docker ps

if docker is not running only one set cloumn will show

10. if you want to know running and stopped container want to show

docker ps -a

11. test the command

docker -it ubuntu /bin/bash 

if image not find it will take form docker hub ----< need to check the command

12. What to know which os is running in container

cat etc/os-release

13. If image available of jenkins you can save it in docker conatiner to run in feature if required

docker pull jenkins

14. To build docker image

docker build -t  appname   .                                   From current directory of repository mention dot it will take docker file to build the image

15. To know the status of docker build

docker images  & docker ps  

16. To pull images to docker hub

Need to login :- cmd :- docker login

next tag the image :- CMD :-     docker tag repositoryname:latest dockerhub-username/repositoryname

 #repository name you can see in docker images command it will display name in repository

next after tagging push to docker hub    -----cmd :-  docker push docker-hub-username/docker-

image-name:version               version : maye latest or v1,2,3 ....

17. Find any information about conatiner working status find out any issue

How to see logs for container 

CMD :- docker logs container_id

18. Docker network  
The ‘docker network’ command is used to know the details of the list of networks in the cluster.
Ex: - NETWORK ID          NAME                DRIVER              SCOPE
85083e755f04        bridge              bridge              local
f51d1f2379e0        host                host                local
5e5d9a154c00        none                null 

19. Docker copy 
This command copies a file from docker to the local system. Here is how to use it –
greatlearning@greatlearning:/home/greatlearning$ sudo docker cp 09ca4feb7tfc:/usr/local/apache2/logs/httpd.pid /home/greatlearning/

20. Docker volume  
This command creates a volume so that the docker container can use it to store data. Here is how to use it –
$ docker volume create

7e7bc886f69bb24dbdbf19402e31102a25db91bb29c56cca3ea8b0c611fd9ad0
To check whether this command created the volume or not, run the following command -

$ docker volume ls

DRIVER              VOLUME NAME
local               7e7bc886f69bb24dbdbf19402e31102a25db91bb29c56cca3ea8b0c611fd9ad0
21. Docker logout  
This command will log you out of the docker hub. Here is how to use it –
greatlearning@greatlearning:/home/greatlearning$ docker logout
Removing login credentials for https://index.docker.io/v1/
22. Docker exec  
This command is used to access the container that is running. Here is how to use it –  
CMD :- docker exec -it f92873921f86 bash -it (iteractive terminal)   
mysql -uroot -pmy-secret-pw
SHOW DATABASES;
23. Docker search  
The “docker search” command searches for specific images through the Docker hub. This command returns the specific information, including image name, description, automated, official stars, etc. Here is how to use it – 
docker search MySQL
