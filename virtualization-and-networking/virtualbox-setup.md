# VirtualBox Virtualization Setup

VirtualBox was used to create and manage virtual machines for practicing server administration and DevOps infrastructure.

## Virtual Machines

The lab environment included:

- Windows Server
- Ubuntu Server

The virtual machines provided an isolated environment for practicing server configuration, networking, application deployment, and infrastructure management.

## Virtual Machine Configuration

The Ubuntu Server virtual machine was configured with:

- Memory: 8192 MB
- Processors: 4
- Network Adapter: NAT Network

## Why Virtualization?

Virtualization makes it possible to run multiple operating systems on the same physical machine.

For DevOps learning, this provides an environment where servers can be created, configured, modified, and tested without requiring separate physical machines.

Virtual machines are useful for practicing:

- Server administration
- Networking
- Linux administration
- Application deployment
- Infrastructure configuration
- Troubleshooting

## Key Concept

A Type 2 hypervisor runs on top of an existing host operating system.

Physical Computer
    |
    v
Windows Host OS
    |
    v
VirtualBox
    |
    +------------------+
    |                  |
    v                  v
Ubuntu Server      Windows Server

This lab environment forms the foundation for the rest of the DevOps experiments in this repository.
