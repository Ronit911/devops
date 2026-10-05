# Continuous Integration Pipeline

Continuous Integration focuses on automatically validating changes as they are introduced.

## Basic CI Flow

Developer
    |
    v
Push / Pull Request
    |
    v
GitHub Actions
    |
    v
Checkout Code
    |
    v
Install Dependencies
    |
    v
Build / Test
    |
    v
Status Check
    |
    v
Pull Request Decision

## Example Validation Steps

A web application CI pipeline may perform:

1. Checkout repository
2. Install runtime
3. Install dependencies
4. Run linting
5. Run tests
6. Build the application

## Why CI?

Without CI, developers may discover integration problems only after code is merged.

CI moves those checks earlier in the development lifecycle.

## CI vs CD

Continuous Integration:

Code
    |
    v
Build / Test / Validate

Continuous Delivery or Deployment:

Validated Code
    |
    v
Package
    |
    v
Deploy
    |
    v
Environment

CI answers:

"Does this change work?"

CD answers:

"Can this validated change be delivered to an environment?"

These concepts were later combined with Docker and self-hosted runners for deployment workflows.
