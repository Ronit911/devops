# Application Deployment

This section documents the process of deploying a web application on a Linux server.

The deployment work involved a React application running on an Ubuntu Server virtual machine.

## Deployment Environment

The basic environment was:

- Ubuntu Server
- Node.js
- npm
- Git
- React
- PM2

The application source code was maintained in GitHub and deployed to the Ubuntu server for testing and hosting.

## Deployment Flow

Developer
    |
    v
GitHub Repository
    |
    v
Ubuntu Server
    |
    +---- Node.js
    |
    +---- React Application
    |
    +---- PM2
    |
    v
Running Application

## Objectives

The deployment process was used to understand:

- How applications are hosted on Linux servers
- How Node.js applications are executed
- How source code is transferred to a server
- How processes are managed
- How an application can remain running after an SSH session ends

The following files document the individual components of this deployment process.
