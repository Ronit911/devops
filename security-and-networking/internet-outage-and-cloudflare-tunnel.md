
# Internet Outage and Cloudflare Tunnel

## Overview

This document covers my learning around Cloudflare Tunnel, its internet dependency, and the behavior of services when the connection between a server and Cloudflare becomes unavailable.

The main question is:

**If internet connectivity goes down on a machine, can a client still access a service running on that machine through the local network?**

The answer depends on how the network and service are configured.

## How Cloudflare Tunnel Works

Cloudflare Tunnel uses the `cloudflared` connector to establish outbound connections from a server to Cloudflare.

A configured hostname or application can then be routed through Cloudflare to a service running on the server.

A simplified flow looks like this:

```text
Remote Client
     |
     v
Cloudflare
     |
     v
Cloudflare Tunnel
     |
     v
cloudflared on Server
     |
     v
Internal Service
```

The tunnel avoids the need to expose the origin service directly through an inbound public port, but it still depends on a working connection from the connector to Cloudflare.

## What Happens During an Internet Outage?

If the server loses internet connectivity:

- The server itself may continue running.
- Local applications and services may continue running.
- The `cloudflared` connector may lose its connection to Cloudflare.
- Access that depends on the tunnel may become unavailable.
- Other services that depend on the internet may also stop working.

The failure of the tunnel does not automatically mean that every service on the server has stopped.

## Local Connectivity Versus Tunnel Connectivity

Consider a Windows server hosting an SMB share.

There are two different possible access paths.

### Direct Local Network Access

```text
Windows Client
      |
      v
Local Network
      |
      v
Windows Server
      |
      v
SMB Shared Folder
```

This path may continue working during an internet outage if the client and server can still communicate locally and the relevant services, routing, DNS, and firewall rules remain functional.

### Access Through Cloudflare

```text
Remote Client
      |
      v
Cloudflare
      |
      v
Cloudflare Tunnel
      |
      v
Server
```

This path depends on the tunnel and its required connections being available.

For SMB specifically, the access method must be configured to support the protocol. A normal HTTP application hostname does not automatically make an SMB share accessible.

## The Important Design Question

If an organization needs local access to continue during an internet outage, it should have a separately configured and tested local access path.

Cloudflare Tunnel does not automatically create this fallback.

The client must be able to reach the server through the intended local address or hostname, and the SMB service and firewall must allow the connection.

DNS configuration also matters. A hostname that resolves to a remote or tunnel-based destination may not use the local path even if the server is physically nearby.

## How to Investigate the Failure

Useful Windows commands include:

```powershell
ipconfig
```

Check the client IP address, subnet, and gateway.

```powershell
Resolve-DnsName SERVER-NAME
```

Check which address the hostname resolves to.

```powershell
Test-NetConnection SERVER-NAME -Port 445
```

Check whether the SMB TCP connection succeeds.

Also inspect the tunnel's status and logs on the machine running `cloudflared`.

Repeat the checks before, during, and after the outage. Record the actual destination address and access method so the results can be interpreted correctly.

## Recovery

After internet connectivity is restored:

1. Confirm that the server can reach the internet.
2. Check whether the tunnel reconnects.
3. Verify the tunnel and configured service route.
4. Test the intended remote access path again.
5. Test local SMB connectivity separately.

Do not assume that restoring internet connectivity automatically resolves every DNS, firewall, or application issue.

## What I Learned

- A running server and an available remote access path are two different things.
- Cloudflare Tunnel depends on outbound connectivity to Cloudflare.
- Local connectivity can continue during an internet outage if it uses an independent working network path.
- DNS, routing, service configuration, and firewall rules determine which path a client actually uses.
- Reliable recovery requires testing the failure scenario rather than assuming a fallback exists.

## Notes From My Setup

- Server and client configuration: To be documented
- Access method used: To be documented
- Behavior before the outage: To be documented
- Behavior during the outage: To be documented
- Behavior after connectivity returned: To be documented
- Confirmed cause and troubleshooting steps: To be documented
