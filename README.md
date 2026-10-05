# DevOps

A hands-on record of my journey into DevOps, infrastructure, cloud networking, application deployment, CI/CD, containerization, and release engineering.

This repository documents the concepts I learn, the systems I configure, the applications I deploy, and the practical problems I solve while building my DevOps skills.

---

## What I'm Learning

### Infrastructure & Networking

- Windows Server
- Ubuntu Server
- Virtualization and Type 2 hypervisors
- NAT networking
- Static IP configuration
- Network routing and connectivity
- Linux server administration

### Application Deployment

- Node.js
- React
- Linux-based application hosting
- Static application deployment
- Process management with PM2
- Remote server deployment

### Cloud & Networking

- Domains and DNS
- Cloudflare
- Cloudflare Tunnel
- HTTPS and TLS
- Reverse proxy concepts
- Secure application access

### Git & CI/CD

- Git
- GitHub
- GitHub Actions
- Continuous Integration
- Continuous Deployment
- Pull request workflows
- Self-hosted GitHub Actions runners
- Automated application deployment workflows

### Containers & Web Infrastructure

- Docker
- Dockerfiles
- Docker images and containers
- Multi-stage builds
- Container-based application deployment
- Nginx
- Reverse proxies
- Multi-application hosting

### Production & Release Engineering

- Branching strategies
- Pull requests
- Required CI checks
- Versioning
- Development, staging, and production environments
- Container registries
- Release workflows
- Deployment architecture

---

## Learning Progression

The learning path in this repository is gradually moving from individual infrastructure components toward complete application delivery workflows.

```text
Servers & Infrastructure
        ↓
Virtualization & Networking
        ↓
Application Deployment
        ↓
Process Management
        ↓
Domain & Cloudflare
        ↓
Git & GitHub
        ↓
GitHub Actions & CI/CD
        ↓
Docker
        ↓
Nginx & Reverse Proxy
        ↓
Self-Hosted Runners
        ↓
Remote Deployment
        ↓
Production Deployment Concepts
        ↓
Environments & Release Engineering
```

---

## Hands-On Work

The repository contains practical documentation and implementation work across the different stages of the learning path.

Examples include:

- Setting up Windows Server and Ubuntu Server virtual machines
- Configuring VirtualBox networking and static IP addresses
- Deploying a React application on Ubuntu
- Managing applications with PM2
- Connecting domains and configuring DNS through Cloudflare
- Setting up Cloudflare Tunnel
- Working with CI/CD pipelines using GitHub Actions
- Working with self-hosted GitHub Actions runners
- Containerizing applications with Docker
- Configuring Nginx as a reverse proxy
- Deploying applications to remote Linux servers
- Working with HTTPS and TLS
- Designing production-oriented deployment and release workflows

Each topic contains a combination of hands-on implementation notes, commands, configuration examples, architecture explanations, troubleshooting steps, and lessons learned.

---

## Hands-On Projects

### 1. Linux Application Deployment Lab

- Created and configured an Ubuntu Server environment
- Configured VirtualBox networking
- Deployed a React application
- Installed and used Node.js and npm
- Managed the application using PM2
- Troubleshot application, process, and network issues

### 2. Cloudflare Application Access

- Connected a domain through Cloudflare
- Configured DNS
- Installed and configured cloudflared
- Created a Cloudflare Tunnel
- Routed a hostname to the application running on the server
- Verified tunnel and service status

### 3. GitHub CI/CD & Self-Hosted Runner

- Worked with Git and GitHub workflows
- Used branches and pull requests
- Configured branch protection and required reviews
- Worked with GitHub Actions
- Configured a Linux self-hosted GitHub Actions runner
- Investigated runner processes, services, permissions, and connectivity

### 4. Containerized Deployment

- Studied Docker images, containers, and Dockerfiles
- Worked with multi-stage Docker builds
- Documented containerized deployment architecture
- Connected Docker with CI/CD and reverse-proxy concepts

### 5. Nginx & Production Concepts

- Learned Nginx reverse proxy configuration
- Worked with HTTP/HTTPS and TLS concepts
- Documented multi-application routing
- Studied production deployment, rollback, environments, and troubleshooting

---

## Repository Structure

```text
devops/
│
├── server-and-microsoft-365/
├── virtualization-and-networking/
├── application-deployment/
├── cloudflare/
├── github-and-cicd/
├── docker/
├── nginx/
├── self-hosted-runner/
└── production-release/
```

Each directory represents a stage or area of the DevOps learning process.

The documentation is organized around practical implementation rather than only theoretical concepts.

---

## Approach

I am following a hands-on approach to learning DevOps.

For each technology or workflow, I aim to:

1. Understand the underlying concept
2. Configure and work with the technology
3. Build or deploy something practical
4. Troubleshoot issues encountered during implementation
5. Document the commands and configuration involved
6. Understand why each component is required
7. Connect individual technologies into a complete workflow

The goal is to understand not only **how to use a tool**, but also **why it is used and how it fits into the larger deployment system**.

---

## Current Learning Focus

My current focus is connecting the individual DevOps components documented in this repository into complete deployment workflows involving:

- Git and GitHub workflows
- Pull requests and CI checks
- GitHub Actions
- Self-hosted runners
- Docker-based deployments
- Nginx reverse proxy
- Cloudflare
- Remote Linux servers
- Application versioning
- Release workflows

The goal is to progressively move from individual tool usage toward reproducible and automated application delivery.

---

## Implementation vs Learning

This repository contains both hands-on implementation work and structured learning documentation.

### Hands-On Work

- VirtualBox server environments
- Ubuntu Server configuration
- Windows Server setup
- Linux networking
- React application deployment
- PM2 process management
- Cloudflare DNS
- Cloudflare Tunnel
- Git/GitHub workflows
- GitHub Actions workflows
- Self-hosted GitHub Actions runner
- Nginx configuration and reverse-proxy concepts

### Learning / Reference

- Docker fundamentals and container lifecycle
- Multi-stage Docker builds
- Container registries
- Production environment strategies
- Release engineering
- Rollback strategies
- Production deployment patterns
- Advanced CI/CD architecture

The distinction is intentional: some sections document systems I have configured hands-on, while others document concepts and practices I am currently learning and working toward implementing.

---

## Goal

The goal of this repository is to build a strong practical understanding of DevOps by progressively moving from infrastructure fundamentals toward automated, containerized, and production-oriented application delivery.

Rather than treating each technology as an isolated tool, I am focusing on understanding how infrastructure, source control, CI/CD, containers, networking, reverse proxies, security, and release processes fit together into a complete software delivery workflow.
