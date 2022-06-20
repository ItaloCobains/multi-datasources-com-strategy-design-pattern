## Comandos Docker Postgres

docker run --name postgres -e POSTGRES_USER=italo -e POSTGRES_PASSWORD=italo -e POSTGRES_DB=heroes -p 5432:5432 -d postgres

docker ps

docker exec -it postgres /bin/bash

## Cliente

docker run --name adminer -p 8080:8080 --link postgres:postgres -d  adminer


## Comandos Docker MongoDB

docker run --name mongodb -p 27017:27017 -e MONGO_INITDB_ROOT_USERNAME=admin -e MONGO_INITDB_ROOT_PASSWORD=admin -d mongo:4

## Cliente

docker run --name mongoclient -p 3000:3000 --link mongodb:mongodb -d mongoclient/mongoclient

docker exec -it mongodb mongo --host localhost -u admin -p admin --authenticationDatabase admin --eval "db.getSiblingDB('herois').createUser({user: 'italo', pwd: 'italo', roles: [{role: 'readWrite', db: 'herois'}]})"