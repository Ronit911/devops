# Self-Hosted Runner Security

A self-hosted runner is powerful because workflow jobs can execute commands on the machine.

That also makes runner security extremely important.

## Trust Model

A workflow executed on a self-hosted runner can potentially interact with the runner's environment.

Therefore:

GitHub Repository
    |
    v
Workflow
    |
    v
Runner
    |
    v
Server Resources

The runner should be treated as infrastructure that can execute code.

## Dedicated User

A useful security practice is to run the runner under a dedicated non-root user.

For example:

ghrunner

The purpose is to avoid giving normal workflow jobs unrestricted root privileges.

Instead of:

Workflow
    |
    v
root

Prefer:

Workflow
    |
    v
Dedicated Runner User
    |
    v
Limited Permissions

## Why Avoid Root

Running CI/CD jobs as root can increase the impact of a compromised or malicious workflow.

A dedicated user provides a better security boundary.

## Sudo Permissions

Some deployment workflows require elevated privileges.

Instead of giving unrestricted sudo access, permissions should be limited to the commands that are actually required.

For example, a deployment may need controlled access to:

- Docker
- system services
- Nginx
- Application directories

The exact sudo policy depends on the infrastructure.

## Secrets

Sensitive information should not be committed to the repository.

Examples include:

- SSH private keys
- API tokens
- Cloud credentials
- Passwords
- Database credentials
- Deployment secrets

GitHub Actions secrets or an appropriate secrets-management system should be used instead.

## Runner Isolation

Important considerations include:

- Use a dedicated server where practical
- Keep the operating system updated
- Limit user permissions
- Protect SSH access
- Avoid unnecessary services
- Review workflow changes
- Restrict sudo privileges
- Protect secrets
- Monitor runner activity

## Repository Trust

Self-hosted runners should be used carefully with workflows from untrusted code.

Pull requests from unknown contributors can potentially execute workflow code.

Repository permissions and workflow design should therefore be considered before allowing untrusted workflows to run on a production runner.

## Production Principle

A self-hosted runner should be treated as part of the deployment infrastructure, not simply as another GitHub setting.
