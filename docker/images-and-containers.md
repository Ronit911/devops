# Images and Containers

Docker images and containers are two of the most important concepts in Docker.

## Docker Image

An image is a read-only package containing the files and configuration required to create a container.

Images can contain:

- Application code
- Runtime
- System libraries
- Dependencies
- Configuration required by the application

## Docker Container

A container is a running instance of an image.

For example:

Docker Image
    |
    +---- Container A
    +---- Container B
    +---- Container C

The same image can be used to create multiple containers.

## Common Image Commands

List images:

docker images

Build an image:

docker build -t my-app .

Remove an image:

docker rmi my-app

## Common Container Commands

Run a container:

docker run -d --name my-app my-app

List running containers:

docker ps

List all containers:

docker ps -a

Stop a container:

docker stop my-app

Start a stopped container:

docker start my-app

Restart a container:

docker restart my-app

Remove a container:

docker rm my-app

## Logs

Container logs can be viewed with:

docker logs my-app

Follow logs continuously:

docker logs -f my-app

This is useful when diagnosing application startup or runtime problems.

## Inspecting Containers

Container configuration can be inspected using:

docker inspect my-app

This can help investigate:

- Network configuration
- Port mappings
- Mounts
- Environment variables
- Container state

## Container Lifecycle

A simplified lifecycle is:

Image
    |
    v
docker run
    |
    v
Created
    |
    v
Running
    |
    v
Stopped
    |
    v
Removed

Understanding this lifecycle is important when troubleshooting containerized applications.
