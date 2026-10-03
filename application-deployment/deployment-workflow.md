# Application Deployment Workflow

The deployment process connected several individual tools into one workflow.

## Development

Application development starts on the developer machine.

Developer
    |
    v
Git
    |
    v
GitHub

The source code is stored in a GitHub repository so that it can be version controlled and accessed from the deployment server.

## Server Deployment

The application can then be obtained on the Ubuntu server.

GitHub
    |
    v
Ubuntu Server
    |
    v
Application Dependencies
    |
    v
Application Build
    |
    v
PM2
    |
    v
Running Application

## Process Management

PM2 manages the application process and provides commands for:

- Starting
- Stopping
- Restarting
- Monitoring
- Logging

## External Access

The deployment was later connected with Cloudflare infrastructure.

The broader architecture became:

Client
    |
    v
Cloudflare
    |
    v
Tunnel / Network Layer
    |
    v
Ubuntu Server
    |
    v
Application
    |
    v
PM2

This demonstrated how application deployment, process management, networking, and cloud services can work together.

## Learning Outcome

The deployment provided practical exposure to the difference between:

- Developing an application
- Running an application
- Managing an application process
- Exposing an application to users
- Automating the deployment process

These concepts become important when moving from manual deployment toward CI/CD.
