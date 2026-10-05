# GitHub Actions

GitHub Actions was used to understand automated CI/CD workflows.

## What GitHub Actions Does

GitHub Actions allows workflows to run automatically in response to repository events.

Examples include:

- Pushes
- Pull requests
- Manual triggers
- Scheduled events
- Release events

## Workflow Structure

A workflow is normally stored under:

.github/workflows/

A basic workflow contains:

- Trigger
- Jobs
- Runner
- Steps

Conceptually:

GitHub Event
    |
    v
Workflow
    |
    v
Job
    |
    v
Runner
    |
    v
Steps
    |
    v
Result

## Example Structure

name: CI

on:
  pull_request:
  push:

jobs:
  build:
    runs-on: ubuntu-latest

    steps:
      - uses: actions/checkout@v4

      - name: Install dependencies
        run: npm install

      - name: Build
        run: npm run build

## Self-Hosted Runners

GitHub Actions can use GitHub-hosted runners or self-hosted runners.

A self-hosted runner executes jobs on infrastructure controlled by the user or organization.

This becomes useful when workflows need:

- Private network access
- Custom software
- Specialized infrastructure
- Direct access to deployment servers

The self-hosted runner work is documented separately in this repository.
