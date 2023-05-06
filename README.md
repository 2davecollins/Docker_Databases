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
### MongoDB single instance DDB_mongoDB_Single
### MongoDB replicaset branch DDB_MongoDB_Replicaset
### Postgress with pgadmin DDB_Postgress_pgadmin


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

