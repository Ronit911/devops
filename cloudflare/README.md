# Cloudflare

Cloudflare was used to connect the deployed application to a domain and provide secure external access.

The work included DNS configuration, Cloudflare Tunnel, hostname routing, and HTTPS.

## Role of Cloudflare

The application was running on an Ubuntu Server inside a local or private network.

Instead of exposing the server directly to the public internet, Cloudflare can provide an intermediary layer between the user and the application.

Basic architecture:

Client
    |
    v
Cloudflare
    |
    v
Cloudflare Tunnel
    |
    v
Ubuntu Server
    |
    v
Application

## Technologies Used

- Cloudflare DNS
- Cloudflare Tunnel
- Custom domain
- HTTPS / TLS
- Hostname routing

## Learning Objectives

The Cloudflare work was used to understand:

- DNS and domain resolution
- Public versus private network access
- Tunneling
- Secure application exposure
- Hostname-based routing
- HTTPS
- Cloud-based networking

The following documentation covers the individual components.
