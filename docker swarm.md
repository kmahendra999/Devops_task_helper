When install docker 
it create 3 netword by Default 

Bridge - default network for container
container receive ip address : 172.17.0.0
container receive ip address : 172.17.0.1-x  containers
docker run ubuntu

none
docker run ubuntu --network=none

host
docker run ubuntu --network=host
esme base machine se connect hote he when we map ports -p 5000:80

docker netword ls for see networks

if we want to create network and isolate then 
create network and ssign

=====================================
docker cluster rebuild karne ke liye
docker swarm init --force-new-cluster

docker node promote - worker ko manager node banane ke liye

======================================

docker swarm working

on master
-----------
docker swarm init
or
docker swarm init --advertise-addr 192.168.56.101

docker node ls to see nodes

on workers - paste join comamnd

then master docker node ls

if worker want to leave : docker swarm leave

FOR REMOTE NODE on masSTER : docker rm  DOCKERNODE-2

FOR JOIN MASTER NODES : docker swarm join-token manager
it will genrate token for join node as master

on master docker node ls for see master nodes.

leader , reachable are master
worker are workder node in docker ls

for docker worker join command :
docker swarm join-token worker


worker node ko promote karke as master banane ke liye: 
from master : docker node promote docker-node2
docker node ls

shutdown now for shutdows the node/container / pc

swarm me kam karne ke liye kam se kam 2 masster hone chahiye


jab 2 nodes bhi nahi ho masster ke cluster me tab
docker swarm init --force-net-cluster --advertise-addr 192.168.56.101


## Manage replics


docker service create --replicas=3 mywebserver
docker service create --replicas=3 --netword=frontend mywebserver
docker service create --replicas=3 -p 8080:80 mywebserver

3 replicas on x nodes
docker service create --replicas=3 mywebserver

1 instance on every node
docker service create --mode global mywebserver

update no of replics
docker service create --replicas=3 --name webserver my-web-server
docker service update --replicas=3 webserver







