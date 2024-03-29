# - Docker Cheat Sheet



## Pulling an image

Pull an image from Docker Hub:

```bash
docker pull image-name
```

Example:

```bash
docker pull ubuntu
```

## Running Containers

Run an image as a container:

```bash
docker run -it image-name
```

Example:

```bash
docker run -it ubuntu
```

## Managing Images

List all images on your local machine:

```bash
docker images
```
or
```bash
docker image ls
```

Remove an image from your local machine:

```bash
docker image rm image-id
```

Inspect metadata about a specific image:

```bash
docker image inspect image-id
```

Remove all unused images from your local machine:

```bash
docker image prune -a
```

## Managing Containers

Remove a specific container:

```bash
docker container rm container-id or container-name
```

Example:

```bash
docker container rm a85ec1666e25
```

```bash
docker container rm MyDocker
```

Remove all unused containers from your local machine:

```bash
docker container prune
```

## Additional Commands

View the history of an image:

```bash
docker image history image-id
```

Build a custom image:

```bash
docker build -t file-name location
```

Example:

```bash
docker build -t myNewImage .
```

Run a container with a specific command:

```bash
docker run -it file-name [CMD]
```

Example:

```bash
docker run -it docker1 bash
```

## Note

Replace `image-name`, `image-id`, `container-id`, `container-name`, `file-name`, and `[CMD]` with your actual values when using the commands.

For more information, refer to the [Docker documentation](https://docs.docker.com/).
