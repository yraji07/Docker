Bridge networks: 
----------------

$ ifconfig
$ docker container run -d --name C1 alpine sleep 1d          (c1 contains the sleep 1d mode)
$ docker network inspect bridge
$ docker network ls
$ docker network create -d bridge --subnet "10.0.0.0/24" my_bridge
$ docker network ls
$ docker container run -d --name C2 --network my_bridge alpine sleep 1d           (prepraing containers) 
$ docker container run -d --name C3 --network my_bridge alpine sleep 1d           (prepraing containers)
$ docker container ls
$ docker network inspect my_bridge                         (it giges my_ bridge layers)
$ docker container exec C2 ping -c 2 C3                    (pings c2 to c3)
$ docker container exec C2 ping -c 2 10.0.0.3             (pings c2 to c3 ip addr)
$ docker container run -d --name mysqldb -v mysqldb:/var/lib/mysql -P -e MYSQL_ROOT_PASSWORD=rootroot -e MYSQL_DATABASE=employees -e MYSQL_USER=qtdevops -e MYSQL_PASSWORD=rootroot --network my_bridge mysql
$ docker network inspect my_bridge
$ docker container run --name phpmyadmin --network my_bridge -d -e PMA_HOST=mysqldb -P phpmyadmin             (pulls the phpadmin)
$ docker container ls
   Now check in the port php page 
$ docker network connect my_bridge C1 
$ docker exec C2 ping C1

docker container exec -it C1 /bin/sh
# ip addr

# exit 
docker network disconnect bridge C1
docker container exec C1 ip addr
docker network disconnect bridge C1
docker container exec C1 ip addr
