---
hide:
  - navigation
---
Docker is like a super organized backpack for computer programs. It packs everything a program needs to run smoothly, so it can easily move from one computer to another without causing any mess or trouble.

## Install
Install Docker Desktop on [Mac](https://docs.docker.com/desktop/install/mac-install/), [Windows](https://docs.docker.com/desktop/install/windows-install/), or [Linux](https://docs.docker.com/desktop/install/linux-install/).

## Terminologies
Basic terminologies in docker are:

| Terminology    | Explanation                                                                                                       |
| -------------- | ----------------------------------------------------------------------------------------------------------------- |
| Docker         | Containerization platform for building, shipping, and running applications.                                       |
| Docker Desktop | Desktop application providing a GUI for Docker on Windows and macOS.                                              |
| Image          | Lightweight, standalone, executable package that includes application code, runtime, libraries, and system tools. |
| Container      | Runnable instance of a Docker image, encapsulating an application and its dependencies.                           |
| Dockerfile     | Text file with instructions to build a Docker image.                                                              |
| Registry       | Service for storing and distributing Docker images. These can be public or private.                               |
| Docker Hub     | Cloud-based public registry service by Docker for sharing and managing Docker images.                             |
| Docker Compose | Tool for defining and running multi-container Docker applications using a YAML configuration file.                |


Few other terminologies:

| Terminology     | Explanation                                                                                           |
| --------------- | ----------------------------------------------------------------------------------------------------- |
| Docker Engine   | Core of Docker responsible for building, running, and managing Docker containers.                     |
| Docker Daemon   | Background process managing Docker containers and handling Docker API requests.                       |
| Swarm           | Native clustering and orchestration for Docker, enabling the creation of a swarm of Docker nodes.     |
| Service         | In Docker Swarm, a definition of tasks to execute on nodes, specifying image, ports, and replicas.    |
| Stack           | Docker Compose file used in Docker Swarm mode, defining a multi-container application.                |
| Overlay Network | Docker Swarm network spanning multiple nodes for communication between containers on different hosts. |

## Docker Cheat Sheet
https://docs.docker.com/get-started/docker_cheatsheet.pdf

## Running Your First Docker Container
You can search for images at [docker hub](https://hub.docker.com/). In the docker image page, you would have instructions on how to pull the image and use it. Example: https://hub.docker.com/_/mongo

To pull (download) an image:
```
docker pull <image_name>
```

Use 'docker run' to create and run a new container. If the image can't be found, it will automatically pull.
```
docker run <image_name>
```
Or, alternatively:
```
docker create <image_name> # (1)!
docker start <container_name_or_container_id>
```
1. Outputs container id. Use this for the docker start command.


To run it as a container in background (detached) mode:

```
docker run -d <image_name>
```

To run it with a custom name for the container:
```
docker run -d --name <container_name> <image_name>
```

Container name needs to be unique. Rerunning the above command again would result in an error.

To delete a container:
```
docker rm <container_name>
```

To run the container and map the host port with the container port:
```
docker run -d --name <container_name> -p <host_port>:<container_port> <image_name>
```

Some configurations like naming the container, mapping the port can be made only when creating a container and these configurations can't be edited or modified after the container is created. If you need to modify them, you need to delete and recreate the container.

To stop the container:
```
docker stop <container_name_or_container_id>
```

To start the container:
```
docker start <container_name_or_container_id>
```

### Docker Container Shell
To get into the terminal of a running docker container:
```
docker exec -it container-name sh
```
If 'sh' didn't work, you can try 'bash' (one of these two are typically expected within a container).

Once inside the terminal of the docker container, you can run commands within the container. Few useful commands to use here are:
```
# List Directory
ls

# Present Working Directory
pwd

# Go one folder level back
cd ..

# List the environment variables within the container
env
```
### Logs
```
# Get logs from container
docker container-name logs

# Get last few logs
docker container-name logs | tail

# Stream the logs
docker container-name logs -f
```
### Docker Volume
The file system in containers are would be lost when the containers are restarted. To avoid this and have data persistence, we do a mapping of host volume to the container volume.

Example:
```
docker run -v /path/on/host:/path/in/container my_image
```

#### Named Volume
It is possible to provide a friendly name for the host volume, instead of providing an absolute path.
```
docker run -v my_named_volume:/path/in/container my_image
```


## DockerFile
File name must be called 'DockerFile'. Some useful commands to use inside the dockerfile are:
```
FROM - Source Image on top of which we are building our image
ENV - Set an environment variable (instead of this, preferable to use env  externally using docker compose)
RUN - Run a command inside the container. Can use multiple RUN commands in a docker file.
COPY - Copy from host to container
CMD - Entry Point Command for container. Only 1 per container.
```

### Docker Build
Build a docker image with the provided name and tag. 
```
docker build -t  [image-name]:[version] . 
```

The last argument in above command indicates the build context being passed for the docker build, which would be used by the COPY and other such commands. Using "." indicates to pass the current directory for the build context.

## Private Docker Registry
One option is to create a docker registry in AWS, by choosing ECR - Elastic Container Registry. AWS ECR supports maintaining only 1 container image in ECR. There are other options like 'Digital Ocean', where they allow having multiple images pushed to a single docker registry.

To push an image to a private repository,
1. You need to login to the docker's private repository (once at the beginning of the session).
2. Then use docker push. Example: 
```
docker push [docker-registry-domain/container-name:tag]
```

AWS CLI and credentials has to be configured.

## Docker Tutorials 
- Docker Tutorial for Beginners [Full Course in 3 Hours] by TechWorld with Nana: https://www.youtube.com/watch?v=3c-iBn73dDE

## Collection of Docker Compose Examples
https://github.com/docker/awesome-compose