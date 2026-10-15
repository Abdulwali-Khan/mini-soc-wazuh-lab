# Milestone 1 — Lab Planning

## Objective

Plan a small Security Operations Center (SOC) lab using VMware Workstation, Kali Linux, Ubuntu Linux, and Wazuh.

## Work Completed

- Checked my laptop's CPU, RAM, storage, and virtualization support.
- Planned the resources needed for three virtual machines.
- Reviewed VMware's host-only network settings and DHCP range.
- Selected planned static IP addresses for each virtual machine.
- Created a network diagram showing the systems and how they will communicate.

## Planned Virtual Machines

| System | IP Address | RAM | vCPUs | Storage |
|---|---|---|---|---|
| Kali Linux | 192.168.159.10 | 2 GB | 2 | 30 GB |
| Ubuntu Linux | 192.168.159.20 | 2 GB | 2 | 25 GB |
| Wazuh Server | 192.168.159.30 | 8 GB | 2 | 50 GB |

## Network Configuration

The lab will use VMware's VMnet1 host-only network with the subnet `192.168.159.0/24`.

I chose host-only networking to keep the planned security testing separate from my regular network.

## What I Learned

This milestone helped me understand how to plan virtual machine resources, choose IP addresses outside a DHCP range, and design an isolated network for security testing.

## Status

Milestone 1 is complete. The virtual machines and Wazuh services will be installed during Milestone 2.
