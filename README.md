# Docker Cheat Sheet

### Run:
- `docker run -it image-name`: Runs a container interactively based on the specified image.
- `docker run -itd --name container-name --rm image-name`: Runs a container with a custom name and removes it when stopped.
- `docker run -it -p on:from image-name`: Runs a container with port mapping.
- `docker run -it -P image-name`: Runs a container with automatic port mapping.
- `docker run -itd --network network-name --rm --name container-name`: Runs a container with a specific network and name.
- `docker run -it -P image-name`: Runs a container with automatic port mapping.
- `docker run -it file-name [CMD]`: Runs a container with a specific command.
- `docker run -itd container-name [CMD]`: Runs a command in a running container in detached mode.

### Pulling an image:
- `docker pull image-name`: Pulls an image from a registry to your local machine.

### Building and Tagging Images:
- `docker build -t file-name location`: Builds a custom image using a Dockerfile.
- `docker build -t image-name:tag location`: Builds an image with a specific tag.
- `docker tag image-name new-tag-name`: Tags an existing image with a new name.

### Images Management:
- `docker images`: Lists all images on your local machine.
- `docker image ls`: Lists all images on your local machine.
- `docker image rm image-id`: Removes a specific image from your local machine.
- `docker image inspect image-id`: Retrieves metadata about a specific image.
- `docker image prune -a`: Removes all unused images from your local machine.
- `docker image history image-id`: Displays the history of changes to an image.

### Container Management:
- `docker container rm container-id or container-name`: Removes a specific container.
- `docker container stop container-id or container-name`: Stops a specific container.
- `docker container prune`: Removes all unused containers from your local machine.
- `docker attach container-name`: Attaches to a running container's console or output.

### Docker Network:
- `docker network create bridge-name`: Creates a user-defined bridge network.
- `docker network ls -a`: Lists all networks, including ones that are not in use.
- `docker network inspect network-name`: Retrieves details about a specific network.
- `docker network rm network-name`: Removes a specific network.
- `docker network connect network-name container-name`: Connects a container to a specific network.
- `docker network disconnect network-name container-name`: Disconnects a container from a specific network.

### Docker Volume:
- `docker run -it -v /host/path:/container/path image-name` - This command mounts the directory `/host/path` on the host machine into the container at `/container/path`
- `docker run -it -v my_volume:/container/path image-name` - This command uses a Docker-managed volume named `my_volume` and mounts it into the container at `/container/path`
- `docker volume create volume-name`: Used to create a volume.
- `docker volume inspect volume-name`: Displays detailed information on one or more volumes.
- `docker volume ls`: Lists volumes.
- `docker volume prune`: Removes unused local volumes.
- `docker volume rm volume-name`: Removes one or more volumes.


### Docker Hub Integration:
- `docker push image-name`: Pushes an image to a registry like Docker Hub.

### Miscellaneous:
- `docker stats`: Displays live system resource usage statistics for all containers.

# Keywords

- ```-it``` stands for interactive.
- ```-p``` stands for port or port mapping.
- ```-t``` stands for tag.
- ```-d``` stands for `detach.` It tells Docker to run the container in the background, meaning it will start the container and return you to the command prompt without attaching your terminal to the container's output. This is useful for running containers that you don't need to actively monitor.
- ```-v``` stands for "volume." It is used to create a volume or bind mount between the host machine and the Docker container.

## Note

Replace `image-name`, `image-id`, `container-id`, `container-name`, `file-name`, and `[CMD]` with your actual values when using the commands.

For more information, refer to the [Docker documentation](https://docs.docker.com/).
