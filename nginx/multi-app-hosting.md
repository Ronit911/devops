# Multi-Application Hosting

One advantage of using Nginx as a reverse proxy is that a single server can route traffic to multiple applications.

## Example Architecture

Suppose a server runs:

Application A on port 3000

Application B on port 4000

Application C on port 5000

Nginx can expose them through different hostnames.

Example:

app1.example.com
    |
    v
Nginx
    |
    v
127.0.0.1:3000


app2.example.com
    |
    v
Nginx
    |
    v
127.0.0.1:4000


app3.example.com
    |
    v
Nginx
    |
    v
127.0.0.1:5000

## Why This Is Useful

Applications do not all need to listen directly on public ports.

Nginx can provide a single public entry point while routing traffic internally.

This is especially useful when running multiple services on one server.

## Docker Example

The backend applications could also be containers:

Nginx
    |
    +---- app1 container :3000
    |
    +---- app2 container :4000
    |
    +---- app3 container :5000

Nginx routes each hostname to the appropriate backend.

## Example Configuration

server {
    listen 443;
    server_name app1.example.com;

    location / {
        proxy_pass http://127.0.0.1:3000;
    }
}

server {
    listen 443;
    server_name app2.example.com;

    location / {
        proxy_pass http://127.0.0.1:4000;
    }
}

The real HTTPS configuration would also include the appropriate TLS settings.

## Benefits

This architecture provides:

- Centralized routing
- One public entry point
- Multiple applications on one server
- Easier HTTPS management
- Separation between public and internal ports
- Compatibility with Docker-based deployments

## Production Considerations

When hosting multiple applications, consider:

- Resource usage
- Application isolation
- Logs
- TLS certificates
- DNS records
- Container networking
- Health checks
- Deployment strategy
- Failure isolation

## Connection With the DevOps Workflow

The broader architecture can look like:

Users
    |
    v
Cloudflare
    |
    v
Nginx
    |
    +---- Application A
    |
    +---- Application B
    |
    +---- Docker Container
    |
    +---- Other Services

This is one of the reasons Nginx is commonly used in production-oriented application deployments.
