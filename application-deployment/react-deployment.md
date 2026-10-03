# React Application Deployment

A React application was deployed to an Ubuntu Server environment as part of the DevOps learning process.

## Application

A simple React application was created and maintained in a GitHub repository.

The application was deployed to the Ubuntu server and made accessible through the server environment.

## Deployment Process

The basic workflow was:

Developer
    |
    v
GitHub Repository
    |
    v
Clone / Pull Repository
    |
    v
Install Dependencies
    |
    v
Build Application
    |
    v
Run Application
    |
    v
PM2

## Node.js Environment

The server environment included Node.js and npm.

Versions used during the setup included:

Node.js: v22.22.0
npm: v9.2.0

The versions can be verified with:

node -v
npm -v

## Installing Dependencies

After obtaining the application source code, dependencies can be installed with:

npm install

For a production build:

npm run build

The exact commands depend on the application and its package configuration.

## Deployment Concept

The important concept is that the server needs both the application source/build and an execution environment capable of serving it.

For a Node.js-based application:

Application
    |
    v
Node.js Runtime
    |
    v
Listening Port
    |
    v
Client Request

This deployment formed the foundation for later work involving PM2, Cloudflare Tunnel, Nginx, Docker, and CI/CD.
