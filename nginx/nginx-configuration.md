# Nginx Configuration

Nginx behavior is controlled through configuration files.

Understanding the configuration structure is important when troubleshooting deployment problems.

## Basic Server Block

A simplified configuration:

server {
    listen 80;
    server_name example.com;

    location / {
        proxy_pass http://127.0.0.1:3000;
    }
}

## Important Directives

### listen

Defines the port where Nginx listens for requests.

Example:

listen 80;

HTTPS commonly uses:

listen 443 ssl;

### server_name

Defines the hostname associated with a server block.

Example:

server_name example.com;

### location

Defines how requests matching a path should be handled.

Example:

location / {
    proxy_pass http://127.0.0.1:3000;
}

### proxy_pass

Defines the backend destination.

Example:

proxy_pass http://127.0.0.1:3000;

## Configuration Testing

Before reloading Nginx, the configuration can be tested with:

sudo nginx -t

A successful configuration test is important before applying changes.

## Reloading Nginx

After making configuration changes:

sudo systemctl reload nginx

Reloading allows Nginx to apply configuration changes without unnecessarily stopping the service.

## Service Status

Check the service:

sudo systemctl status nginx

Start Nginx:

sudo systemctl start nginx

Stop Nginx:

sudo systemctl stop nginx

Restart Nginx:

sudo systemctl restart nginx

## Logs

Nginx logs are useful when diagnosing problems.

Common locations include:

/var/log/nginx/access.log
/var/log/nginx/error.log

The access log records incoming requests.

The error log contains information about errors and other Nginx events.

## Troubleshooting Approach

When an application is not accessible:

1. Check whether Nginx is running.
2. Test the Nginx configuration.
3. Check the listening ports.
4. Check the backend application.
5. Check Nginx logs.
6. Test the backend directly.
7. Verify DNS and Cloudflare configuration if applicable.

This separates infrastructure problems from application problems.
