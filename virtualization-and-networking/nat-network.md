# NAT Network Configuration

A NAT Network was configured in VirtualBox to allow the virtual machines to communicate with each other while also providing access to external networks.

## Network Configuration

Example NAT Network configuration:

Network: 192.168.5.0/24
Gateway: 192.168.5.1

The virtual machines were assigned addresses within this private network.

Example:

NAT Network
192.168.5.0/24
    |
    +---- Gateway: 192.168.5.1
    |
    +---- Ubuntu Server: 192.168.5.x
    |
    +---- Windows Server: 192.168.5.x

## Why NAT Networking?

NAT allows virtual machines to communicate through a private network while sharing the host machine's external network connection.

This is useful for a local DevOps lab because servers can communicate with each other without exposing the virtual machines directly to the public internet.

## Verification

Network connectivity can be checked from Ubuntu using:

ip addr

To inspect routes:

ip route

Connectivity to the gateway can be tested with:

ping 192.168.5.1

Internet connectivity can be tested with:

ping 8.8.8.8

DNS resolution can be checked with:

ping google.com

## Key Concepts

The setup helped build practical understanding of:

- Private IP addressing
- NAT
- Gateways
- Network interfaces
- Routing
- Connectivity testing
- Virtual machine networking
