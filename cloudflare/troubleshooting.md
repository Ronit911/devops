# Cloudflare Troubleshooting

Troubleshooting a Cloudflare deployment requires checking multiple layers.

## Layer 1: Application

First verify that the application works locally on the server.

For example:

curl http://localhost:<port>

If the local application does not work, Cloudflare is not the first place to troubleshoot.

## Layer 2: Application Process

Check whether the application process is running.

For PM2:

pm2 status

Check logs:

pm2 logs

## Layer 3: Tunnel

Check the Cloudflare connector:

systemctl status cloudflared

If the service is not running, inspect its logs:

journalctl -u cloudflared

## Layer 4: DNS

Verify that the hostname is configured correctly.

Example:

react.ronitwork.bid

DNS configuration should point the hostname toward the Cloudflare-managed infrastructure associated with the tunnel.

## Layer 5: HTTPS

If DNS and the tunnel are functioning but HTTPS requests fail, investigate:

- TLS configuration
- Cloudflare SSL/TLS settings
- Origin service configuration
- Hostname routing
- Certificate-related errors

## Troubleshooting Order

A useful troubleshooting sequence is:

Application
    ?
Application Port
    ?
PM2 / Process
    ?
cloudflared
    ?
Tunnel Configuration
    ?
DNS
    ?
Cloudflare
    ?
Client

Checking the layers from the inside outward helps isolate the failure point instead of changing multiple components at once.
