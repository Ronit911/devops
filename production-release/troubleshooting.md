# Production Deployment Troubleshooting

Production troubleshooting should be systematic.

A deployment contains multiple layers, so the investigation should move from the highest-level symptom toward the underlying component.

## Layer 1: GitHub Actions

Check:

- Did the workflow start?
- Did the correct branch trigger it?
- Did CI pass?
- Did the deployment job run?
- Did the runner accept the job?

## Layer 2: Self-Hosted Runner

Check:

- Is the runner online?
- Is the runner service running?
- Does the runner user have the required permissions?
- Did the deployment commands execute?

Useful Linux checks can include:

sudo systemctl status <runner-service>

ps -ef | grep '[R]unner.Listener'

## Layer 3: Docker

If Docker is involved, check:

docker ps

docker ps -a

docker images

docker logs <container>

Look for:

- Container crashes
- Missing environment variables
- Port conflicts
- Image problems
- Application startup failures

## Layer 4: Application

Check whether the application itself is healthy.

Test the backend directly where appropriate.

For example:

curl http://127.0.0.1:3000

If the backend works directly but the public website does not, the problem may be further up the stack.

## Layer 5: Nginx

Check:

sudo nginx -t

sudo systemctl status nginx

Review:

/var/log/nginx/access.log

/var/log/nginx/error.log

## Layer 6: Cloudflare / DNS

If the server works locally but the public hostname does not, investigate:

- DNS records
- Cloudflare configuration
- TLS settings
- Tunnel configuration when applicable
- Origin connectivity

## Layer 7: External Access

Finally test the public endpoint.

The troubleshooting path becomes:

GitHub Actions
    |
    v
Runner
    |
    v
Docker
    |
    v
Application
    |
    v
Nginx
    |
    v
Cloudflare
    |
    v
Internet

## Troubleshooting Principle

Do not change several components simultaneously.

Isolate the layer where the failure occurs first.

This makes production incidents easier to diagnose and reduces the risk of introducing additional problems while troubleshooting.
