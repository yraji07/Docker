### Installation  on ec2 vm 
$ sudo apt update 
$ curl -fsSL https://get.docker.com -o get-docker.sh
$ sh get-docker.sh
$ sudo usermod -aG docker <ubuntu>               (ubuntu is the user name)
$ exit 

and relogin 
Now u can run the "docker info" command and see the client, plugins & server info 

# Task 

# Run hello-world docker container  and observe the container status 

$ docker container run hello-world

Unable to find image 'hello-world:latest' locally
latest: Pulling from library/hello-world
2db29710123e: Pull complete
Digest: sha256:4e83453afed1b4fa1a3500525091dbfca6ce1e66903fd4c01ff015dbcb1ba33e
Status: Downloaded newer image for hello-world:latest

Hello from Docker!
This message shows that your installation appears to be working correctly.

To generate this message, Docker took the following steps:
 1. The Docker client contacted the Docker daemon.
 2. The Docker daemon pulled the "hello-world" image from the Docker Hub.
    (amd64)
 3. The Docker daemon created a new container from that image which runs the
    executable that produces the output you are currently reading.
 4. The Docker daemon streamed that output to the Docker client, which sent it
    to your terminal.

To try something more ambitious, you can run an Ubuntu container with:
 $ docker run -it ubuntu bash

Share images, automate workflows, and more with a free Docker ID:
 https://hub.docker.com/

For more examples and ideas, visit:
 https://docs.docker.com/get-started/ 

 ![preview](Screenshot%202023-04-14%20144831.png) 

# Check the docker images and also write down the size of hello-world image
 
 $ docker images hello-world          (this command gives the image sizeof hello-world)

 REPOSITORY    TAG       IMAGE ID       CREATED         SIZE
hello-world   latest    feb5d9fea6a5   18 months ago   13.3kB 

 ![preview](Screenshot%202023-04-14%20150918.png) 

# Run the nginx container with name as nginx2 and expose it on 8080 port on docker host

Now the run the following command: 
----------------------------------
 $ docker container run --name nginx2 -p 8080:80 -d nginx
 
 output: 
7e2fc785ed3eb777d397e8bed6a458e0e1c6608e4cd684c83e199ec197f5b3f0 
![preview](Screenshot%202023-04-14%20153246.png) 

check on the port http://ip:8080 
![preview](Screenshot%202023-04-14%20153746.png)

# Explain docker container lifecycle
Refer: https://linuxhandbook.com/container-lifecycle-docker-commands/
 
 The complete lifecycle of a docker container revolves around five phases: 
 Create phase. 
 Running phase. 
 Paused phase/unpause phase. 
 ![preview](Screenshot%202023-04-14%20155210.png)

There is a list of following commands:
docker --help
docker container ls


# Explain what happens when you run the docker container 
 The docker run command creates running containers from images and can run commands inside them. When using the docker run command, a container can run a default action (if it has one), a user specified action, or a shell to be used interactively. 
![preview](Screenshot%202023-04-14%20162456.png)


# Show all the states of docker container on nginx based container 
Refer this link
https://www.docker.com/blog/how-to-use-the-official-nginx-docker-image/

# Explain docker architecture 

Docker architecture. Docker uses a client-server architecture. The Docker client talks to the Docker daemon, which does the heavy lifting of building, running, and distributing your Docker containers. The Docker client and daemon can run on the same system, or you can connect a Docker client to a remote Docker daemon.


