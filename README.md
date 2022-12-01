# first docker project

## Installing Images for Project

        docker pull mongo
        docker pull mongo-express

# creating network

        docker network ls

        docker network create mongo-network

# setting mongodb

        docker run -d -p 27017:27017 -e MONGO_INITDB_ROOT_USERNAME=admin -e MONGO_INITDB_ROOT_PASSWORD=password --name mongodb --net mongo-network mongo

- if you have already installed mongodb and takes error.

        docker run -d -p 27018:27017 -e MONGO_INITDB_ROOT_USERNAME=admin -e MONGO_INITDB_ROOT_PASSWORD=password --name mongodb2 --net mongo-network mongo

# setting mongo-express

        docker run -d -p 8082:8082 -e ME_CONFIG_MONGODB_ADMINUSERNAME=admin -e ME_CONFIG_MONGODB_ADMINPASSWORD=password --net mongo-network --name mongo-express -e ME_CONFIG_MONGODB_SERVER=mongodb3 mongo-express
