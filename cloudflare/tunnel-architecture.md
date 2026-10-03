# Tunnel Architecture

The Cloudflare deployment can be represented as a layered architecture.

## Architecture

Client
    |
    | HTTPS
    v
Cloudflare Edge
    |
    | Tunnel
    v
cloudflared
    |
    v
Ubuntu Server
    |
    v
Application

## Local Service

The Cloudflare Tunnel does not necessarily need the application itself to listen on a public IP.

Instead, the tunnel connector can forward traffic to a service available locally on the server.

Conceptually:

Cloudflare
    |
    v
Tunnel
    |
    v
localhost:<application-port>
    |
    v
Application

## Hostname Routing

A hostname can be associated with a particular tunnel route.

For example:

react.ronitwork.bid
        |
        v
Cloudflare Tunnel
        |
        v
Ubuntu application

This allows multiple hostnames or services to be handled through a controlled routing configuration.

## Why This Matters

The architecture demonstrates an important DevOps concept:

The application does not need to be directly responsible for public internet exposure.

Different layers can handle different responsibilities:

Cloudflare
    ? Public access and edge networking

Tunnel
    ? Secure connection to the server

Ubuntu
    ? Host infrastructure

PM2 / Application
    ? Application process

This separation makes the deployment architecture easier to reason about and extend.
