# Docker

1. docker pull <image name>
It will connect to docker deamon in Docker HOst and then Docker Deamon will connect with Docker RegistryHub to get the image. And then it will be pulled into dockerhost

2. docker run -p 80:8080 -d <image name>
# ( local port:containerport )

# HOW TO INSTALL DOCKER AND PULL,PUSH IMAGE TO DOCKER REGISTRY HUB

1. Install docker desktop
2. check the docker version
   # docker --version
3. Create account in docker hub and login to it
   # docker login
4. After logging into docker hub we can able to pull or push the images from it by using below command for pulling image
   # docker pull <image name with tag >
5. After pulling the image check it whether it came or not
   # docker images (we will get the list of images)
6. After checking the pulled image then we can run the image
   # docker run --name <give name to the container which is going to create> -p <localport:containerport> -d <image name>
7. To get the list of containers
   # docker ps (shows running containers)
   # docker ps -a (shows all containers running and stopped )
   # docker ps -q (shows only container ID)
   # docker ps -a -f "status=exited" (shows stopped containers. -f means filter)
9. Command to connect container terminal
   # docker exec -it <container name> /bin/sh
10. Commands to start,stop,remove. (we cannot remove container without stopping)
    # docker stop <container-name>
    # docker start <container-name>
    # docker rmi <image-id> (To remove image)


# To PUSH IMAGE TO DOCKER HUB

1. Create the folder and write a docker file, index.html file ( We can take the existing nginx image and edit it as per our requirement )
2. Once docker file and index.html file was written, Build the image
   # docker build -t <dockerhub-id>/<image-name>:v1 . (. is given so that dockerfile and index.html are in current folder and will be executed from here and -t is tag)
   # docker build -t ahmed-66/mynginx-image:v1 .
3. Once after building the image, Run the image
   # docker run --name <name giving to container> -p 80:80 -d dockerhub-id>/<image-name>:v1
4. If we want to change the tag
   # docker tag dockerhub-id>/<image-name>:v1 dockerhub-id>/<image-name>:v1-release
5. Then we can push the docker image to docker hub
   # docker push dockerhub-id>/<image-name>:v1-release


# COMMANDS
# Docker Container Commands
docker ps
Lists running containers.

docker ps -a: Lists all containers (running and stopped).

docker ps -q: Lists only the container IDs of running containers.

docker run <image>
 Creates and starts a new container from a specified image.

docker stop <container_id>
 Stops a running container.

docker start <container_id>
 Starts a stopped container.

docker restart <container_id>
 Restarts a container.

docker rm <container_id>
 Removes a container (must be stopped first).

docker exec -it <container_id> <command>
 Runs a command in a running container, e.g., /bin/bash to open a shell.

docker logs <container_id>
 Displays logs for a container.

docker attach <container_id>
 Attaches to a running container to interact with it.

docker top <container_id>
 Shows the running processes of a container.

docker inspect <container_id>
 Provides detailed information about a container.

docker pause <container_id>
 Pauses a running container.

docker unpause <container_id>
 Unpauses a paused container.

docker stats
 Displays resource usage statistics for containers (CPU, memory, etc.).

docker kill <container_id>
 Sends a SIGKILL signal to a container to force it to stop.

# Docker Image Commands

docker images
 Lists all images on the system.

docker pull <image>
 Downloads an image from Docker Hub or another repository.

docker build -t <image_name> <path>
 Builds a Docker image from a Dockerfile located at <path>.

docker rmi <image_id>
 Removes an image from the system.

docker tag <image_id> <new_tag>
 Tags an image with a new tag.

docker push <image_name>
 Uploads an image to a Docker registry (like Docker Hub).

# Docker Volume Commands
docker volume ls
 Lists all Docker volumes.

docker volume create <volume_name>
 Creates a new Docker volume.

docker volume rm <volume_name>
 Removes a volume.

docker volume inspect <volume_name>
 Provides detailed information about a volume.

# Docker Network Commands

docker network ls
 Lists all Docker networks.

docker network create <network_name>
 Creates a new Docker network.

docker network inspect <network_name>
 Provides detailed information about a Docker network.

docker network rm <network_name>
 Removes a Docker network.

docker network connect <network_name> <container_id>
 Connects a container to a network.

docker network disconnect <network_name> <container_id>
 Disconnects a container from a network.

# Docker System Commands

docker info
 Displays detailed system-wide Docker information.

docker version
 Shows the version of Docker installed.

docker system prune
 Cleans up unused Docker objects (containers, images, volumes, networks) to free up space.

docker stats
 Shows real-time resource usage statistics for containers.

# Docker Compose Commands (If you’re using Docker Compose)

docker-compose up
 Starts and runs the containers defined in a docker-compose.yml file.

docker-compose down
 Stops and removes all containers defined in a docker-compose.yml file.

docker-compose logs
 Shows logs for all containers defined in a docker-compose.yml file.

docker-compose ps
 Lists the status of containers managed by Docker Compose.

docker-compose build
 Builds images defined in the docker-compose.yml file.

docker-compose exec <service> <command>
 Executes a command inside a running container managed by Docker Compose.

# Other Useful Commands

docker login
Logs into a Docker registry (e.g., Docker Hub).

docker logout
 Logs out of a Docker registry.

docker info
 Provides detailed information about the Docker system (like version, configuration, etc.).

docker events
 Streams real-time events from the Docker daemon (e.g., container start, stop, etc.).

docker history <image>
 Displays the history of an image (which layers were created and when).

docker cp <container_id>:<path> <host_path>
 Copies files from a container to the host machine.

docker save <image>
 Saves an image to a tarball file.

docker load
 Loads an image from a tarball file.
