# Docker Database DDB_MongoDB_Replicaset

## This branch can creata a MongoDB With Replicaset

### mongo1 port 27017
### mongo2 port 27018
### mongo3 port 27019

## Need to run rs-init.sh script to set replicatset with priority for mongo1

###  TODO automat the process

start MongoDB with command
```
docker-compose up -d

```
connect to mongo1

```
docker exec -it mongo1 bash

chmod 744 /scripts/rs-init.sh

./scripts/rs-init.sh

``