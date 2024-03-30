# - Docker Cheat Sheet



## Pulling an image

```bash
docker pull image-name
```

Example:

```bash
docker pull ubuntu
```

## Running Containers

```bash
docker run -it image-name
```

Example:

```bash
docker run -it ubuntu
```


## Spin a container with custom name

```bash
docker run -itd --name container-name --rm image-name
```

Example:

```bash
docker run -itd --name my-busybox --rm busybox
```

## List all images on your local machine:

```bash
docker images
```
or
```bash
docker image ls
```

## Remove an image from your local machine:

```bash
docker image rm image-id
```

## Inspect metadata about a specific image:

```bash
docker image inspect image-id
```

## Remove all unused images from your local machine:

```bash
docker image prune -a
```

## Remove a specific container:

```bash
docker container rm container-id or container-name
```

Example:

```bash
docker container rm a85ec1666e25
```
or
```bash
docker container rm MyDocker
```
## Stop a specific container:

```bash
docker container stop container-id or container-name
```

Example:

```bash
docker container stop a85ec1666e25
```
or
```bash
docker container stop MyDocker
```

## Remove all unused containers from your local machine:

```bash
docker container prune
```

## View the history of an image:

```bash
docker image history image-id
```

## Build a custom image:

```bash
docker build -t file-name location
```

Example:

```bash
docker build -t myNewImage .
```

## Run a container with a specific command:

```bash
docker run -it file-name [CMD]
```

Example:

```bash
docker run -it docker1 bash
```

## Run a container in detach mode:

```bash
docker exec -itd container-name [CMD]
```

Example:

```bash
docker exec -itd my-container sh
```

## Run a container with a port mapping:

```bash
docker run -it -p on:from image-name
```

Example:

```bash
docker run -it -p 3000:3001 my-node-app
```
ps: in this case app will run on port 3000 but usally we use same ports for both like ```3001:3001```

## Build again the same image using tag

```bash
docker build -t image-name:tag location
```

Example:

```bash
docker build -t my-node-app:latest .
```

## Automatic Port Mapping

```bash
docker run -it -P image-name
```

Example:

```bash
docker run -it -P my-node-app
```

ps: for using automatic port mapping you need to export ports in Dokerfile with the key word ```EXPOSE``` e.g ```EXPOSE 3000``` and you can port more one ports or range of ports like ```EXPOSE 3000-3005```

## Docker Stats

```bash
docker stats
```
## Tag a image (make a copy with different name)

```bash
docker tag image-name new-tag-name
```

Example:

```bash
docker tag my-node-app meeruzairwashere/my-first-node-app
```
## Push Image to the dockerhub

```bash
docker push image-name
```

Example:

```bash
docker push meeruzairwashere/my-first-node-app
```
ps: before push you need to create the repository with the same name on docker hub

# Docker Network

## Create user defined bridge network

```bash
docker network create bridge-name 
```

Example:

```bash
docker network create meers-bridge
```
## List all networks

```bash
docker network ls -a 
```

## Inspect a network

```bash
docker network inspect network-name
```

Example:

```bash
docker network inspect meers-bridge
```
## remove a network

```bash
docker network rm network-name
```

Example:

```bash
docker network rm meers-bridge
```

## Connect a container to the specific network

```bash
docker network connect network-name container-name
```

Example:

```bash
docker network connect meers-brudge my-container
```

## Disconnect a container to the specific network

```bash
docker network disconnect network-name container-name
```

Example:

```bash
docker network disconnect meers-brudge my-container
```

## Spin a container with specific network and name 

```bash
docker run -itd --network network-name --rm --name container-name
```

Example:

```bash
docker run -itd --network meers-bridge --rm --name my-container
```


# Keywords

- ```-it``` stands for interactive.
- ```-p``` stands for port or port mapping.
- ```-t``` stands for tag.
- ```-d``` stands for `detach.` It tells Docker to run the container in the background, meaning it will start the container and return you to the command prompt without attaching your terminal to the container's output. This is useful for running containers that you don't need to actively monitor.

## Note

Replace `image-name`, `image-id`, `container-id`, `container-name`, `file-name`, and `[CMD]` with your actual values when using the commands.

For more information, refer to the [Docker documentation](https://docs.docker.com/).
