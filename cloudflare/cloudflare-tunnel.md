# Cloudflare Tunnel

Cloudflare Tunnel was configured to provide external access to an application running on an Ubuntu Server.

## Why Cloudflare Tunnel?

A traditional deployment may require exposing a server's public IP and opening inbound ports.

Cloudflare Tunnel provides another approach.

The tunnel creates an outbound connection from the server to Cloudflare.

Simplified architecture:

Internet
    |
    v
Cloudflare
    |
    v
Encrypted Tunnel
    |
    v
cloudflared
    |
    v
Ubuntu Server
    |
    v
Application

## cloudflared

The Cloudflare connector used on the server was cloudflared.

The service was configured to run on the Ubuntu Server.

The service could be checked using:

systemctl status cloudflared

## Tunnel

A Cloudflare Tunnel was created for the deployment environment.

The tunnel was associated with a hostname so that requests could be routed to the application running on the Ubuntu server.

Example hostname:

react.ronitwork.bid

## Benefits

Using a tunnel provides several useful characteristics:

- No requirement to expose the application server directly
- Outbound connection from the server
- Cloudflare-managed public entry point
- HTTPS support
- Hostname-based routing

## Operational Model

The server runs the tunnel connector.

The connector maintains communication with Cloudflare.

When a client requests the configured hostname, Cloudflare can route the request through the tunnel to the configured local service.

## Learning Outcome

This provided practical understanding of how a privately hosted application can be made accessible through a cloud networking layer without simply exposing the server directly to inbound internet traffic.
