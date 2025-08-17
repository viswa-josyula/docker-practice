# Table of Contents
- [Table of Contents](#table-of-contents)
- [Basic Docker Commands](#basic-docker-commands)
- [Docker Run Commands](#docker-run-commands)

# Basic Docker Commands
- Run Docker Container -> `docker run <docker-image>`
  - ex: `docker run ubuntu`
> The Command Pulls the container if does not exist locally and runs the Container
- Run Container with Aruguments -> `docker run <docker-image> <action>`
  - ex: `docker run -it ubuntu bash`
  - ex: `docker run ubuntu sleep 30`
- List Running Containers -> `docker ps`
- Run Container in Detached Mode -> `docker run -d <docker-image>`
  - ex: `docker run -d ubuntu`
  - ex: `docker run -d ubuntu sleep 30`
- List all the Containers Active or Killed -> `docker ps -a`
- Stop Docker Container -> `docker stop <container-id>/<container-name>`
  - ex: `docker stop 1e23`
  - ex: `docker stop serenity-pod`
> Need not Specify Complete container-id to Delete
- Remove Docker Container -> `docker em <container-id>/<container-name>`
- List all Docker Images -> `docker images`
- Remove Docker Images -> `docker rmi <docker-image>`
  - ex: `docker rmi ubuntu`
> The Command will fail if any Container is Running with the Image
- Pull Docker Image -> `docker pull <docker-image>`
  - ex: `docker pull ubuntu`
> The command just pulls the Image and doesnot run the Container
- To execute any Command on Running Container -> `docker exec <container-id> <command> <command-specification>`
  - ex: `docker exec c1a19 cat /etc/*release*`

# Docker Run Commands
  - Docker Continer with Tag -> `docker run <image>:<tag> <arguments>`
    - ex: `docker run ubuntu:17.10 cat /etc/*release*`
  - Inspect Docker Container -> `docker inspect <container-id>`
    - `docker inspect 1e23y`
  - Attach to Docker Container -> `docker attach <container-id>`
    - ex: `docker attach q23re`
  - Port Mapping -> `docker run -p <host-port>:<container-port> <docker-image>`
    - ex: `docker run -p 8080:8080 -p 50000:50000 jenkins:jenkins`
  - Volume Mapping -> `docker run -v <host-directory/volume>:<container-directory> jenkins/jenkins`
    - ex: `docker run -p 8080:8080 -p 50000:50000 --restart=on-failure -v jenkins_home:/var/jenkins_home jenkins/jenkins:lts-jdk17`
  - Docker Logs -> `docker logs <container-id>`
    - ex: `docker logs 1w3r`