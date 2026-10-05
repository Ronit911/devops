# Deployment Architecture

A production deployment consists of multiple components working together.

A simplified architecture for the technologies studied in this repository is:

Users
    |
    v
Cloudflare
    |
    v
Nginx
    |
    v
Application / Docker Container
    |
    v
Server

The deployment automation can be added to this architecture:

Developer
    |
    v
GitHub
    |
    v
GitHub Actions
    |
    v
Self-Hosted Runner
    |
    v
Docker
    |
    v
Application
    |
    v
Nginx
    |
    v
Cloudflare
    |
    v
Users

## Component Responsibilities

### GitHub

Stores source code and manages collaboration.

### GitHub Actions

Automates CI/CD workflows.

### Self-Hosted Runner

Provides the machine where selected workflow jobs execute.

### Docker

Packages applications into reproducible container images.

### Nginx

Acts as a web server and reverse proxy.

### Cloudflare

Can provide DNS, TLS-related services, traffic protection, and connectivity features depending on the deployment architecture.

### Server

Provides the compute environment where applications and infrastructure services run.

## Important Principle

Each component has a specific responsibility.

A production system becomes easier to understand and troubleshoot when these responsibilities are clearly separated.
