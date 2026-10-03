# Application Deployment Troubleshooting

Application deployment often involves problems at multiple layers.

The troubleshooting process was used to understand where failures occur instead of treating the application as a single component.

## Layer 1: Application

Check whether the application itself works.

Useful checks include:

- Application logs
- Build output
- Dependency installation
- Package configuration
- Runtime errors

## Layer 2: Node.js

Check the runtime:

node -v
npm -v

Verify that dependencies are installed:

npm install

Check the application build:

npm run build

## Layer 3: Process Management

Check PM2:

pm2 status

View application logs:

pm2 logs react-app

Restart the process if required:

pm2 restart react-app

## Layer 4: Network

Check whether the application is listening on the expected port.

Useful commands include:

ss -tulpn

and:

curl http://localhost:<port>

## Layer 5: External Access

If the application works locally but cannot be accessed externally, investigate:

- Firewall rules
- Port exposure
- Cloudflare configuration
- Tunnel configuration
- Reverse proxy configuration
- DNS configuration

## Troubleshooting Principle

A useful approach is to troubleshoot from the inside out:

Application
    ?
Runtime
    ?
Process
    ?
Port
    ?
Server
    ?
Network
    ?
Cloud / DNS

This makes it easier to identify which layer is causing the problem.
