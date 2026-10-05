# GitHub Actions Deployment With a Self-Hosted Runner

A self-hosted runner becomes especially useful when GitHub Actions is responsible for deploying an application to a server.

## Basic Workflow

A simplified deployment pipeline is:

Developer
    |
    v
Git Push
    |
    v
GitHub Repository
    |
    v
GitHub Actions
    |
    v
Self-Hosted Runner
    |
    v
Build / Test / Deploy
    |
    v
Application

## Example Workflow

A simplified GitHub Actions workflow could use:

name: Deploy

on:
  push:
    branches:
      - main

jobs:
  deploy:
    runs-on: self-hosted

    steps:
      - name: Checkout
        uses: actions/checkout@v4

      - name: Build
        run: docker build -t my-app .

      - name: Deploy
        run: docker run -d -p 3000:3000 my-app

This is an example architecture rather than a universal production configuration.

## What Happens

When code is pushed to the configured branch:

1. GitHub detects the event.
2. GitHub starts the workflow.
3. The workflow searches for a matching runner.
4. The self-hosted runner receives the job.
5. The runner checks out the repository.
6. Workflow commands execute on the server.
7. The workflow reports the result to GitHub.

## Runner to Application

The runner can execute deployment commands directly on the server.

For example:

GitHub
    |
    v
Runner
    |
    +---- Docker
    |
    +---- Nginx
    |
    +---- Application
    |
    +---- System Services

## Why This Is Useful

This eliminates the need for a separate manual SSH deployment step for every release.

Instead:

Code Change
    |
    v
GitHub
    |
    v
Automated Workflow
    |
    v
Deployment Server

## Important Considerations

A real deployment pipeline should also consider:

- Tests before deployment
- Image versioning
- Existing container cleanup
- Health checks
- Failure handling
- Rollback
- Secrets
- Environment separation
- Deployment logs

## Production Workflow

A more mature workflow can look like:

Pull Request
    |
    v
Code Review
    |
    v
Merge
    |
    v
CI
    |
    +---- Tests
    +---- Build
    +---- Validation
    |
    v
Deployment
    |
    v
Self-Hosted Runner
    |
    v
Production Server

This is the connection between GitHub collaboration, CI/CD, containers, and infrastructure.
