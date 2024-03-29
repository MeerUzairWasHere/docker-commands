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

# Keywords

- ```-it``` stands for interactive.
- ```-p``` stands for port or port mapping.
- ```-t``` stands for tag.

## Note

Replace `image-name`, `image-id`, `container-id`, `container-name`, `file-name`, and `[CMD]` with your actual values when using the commands.

For more information, refer to the [Docker documentation](https://docs.docker.com/).
