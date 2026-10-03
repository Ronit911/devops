# DNS Configuration

DNS translates domain names into information that allows clients to locate services.

For the deployment environment, a domain was connected to Cloudflare and used as the public entry point for the application.

## Domain

A domain was configured through Cloudflare.

The application hostname used during the lab included:

react.ronitwork.bid

The hostname was associated with the application through Cloudflare infrastructure.

## DNS Concept

A simplified request flow is:

User
    |
    v
react.ronitwork.bid
    |
    v
DNS Resolution
    |
    v
Cloudflare
    |
    v
Application

## Why DNS?

Users generally access applications using domain names instead of remembering IP addresses.

DNS provides the mapping between human-readable names and network destinations.

## Cloudflare DNS

Cloudflare can act as the authoritative DNS provider for a domain.

This provides a central location for managing:

- DNS records
- Hostnames
- Cloudflare services
- Application routing

## Important Concept

DNS resolution and application traffic are related but are not the same thing.

DNS answers:

"Where should this hostname resolve or route?"

The application layer answers:

"What should happen when the user reaches the service?"

Cloudflare Tunnel can be used to connect these two parts without requiring direct inbound access to the private server.
