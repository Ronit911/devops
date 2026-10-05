# Docker Fundamentals

Docker is a platform used to build, package, distribute, and run applications using containers.

## Containers

A container is an isolated runtime environment for an application.

Instead of installing every dependency directly on the host operating system, the application and its required environment can be packaged into an image and started as a container.

## Image vs Container

A Docker image is a packaged template.

A container is a running instance created from an image.

The relationship is:

Dockerfile
    |
    v
Docker Image
    |
    v
Docker Container

Multiple containers can be created from the same image.

## Docker Engine

Docker Engine provides the components required to build images and run containers.

Simplified architecture:

Developer
    |
    v
Docker CLI
    |
    v
Docker Engine
    |
    +---- Images
    +---- Containers
    +---- Networks
    +---- Volumes

## Common Commands

Check the Docker installation:

docker --version

Show Docker information:

docker info

List local images:

docker images

List running containers:

docker ps

List all containers:

docker ps -a

## Why Containers Matter

Containers help reduce differences between environments.

For example:

Developer Machine
    |
    v
Docker Image
    |
    v
Testing Environment
    |
    v
Docker Image
    |
    v
Production Environment

Using the same image across environments can make deployments more predictable.

## Docker vs Virtual Machines

A virtual machine includes a complete guest operating system.

Containers generally share the host operating system kernel while isolating application processes.

Simplified comparison:

Virtual Machine

Host OS
    |
    v
Hypervisor
    |
    v
Guest OS
    |
    v
Application


Container

Host OS
    |
    v
Container Runtime
    |
    v
Container
    |
    v
Application

Containers are generally lighter than full virtual machines.
