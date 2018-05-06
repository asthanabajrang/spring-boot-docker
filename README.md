# Spring boot application with docker

Basic example of spring boot application with docker containers

## Running this application-

   mvn clean install

   mvn spring-boot:run

## Run application as container (two step build image and run containers)

## Build docker image-

### Either use below command to create image or use spotify plugin to build image (by deafult this app builds image using plugin).
 We are passing jar file name as argument. We can hardcode this path instead in Docker file. Command to build image

    docker build -f Dockerfile -t web --build-arg JAR_FILE=target/springboot-docker-1.0-SNAPSHOT.jar .

### Run docker image
    docker run -d -p 8080:8080 -t web


---------------------------------------------------------------------------------------


## Basic Docker commands-

1. List all images available in local system
    docker images -a

2. Remove all images available in local system
    docker rmi $(docker images -a -q)elow

3. List all the docker container running and exited
    docker ps -a

4. Remove all containers
    docker rm $(docker ps -a -q)

5. Build docker image-

Either use below command to create image or use spotify plugin to build image. Here we are passing jar file name as argument. We can
hardcode this path instead in Docker file.

    docker build -f Dockerfile -t web --build-arg JAR_FILE=target/springboot-docker-1.0-SNAPSHOT.jar .

6. Run docker image
    docker run -d -p 8080:8080 -t web
