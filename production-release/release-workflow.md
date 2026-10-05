# Release Workflow

A release workflow defines how a change moves from development into production.

## Basic Workflow

A simplified release process is:

Developer
    |
    v
Feature / Change
    |
    v
Git Commit
    |
    v
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
    v
Build
    |
    v
Deployment
    |
    v
Production

## Continuous Integration

CI validates changes automatically.

Typical CI activities include:

- Installing dependencies
- Running tests
- Building the application
- Linting
- Static analysis
- Building Docker images

## Continuous Deployment

Continuous deployment can automatically deploy changes after successful validation.

A simplified pipeline is:

Code
    |
    v
Build
    |
    v
Test
    |
    v
Package
    |
    v
Deploy
    |
    v
Verify

## Release Version

Releases should be identifiable.

For example:

v1.0.0
v1.1.0
v1.1.1

Versioning makes it easier to determine which version is currently deployed and which version should be restored during a rollback.

## Deployment Verification

A deployment should not end simply because the deployment command succeeded.

The application should be checked after deployment.

Examples:

- HTTP response
- Application health
- Logs
- Container status
- Nginx status
- Important application functionality

## Release Principle

A good release process should be:

Repeatable
    +
Traceable
    +
Tested
    +
Recoverable

The objective is to make deployments predictable rather than dependent on manual steps.
