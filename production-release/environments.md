# Deployment Environments

Different environments help separate development work from production systems.

## Common Environments

A typical application may have:

Development
    |
    v
Testing
    |
    v
Staging
    |
    v
Production

Not every project requires all of these environments.

## Development

The development environment is where new functionality is created and tested.

Typical characteristics:

- Frequent changes
- Developer-focused configuration
- Debugging enabled when appropriate
- Experimental changes

## Testing

The testing environment is used to validate application behavior.

Typical activities include:

- Automated tests
- Integration testing
- Regression testing
- Deployment validation

## Staging

Staging can provide an environment that resembles production.

It can be used to validate:

- Deployment procedures
- Configuration
- Infrastructure
- Application behavior

## Production

Production is the environment used by real users.

Production requires greater emphasis on:

- Stability
- Security
- Availability
- Monitoring
- Controlled releases
- Rollback

## Configuration

Different environments often require different configuration.

Examples include:

- API endpoints
- Database connections
- Feature flags
- Domain names
- Secrets
- Resource limits

These values should not normally be hard-coded into application source code.

## Environment Promotion

A controlled release process can look like:

Development
    |
    v
Testing
    |
    v
Staging
    |
    v
Production

The purpose is to detect problems before changes reach production.

## Production Principle

Production should not be treated as simply another development machine.

Changes should be deliberate, traceable, and recoverable.
