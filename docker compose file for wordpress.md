<pre>
  [root@node5 yum.repos.d]# docker compose version
Docker Compose version v2.21.0
[root@node5 yum.repos.d]# cd ~
[root@node5 ~]# ls
anaconda-ks.cfg  Documents  Music            Pictures  Templates
Desktop          Downloads  original-ks.cfg  Public    Videos
[root@node5 ~]# ^C
[root@node5 ~]# mkdir test
[root@node5 ~]# cd test/
[root@node5 test]# ls
[root@node5 test]# ^C
[root@node5 test]# 
[root@node5 test]# vim docker-compose.yml
[root@node5 test]# docker compose up -d
[+] Running 33/2
 ✔ mysqlcon 10 layers [⣿⣿⣿⣿⣿⣿⣿⣿⣿⣿]      0B/0B      Pulled                 44.8s 
 ✔ wpcon 21 layers [⣿⣿⣿⣿⣿⣿⣿⣿⣿⣿⣿⣿⣿⣿⣿⣿⣿⣿⣿⣿⣿]      0B/0B      Pulled         69.3s 
[+] Running 3/3
 ✔ Network test_default  Created                                           0.2s 
 ✔ Container mysqlcon    Started                                           0.1s 
 ✔ Container wpcon       Started                                           0.0s 
[root@node5 test]# docker ps
CONTAINER ID   IMAGE              COMMAND                  CREATED          STATUS          PORTS                                   NAMES
94ee1dd47d33   wordpress:latest   "docker-entrypoint.s…"   17 seconds ago   Up 15 seconds   0.0.0.0:8080->80/tcp, :::8080->80/tcp   wpcon
7067b80eee57   mysql:latest       "docker-entrypoint.s…"   17 seconds ago   Up 16 seconds   3306/tcp, 33060/tcp                     mysqlcon
[root@node5 test]# cat docker-compose.yml 
version: "3.3"

services:
  mysqlcon:
    image: mysql:latest
    container_name: mysqlcon
    environment:
      - MYSQL_ROOT_PASSWORD=redhat
      - MYSQL_DATABASE=db_name
      - MYSQL_USER=db_user
      - MYSQL_PASSWORD=db_password
    volumes:
      - /blogdb:/var/lib/mysql

  wpcon:
    image: wordpress:latest
    container_name: wpcon
    environment:
      - WORDPRESS_DB_HOST=mysqlcon
      - WORDPRESS_DB_USER=db_user
      - WORDPRESS_DB_PASSWORD=db_password
      - WORDPRESS_DB_NAME=db_name
    #host-port:container-port
    ports:
      - "8080:80"
    links:
      - mysqlcon

[root@node5 test]# 
</pre>
