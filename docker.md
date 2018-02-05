# Docker

## Introduction

An **image** is  alightweight, stand alone executable package that includes everything
needed to run a piece of software including the code, a runtime, libraries, env vars
and config files.

A **container** is a runtime instance of an image. What the image becomes in memory
when actually executed. It runs *completely isolted* from the host environment by default,
only accessing host files and ports when configured to do so.

Is the container configured with the image?

Container package depdencies never need to be installed on the host system.

## Commands

`docker build -t <tagname> .` will build a docker image in your current directory.
`docker run -p <HOST_PORT_NUM>:<DOCKER_PORT_NUM> <tagname>` will run a docker container
with your host port mapped to a docker port if needed.

`docker service ls` will list all the docker services that you have running
`docker swarm init` will create a swarm node of docker instances for you. it is 
needed to be done before you do a `docker stack deploy`
`docker stack deploy -c <docker-compose-yaml file path> <name of application>`
eg. `docker stack deploy -c docker-compose.yml getstartedlab`

`docker service ps <service_name>` will show all the tasks for the desired service

