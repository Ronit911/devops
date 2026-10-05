# Dockerfile

A Dockerfile contains instructions used to build a Docker image.

It describes the base image, application files, dependencies, configuration, and command used to start the application.

## Basic Structure

A simplified Dockerfile:

FROM node:24-alpine

WORKDIR /app

COPY package*.json ./

RUN npm install

COPY . .

EXPOSE 3000

CMD ["npm", "start"]

## Important Instructions

### FROM

Defines the base image.

Example:

FROM node:24-alpine

### WORKDIR

Defines the working directory inside the image.

Example:

WORKDIR /app

### COPY

Copies files from the build context into the image.

Example:

COPY package*.json ./

### RUN

Executes a command while building the image.

Example:

RUN npm install

### EXPOSE

Documents the port used by the application.

Example:

EXPOSE 3000

EXPOSE does not by itself publish the port to the host.

### CMD

Defines the default command used when a container starts.

Example:

CMD ["npm", "start"]

## Build Process

A simplified image build process is:

Dockerfile
    |
    v
docker build
    |
    v
Build Context
    |
    v
Docker Image

Example:

docker build -t my-app .

## Running a Container

After building an image:

docker run -d -p 3000:3000 my-app

The port mapping means:

Host Port 3000
    |
    v
Container Port 3000

## Important Principle

A Dockerfile should describe how to build the application environment.

Application configuration that changes between environments should generally be handled separately rather than hard-coded into the image.
