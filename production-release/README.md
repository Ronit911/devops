# Production & Release Engineering

This section documents the production and release engineering concepts that connect the infrastructure and deployment topics covered throughout this repository.

The goal is to understand how an application moves from source code to a controlled production deployment.

## Topics

- Deployment architecture
- Development and production environments
- Release workflows
- Versioning
- Rollback strategies
- Production deployment checklist
- Deployment troubleshooting

## Overall DevOps Flow

The repository can be viewed as a progression:

Infrastructure
    |
    v
Application
    |
    v
Git
    |
    v
CI/CD
    |
    v
Docker
    |
    v
Nginx
    |
    v
Self-Hosted Runner
    |
    v
Production Deployment

## Production Engineering

Production engineering is not simply running an application on a server.

It also involves:

- Reliability
- Repeatable deployments
- Monitoring
- Security
- Version control
- Rollback
- Configuration management
- Failure handling

## Goal

The goal of this section is to understand how the individual tools documented in this repository work together as a complete deployment system.
