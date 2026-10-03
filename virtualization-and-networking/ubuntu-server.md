# Ubuntu Server Setup

Ubuntu Server was used as the primary Linux environment for practicing DevOps operations.

## Installation

Ubuntu Server was installed as a virtual machine using VirtualBox.

The environment was used for:

- Linux administration
- Application deployment
- Node.js setup
- Git
- PM2
- Cloudflare Tunnel
- Server-side application hosting
- DevOps experimentation

## Server Environment

The Ubuntu Server virtual machine was configured with:

Memory: 8192 MB
Processors: 4
Network: NAT Network

The server received an address from the configured private network.

Example:

Ubuntu Server
    |
    v
enp0s3
    |
    v
192.168.5.x

## Connecting to the Server

SSH was used to access the Linux server remotely.

Example:

ssh username@server-ip

For a locally forwarded SSH port:

ssh -p 2222 username@localhost

## Basic Server Verification

After connecting, useful commands include:

hostname
ip addr
ip route
df -h
free -h
uname -a

These commands provide information about the server identity, network configuration, storage, memory, and operating system.

## Role in the DevOps Lab

The Ubuntu Server became the environment where application deployment and infrastructure tools could be tested.

The later deployment workflow involved:

Developer
    |
    v
GitHub
    |
    v
Application
    |
    v
Ubuntu Server
    |
    +---- Node.js
    +---- PM2
    +---- Cloudflare Tunnel
    +---- Nginx
    +---- Docker

This provided a practical Linux environment for connecting multiple DevOps technologies together.
