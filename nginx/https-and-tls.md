# HTTPS and TLS

HTTPS protects communication between clients and servers by using TLS.

Nginx can terminate TLS connections and forward requests to backend applications.

## HTTP vs HTTPS

HTTP:

Client
    |
    v
Nginx :80
    |
    v
Application

HTTPS:

Client
    |
    v
TLS
    |
    v
Nginx :443
    |
    v
Application

The public endpoint can therefore use HTTPS while the backend service can operate on an internal port.

## TLS Termination

TLS termination means that Nginx handles the encrypted HTTPS connection.

Example:

Browser
    |
    | HTTPS
    v
Nginx :443
    |
    | HTTP or internal protocol
    v
Application :3000

The exact backend protocol depends on the architecture.

## Certificates

A TLS certificate allows a domain to establish a trusted HTTPS connection.

Certificates can be obtained and managed using different certificate authorities and platforms.

In a Cloudflare-based architecture, Cloudflare can also participate in TLS handling depending on the selected SSL/TLS mode and deployment design.

## Common HTTPS Configuration

A simplified Nginx configuration may include:

server {
    listen 443 ssl;
    server_name example.com;

    ssl_certificate /path/to/certificate.pem;
    ssl_certificate_key /path/to/private-key.pem;

    location / {
        proxy_pass http://127.0.0.1:3000;
    }
}

The actual certificate paths and security configuration depend on the environment.

## HTTP to HTTPS Redirect

A common deployment pattern is:

HTTP :80
    |
    v
Redirect
    |
    v
HTTPS :443
    |
    v
Application

A simplified configuration:

server {
    listen 80;
    server_name example.com;

    return 301 https://$host$request_uri;
}

## Security Considerations

Production HTTPS configurations should consider:

- Certificate management
- Private key protection
- TLS versions
- Strong cipher configuration
- HTTP to HTTPS redirects
- Certificate renewal
- Security headers

HTTPS should be treated as part of the overall deployment architecture rather than simply enabling a port.
