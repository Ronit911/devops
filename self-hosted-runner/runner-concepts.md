# Self-Hosted Runner Concepts

A GitHub Actions runner is the machine that executes workflow jobs.

There are two broad categories:

- GitHub-hosted runners
- Self-hosted runners

## GitHub-Hosted Runner

With a GitHub-hosted runner, GitHub provides the execution environment.

The workflow requests a runner such as:

ubuntu-latest

GitHub creates or allocates the environment and executes the workflow.

Simplified model:

GitHub
    |
    v
GitHub-Hosted Runner
    |
    v
Workflow Job

## Self-Hosted Runner

With a self-hosted runner, the user provides the machine.

The machine runs GitHub's runner software and waits for jobs.

Simplified model:

GitHub
    |
    v
Self-Hosted Runner
    |
    v
User-Controlled Server

## Why Use One

Self-hosted runners can be useful when:

- Deployment must happen on a specific server
- Custom software is required
- Private network access is required
- Internal infrastructure must be accessed
- More control over the environment is required

## Runner Labels

Runners can have labels that allow workflows to select appropriate machines.

For example:

self-hosted
linux
x64

A workflow can request:

runs-on: self-hosted

or use more specific labels when multiple runners exist.

## Runner Communication

The runner normally establishes outbound communication with GitHub.

A simplified model is:

Server
    |
    | Outbound connection
    v
GitHub
    |
    | Job instructions
    v
Runner
    |
    v
Workflow execution

The exact communication mechanism is handled by the GitHub Actions runner software.

## Important Distinction

The runner is not the same thing as GitHub Actions.

GitHub Actions is the automation platform.

The runner is the execution environment where a workflow job actually runs.

## Deployment Example

A deployment workflow could follow:

Developer
    |
    v
Push to GitHub
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
