# Docker Database Master branch

## install docker on ubuntu
```
# apt update
# apt upgrade
# apt install apt-transport-https ca-certificates curl software-properties-common

curl -fsSL https://download.docker.com/linux/ubuntu/gpg | sudo apt-key add -

add-apt-repository "deb [arch=amd64] https://download.docker.com/linux/ubuntu focal stable"

apt-cache policy docker-ce

sudo apt install docker-ce

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

### MySQL Branch DDB_MySQL
### MySQL with phpmyadmin Branch DDB_MySQL_PHPMYADMIN
### MongoDB single instance Branch DDB_mongoDB_Single
### MongoDB replicaset Branch DDB_MongoDB_Replicaset
### Postgress with pgadmin Branch DDB_Postgress_pgadmin

### Redis with redisinsight

[Start with Docker](https://redis.io/docs/stack/get-started/install/docker/)
[RedisInsight Docs](https://redis.io/docs/ui/insight/)
[Redis Manual](https://redis.io/docs/manual/)
```
docker run -d --name redis-stack -p 6379:6379 -p 9001:8001 redis/redis-stack:latest

navigate to <ipaddress>:9001 to access redisinsight.#

to stop container run

docker stop redis-stack


```


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

