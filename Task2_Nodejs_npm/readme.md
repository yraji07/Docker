#  https://github.com/expressjs/express

# prerequests

Nodejs <= 0.10
Npm
Git
steps in Dockerfile:
---------------------
1. FROM (base image)   ubuntu or nodejs  
2. need to add prerequests (Run command)
3. clone repo
4. cd express
5. npm install express
6. npm install -g express-generator@4
7. express /tmp/foo && cd /tmp/foo
8. npm install
9. Expose 3000
10. workdir /tmp/foo
10. npm start (CMD ['npm', 'start'])
# ( enetry point ==> which will execu first when container start)
has context menu
-------------------------------------------------------------------------------------
Dockerfile : rough wrk ----------------------------------
/* FROM node:16-alpine3.16
RUN apk add --update npm && \
    apk add git && \
    git clone https://github.com/expressjs/express.git && \
    cd express && \
    npm install express && \
    npm install -g express-generator@4 && \
    express /tmp/foo && \ 
    cd /tmp/foo && \
    npm install
EXPOSE 3000
WORKDIR /tmp/foo
CMD ["npm","start"]  
---------------------------- 


$ mkdir nodejs
$ cd nodejs
$ vi Dockerfile
$ docker image build -t node:16-alpine .
$ docker image ls 
$ docker image ls -a
$ docker container run --name nodejs -d -p 3002:3000 node

![preview](images/Screenshot%202023-04-15%20170601.png)



From dockerplayground
---------------------
$ vi Dockerfile                         (prepare the file in vs.code) 
$ $ docker image build -t img1 .        (this command will build the image name is ur wish dut dont forget to keep dot .)
$ docker image ls
$ docker container ls
$ docker image ls -a
$ docker container run --name raji1 -d -p 3001:3000 img1     ( we  can also give 3001, 3002, 3003 )
a76e20619e7d5f4b272a76a5a33e08ac8ec8c2ed249e3da4ff91a99a5cae516e 


Dockerfile
---------- 

![preview](images/Screenshot%202023-04-15%20170601.png) 


