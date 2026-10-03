# Windows Server Setup

Windows Server was included in the virtualized infrastructure lab to gain practical exposure to Windows-based server environments.

## Virtual Machine

Windows Server was installed as a virtual machine using VirtualBox.

The VM was configured as part of the same local infrastructure lab used for experimenting with server administration and networking.

## Virtualization Environment

The basic architecture was:

Physical Computer
    |
    v
Windows Host
    |
    v
VirtualBox
    |
    +---- Windows Server VM
    |
    +---- Ubuntu Server VM

## Networking

The Windows Server VM was connected to the VirtualBox NAT Network.

The NAT Network provided:

- Private IP addressing
- Communication between virtual machines
- Gateway-based connectivity
- External network access through NAT

## Learning Objectives

Working with Windows Server provides exposure to:

- Windows-based server administration
- Server networking
- Virtual machine management
- Remote administration concepts
- Enterprise infrastructure environments

## DevOps Relevance

DevOps environments frequently contain a mixture of Linux and Windows infrastructure.

Understanding both environments helps when working with:

- Windows-based applications
- Enterprise infrastructure
- Active Directory environments
- Windows-based build agents
- Hybrid infrastructure
- Cross-platform deployment workflows
