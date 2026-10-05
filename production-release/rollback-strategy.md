# Rollback Strategy

A rollback is the process of returning an application to a previously known working version.

Rollback is an important part of production deployment because deployments can fail even when CI checks pass.

## Why Rollbacks Matter

A deployment can fail because of:

- Application bugs
- Configuration problems
- Dependency issues
- Infrastructure problems
- Unexpected production behavior

A recovery strategy should therefore exist before a production release.

## Versioned Deployments

A useful approach is to deploy identifiable versions.

For example:

v1.2.0
v1.2.1
v1.3.0

If version v1.3.0 introduces a critical problem, the deployment can potentially return to v1.2.1.

## Docker and Rollback

Container images make versioned deployments practical.

Example:

my-app:v1.2.1
my-app:v1.3.0

Instead of relying only on a generic latest tag, a deployment can identify the exact image version.

## Simplified Rollback

Current:

Production
    |
    v
my-app:v1.3.0

After rollback:

Production
    |
    v
my-app:v1.2.1

The exact commands depend on the deployment architecture.

## Rollback Process

A controlled rollback can follow:

1. Detect the problem.
2. Confirm the affected version.
3. Stop or replace the problematic deployment.
4. Deploy the previous known-good version.
5. Verify application health.
6. Investigate the failed release.
7. Document the incident.

## Database Considerations

Application rollback does not automatically mean database rollback.

Database changes can be difficult or dangerous to reverse.

Database migrations should therefore be designed carefully, especially when multiple application versions may need to coexist.

## Production Principle

A deployment is not complete unless there is a reasonable recovery strategy.

The goal is not to prevent every failure.

The goal is to make failures recoverable.
