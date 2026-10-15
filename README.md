# Mini SOC Lab Using Wazuh

## Project Overview

I'm building a small Security Operations Center (SOC) lab using VMware Workstation, Kali Linux, Ubuntu Linux, and Wazuh. The goal is to gain hands-on experience with security monitoring, log analysis, and detecting suspicious activity.

Kali Linux will be used to generate controlled security events against an Ubuntu virtual machine. The Ubuntu system will run a Wazuh agent that sends logs to the Wazuh server for monitoring and analysis.

## Lab Environment

| System | Purpose |
|---|---|
| Kali Linux | Generate controlled security events |
| Ubuntu Linux | Monitored endpoint |
| Wazuh Server | Collect and analyze security logs |
| VMware Workstation | Host the virtual machines |

**Network:** VMware VMnet1 (Host-Only), 192.168.159.0/24

## Project Milestones

- [x] Milestone 1 — Plan the lab and create the network diagram
- [ ] Milestone 2 — Set up the virtual machines and install Wazuh
- [ ] Milestone 3 — Generate security events
- [ ] Milestone 4 — Review and investigate Wazuh alerts
- [ ] Milestone 5 — Complete final testing and document results

## Current Progress

Milestone 1 is complete. I reviewed my laptop's hardware, planned the resources for each virtual machine, checked VMware's network settings, and created a network diagram showing how the systems will communicate.

The virtual machines and Wazuh services have not been installed yet.

## Next Steps

I'll create the virtual machines, configure the host-only network, install Wazuh, and connect the Ubuntu endpoint to the Wazuh server. Once everything is working, I'll begin generating test activity and reviewing the alerts.
