# Docker Database Master branch

## Install docker on ubuntu

This branch contains information on how to use docker and docker-compose to create different databases
first step is to install docker on ubuntu server. use VirtualBox or any cloud rsourse tested on Ubuntu server 20.04 VirtualBox 7.0 
```
# apt update
# apt upgrade
# apt install apt-transport-https ca-certificates curl software-properties-common

curl -fsSL https://download.docker.com/linux/ubuntu/gpg | sudo apt-key add -

add-apt-repository "deb [arch=amd64] https://download.docker.com/linux/ubuntu focal stable"

apt-cache policy docker-ce

sudo apt install docker-ce

sudo groupadd docker
sudo usermod -aG docker ${USER}
su - ${USER}

```
[ref docker install](https://www.digitalocean.com/community/tutorials/how-to-install-and-use-docker-on-ubuntu-20-04)

### install docker-compose

```
sudo curl -L "https://github.com/docker/compose/releases/download/1.29.2/docker-compose-$(uname -s)-$(uname -m)" -o /usr/local/bin/docker-compose

sudo chmod +x /usr/local/bin/docker-compose

```
[ref docker-compose install]( https://www.digitalocean.com/community/tutorials/how-to-install-and-use-docker-compose-on-ubuntu-20-04)

## Databases using docker-compose

## Rationaal Databases
### MySQL Branch DDB_MySQL
### MySQL with phpmyadmin Branch DDB_MySQL_PHPMYADMIN
### Postgress with pgadmin Branch DDB_Postgress_pgadmin

## NoSQL Databases

### MongoDB single instance Branch DDB_mongoDB_Single
### MongoDB replicaset Branch DDB_MongoDB_Replicaset

### Redis with redisinsight

[Start with Docker](https://redis.io/docs/stack/get-started/install/docker/)


[RedisInsight Docs](https://redis.io/docs/ui/insight/)


[Redis Manual](https://redis.io/docs/manual/)


```
docker run -d --name redis-stack -p 6379:6379 -p 9001:8001 redis/redis-stack:latest

navigate to <ipaddress>:9001 to access redisinsight 

to stop container run
docker stop redis-stack

```
## Graph Databases

### Neo4j Branch DDB_NEO4J

### [Dgraph docker reference] (https://dgraph.io/docs/deploy/installation/single-host-setup/)

```
    docker run --name dgraph -d -p "8080:8080" -p "9080:9080" -v db:/dgraph dgraph/standalone:latest

    docker run --name ratel  -d -p "9000:8000"  dgraph/ratel:latest

    navigate to ipaddress:9000 navigate to ipaddress port 8080

    or use playgraph
    https://play.dgraph.io/
 
    issue with password use docker ratel and point to ipaddress:8080

```

### Neo4j

##### [docker tutorial neo4j](https://neo4j.com/developer/docker-run-neo4j/)

##### [Neo4j Desktop](https://neo4j.com/download/)

## Docker commands to free up space if needed
use sudo if required
```
$ df -h
$ free

$ sudo docker system prune -a  # all stopped and dangling images

$ sudo docker image prune -a -f
$ sudo docker container prune
$ sudo docker volume prune -f
$ sudo docker system prune -a -f
$ sudo docker container stop $(docker container ls -aq) # stop all container
$ sudo docker-compose down -v # deletes volume


```

