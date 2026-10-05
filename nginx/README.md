# Nginx

This section documents my learning and hands-on understanding of Nginx as a web server and reverse proxy.

Nginx is an important part of a production-style deployment architecture because it can sit between users and application services.

## Topics

- Nginx fundamentals
- Reverse proxy
- Nginx configuration
- HTTPS and TLS
- Multiple application hosting
- Nginx with Docker
- Nginx with Cloudflare

## Role in a Deployment

A simplified architecture is:

Internet
    |
    v
Cloudflare
    |
    v
Nginx
    |
    +---- Application
    |
    +---- Docker Container
    |
    +---- Other Services

Nginx can receive incoming HTTP/HTTPS requests and forward them to the appropriate backend service.

## Why Nginx

Nginx can provide:

- Reverse proxying
- HTTP/HTTPS handling
- Static file serving
- Load balancing
- Request routing
- Connection management
- Security-related controls

## Learning Progression

Application
    |
    v
Application Server
    |
    v
Nginx Reverse Proxy
    |
    v
HTTPS
    |
    v
Cloudflare
    |
    v
Users

The objective is to understand how Nginx fits into a larger production deployment rather than treating it as an isolated web server.
