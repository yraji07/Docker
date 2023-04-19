
# Class4
---------  

sudo apt update
sudo apt install net-tools openjdk-11-jdk tomcat9 -y
# to check network
ifconfig
# to check java
java -version
# to check tomcat
sudo systemctl status tomcat9


# Installing springpetclinc in Docker 
--------------------------------------
sudo apt update
sudo apt install openjdk-17-jdk maven -y
git clone https://github.com/spring-projects/spring-petclinic.git
cd spring-petclinic
# java package
mvn package
java -jar target/spring-petclinic-3.0.0-SNAPSHOT.jar

![preview](imgs/Screenshot%202023-04-14%20210421.png) 
![preview](imgs/Screenshot%202023-04-14%20210529.png)
![preview](imgs/Screenshot%202023-04-14%20214539.png) 

Install docker in this machine 

$ curl -fsSL https://get.docker.com -o get-docker.sh
$ sudo sh get-docker.sh
$ sudo usermod -aG docker ubuntu
$ exit
re-login
$ docker info 

$ cd spring-petclinic
$ vi dockerfile  
keep this in vi file

FROM amazoncorretto:17-alpine-jdk
LABEL author=khaja
ADD target/spring-petclinic-3.0.0-SNAPSHOT.jar /springpetclinic.jar
EXPOSE 8080
CMD ["java", "-jar", "/springpetclinic.jar"]

$ docker image build -t spc:1.0 .
to create container

$ docker container run -d -P 8080:8080 spc:1.0
$ docker container run -d -P 8081:8080 spc:1.0
$ docker container run -d -P 8082:8080 spc:1.0
$ docker stats 


# Class 9 Docker 
Game of life 
------------- 

Exercise:
Gameof life application:
This requires java 8
this requires tomcat 8 or 9
copy the gameoflife.war application into webapps folder of tomcat Refer Here
This runs on port 8080 


# Class 10 
-----------
Experiments:

Create a mysql container
Command: docker container run -d mysql 
create a postgresql container 
Command: docker container run -d postgres
list all the volumes

![preview](imgs/Screenshot%202023-04-15%20101735.png)

inspect all the volumes
create volume docker volume create myvol
![preview](imgs/Screenshot%202023-04-15%20102406.png)

inspect myvol 
![preview](imgs/Screenshot%202023-04-15%20102559.png)

Figure out locations of volumes in your local systems 
![preview](imgs/Screenshot%202023-04-15%20102801.png)
