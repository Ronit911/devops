# Nginx Reverse Proxy

A reverse proxy is a server that receives requests from clients and forwards those requests to backend services.

Nginx is commonly used as a reverse proxy.

## Direct Application Access

Without a reverse proxy, a user might access an application directly:

Browser
    |
    v
Server:3000
    |
    v
Application

This can expose the application's internal port directly.

## Reverse Proxy Architecture

With Nginx:

Browser
    |
    v
Nginx :443
    |
    v
Application :3000

The user communicates with Nginx while Nginx communicates with the backend application.

## Why Use a Reverse Proxy

A reverse proxy provides a central entry point for applications.

It can:

- Hide internal application ports
- Handle HTTPS
- Route requests
- Serve static content
- Add security controls
- Host multiple applications
- Provide a consistent public endpoint

## Basic Configuration

A simplified Nginx server block can look like:

server {
    listen 80;
    server_name example.com;

    location / {
        proxy_pass http://127.0.0.1:3000;

        proxy_set_header Host $host;
        proxy_set_header X-Real-IP $remote_addr;
        proxy_set_header X-Forwarded-For $proxy_add_x_forwarded_for;
        proxy_set_header X-Forwarded-Proto $scheme;
    }
}

The exact configuration depends on the application and environment.

## Request Flow

A request to:

https://example.com

can follow this path:

Client
    |
    v
Nginx
    |
    v
127.0.0.1:3000
    |
    v
Application

## Nginx and Docker

Nginx can also proxy traffic to a Docker container.

Example:

Internet
    |
    v
Nginx :443
    |
    v
Docker Container :3000

This allows the application container to remain behind the reverse proxy.

## Important Concept

Nginx does not have to run the application itself.

Its role can be to receive and route requests to the application process.
