
# Windows SMB Server and Client Connectivity

## Overview

This document covers my learning around connecting a Windows client to a Windows SMB server and understanding the components required for file sharing to work.

## What Is SMB?

Server Message Block (SMB) is a network protocol used by Windows for file and printer sharing.

For example, a client can access a shared folder using a UNC path such as:

`\\SERVER-NAME\SHARE-NAME`

For a connection to work, several things must be configured correctly:

- The server must be running.
- The SMB service and shared folder must be available.
- The client must be able to reach the server over the network.
- DNS or hostname resolution must point to the correct destination.
- Firewalls must permit the required traffic.
- The user must have the necessary share and file-system permissions.

SMB commonly uses TCP port 445.

## How the Connection Works

1. The client identifies the server using a hostname or IP address.
2. The hostname is resolved if the client uses a hostname.
3. The client attempts to establish a network connection to the server.
4. The SMB service handles the connection.
5. Authentication and permissions determine whether the shared resource can be accessed.

A server being online does not necessarily mean that its SMB share is reachable.

## Connectivity Checks

### Check the client's network configuration

Run this in PowerShell:

```powershell
ipconfig
```

This displays network adapters, IP addresses, subnet masks, and gateway information.

### Check hostname resolution

```powershell
Resolve-DnsName SERVER-NAME
```

Replace `SERVER-NAME` with the actual hostname.

Check whether it resolves to the expected address.

### Check SMB port connectivity

```powershell
Test-NetConnection SERVER-NAME -Port 445
```

Check `TcpTestSucceeded` in the output.

A value of `True` indicates that the TCP connection succeeded. It does not by itself prove that authentication or share permissions are correct.

### Access the shared folder

Use the actual share path configured on the server:

```text
\\SERVER-NAME\SHARE-NAME
```

## Troubleshooting

If the share cannot be accessed, check the following in order:

1. Is the server running?
2. Does the hostname resolve to the expected IP address?
3. Is the client using the intended network path?
4. Is TCP port 445 reachable?
5. Are the SMB service and share configured correctly?
6. Are Windows Firewall rules allowing the connection?
7. Are the share and NTFS permissions correct?
8. Are the supplied credentials valid?

Changing several settings at once makes troubleshooting harder. Check one layer at a time.

## What I Learned

- Network connectivity and application-level connectivity are different.
- DNS, routing, firewall rules, and permissions all affect access.
- A successful ping does not prove that SMB works.
- A failed ping does not necessarily mean the server is unavailable.
- Testing the specific service port gives more useful information than relying on ping alone.

## Notes From My Setup

- Client operating system: To be documented
- Server operating system: To be documented
- Network configuration: To be documented
- Shared folder and access method: To be documented
- Issues encountered and their resolution: To be documented

## Security Considerations

SMB should not be exposed directly to the public internet. Access should be restricted to trusted, appropriately secured network paths, with suitable authentication and firewall rules.
