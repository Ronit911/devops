# Self-Hosted GitHub Actions Runner

This section documents my learning and hands-on work with GitHub Actions self-hosted runners.

A self-hosted runner allows GitHub Actions workflows to execute jobs on infrastructure controlled by the repository owner instead of using GitHub-hosted runner infrastructure.

This becomes useful when a deployment workflow needs access to a specific server, private network, local resources, or custom software.

## Topics

- Self-hosted runner concepts
- Runner architecture
- Runner installation
- Runner services
- Runner users and permissions
- GitHub Actions deployment
- Security considerations
- Troubleshooting

## Why Self-Hosted Runners

GitHub-hosted runners provide temporary managed environments.

A self-hosted runner runs on infrastructure that the organization controls.

Simplified architecture:

GitHub
    |
    | Job
    v
GitHub Actions
    |
    v
Self-Hosted Runner
    |
    v
Deployment Server
    |
    v
Application

## Hands-On Context

As part of my DevOps learning, I worked with a Linux server and configured a GitHub Actions self-hosted runner for deployment workflows.

The runner was intended to allow GitHub Actions jobs to execute directly on the deployment server.

## Learning Progression

GitHub Repository
    |
    v
GitHub Actions Workflow
    |
    v
Runner Selection
    |
    v
Self-Hosted Runner
    |
    v
Deployment Commands
    |
    v
Application

## Related Areas

The runner connects directly with:

- GitHub Actions
- CI/CD
- Docker
- Nginx
- Production deployment

The goal is to understand how source code changes can move from GitHub into a real deployment environment through an automated workflow.
