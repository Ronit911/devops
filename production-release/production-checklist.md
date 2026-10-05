# Production Deployment Checklist

A deployment checklist helps reduce mistakes during production releases.

## Before Deployment

Check:

- Code has been reviewed
- Pull request requirements are satisfied
- CI checks are passing
- Correct branch is being deployed
- Correct version has been identified
- Required configuration is available
- Secrets are available through secure mechanisms
- Required infrastructure is healthy

## Build

Verify:

- Dependencies install correctly
- Tests pass
- Application builds successfully
- Docker image builds successfully when applicable
- Image is appropriately tagged

## Deployment

Verify:

- Deployment server is reachable
- Self-hosted runner is online when required
- Required services are running
- Docker is available
- Nginx configuration is valid
- Correct application version is deployed

## After Deployment

Check:

- Application responds correctly
- HTTP/HTTPS access works
- Docker containers are healthy
- Nginx is running
- Logs do not show critical errors
- Important application functionality works

## Rollback Readiness

Before a production release, know:

- What version is currently running
- What version is being deployed
- Which previous version can be restored
- How the rollback will be performed

## Security

Verify:

- No secrets are committed
- SSH access is appropriately protected
- Runner permissions are appropriate
- Production services are not unnecessarily exposed
- TLS is configured correctly where required

## Documentation

Record:

- Version deployed
- Date of deployment
- Important configuration changes
- Known issues
- Rollback information

## Final Principle

A checklist does not replace engineering judgment.

It provides a repeatable baseline that reduces avoidable mistakes.
