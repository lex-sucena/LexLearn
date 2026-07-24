# Architecture Overview

This document describes the architecture of the Enterprise Infrastructure Lab.

## Purpose

Define the structure and evolution of the infrastructure that supports the fictional company, LexLearn.

The architecture is designed to simulate a real-world enterprise environment while remaining scalable and easy to extend as new technologies are introduced.

## Design Principles

The infrastructure should:

- Simulate a real corporate environment.
- Be modular and scalable.
- Follow industry best practices whenever practical.
- Prioritize simplicity before complexity.
- Support future integration with additional services and technologies.

## Current Architecture

The initial infrastructure consists of a single Windows Server acting as the Domain Controller and a Windows 11 client joined to the domain.

### Virtualization Platform

- Virtual Machine Manager (virt-manager)
- KVM/QEMU virtualization

### Virtual Machine Distribution

Due to hardware limitations, the virtual machines will be hosted across two physical computers.

| Host | Virtual Machine |
|------|----------------|
| Laptop | SRV-DC-01 |
| Desktop PC | CLT-01 |

### Virtual Network

| Network | Subnet |
|----------|--------|
| Internal Network | 192.168.10.0/24 |

### Virtual Machines

| Name | Operating System | Purpose |
|------|-------------------|---------|
| SRV-DC-01 | Windows Server 2022 | Domain Controller, DNS, DHCP |
| CLT-01 | Windows 11 Pro | Domain-joined client workstation |

### Domain

| Property | Value |
|----------|-------|
| Domain Name | lexlearn.local |

### IP Addressing

| Device | Address |
|---------|---------|
| SRV-DC-01 | 192.168.10.10 (Static) |
| CLT-01 | DHCP |

### Server Roles

#### SRV-DC-01

- Active Directory Domain Services (AD DS)
- DNS
- DHCP

#### CLT-01

- Domain member
- Client workstation

## Future Components

The infrastructure will gradually expand with additional services, including:

- File Services
- Group Policy
- PowerShell Automation
- Monitoring
- Security
- Microsoft Entra ID
- Microsoft Intune
- Microsoft Azure

## Architecture Evolution

The environment will evolve incrementally.

Each new component should integrate with the existing infrastructure rather than being implemented as an isolated lab.