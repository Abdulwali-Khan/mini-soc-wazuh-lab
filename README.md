# Mini SOC Lab Using Wazuh

## Project Overview

I'm building a small Security Operations Center (SOC) lab using VMware Workstation, Kali Linux, Ubuntu Linux, and Wazuh. The goal is to gain hands-on experience with security monitoring, log analysis, and detecting suspicious activity.

The Wazuh server and Ubuntu endpoint are now configured and communicating over an isolated VMware host-only network. The Ubuntu endpoint runs a Wazuh agent that sends security events to the server for monitoring and analysis.

In the next milestone, I'll use Kali Linux to generate controlled security activity against the Ubuntu endpoint and investigate the results in Wazuh.

## Lab Environment

| System | Purpose | Status |
|---|---|---|
| Kali Linux | Generate controlled security events | Planned |
| Ubuntu Linux | Monitored endpoint running the Wazuh agent | Configured |
| Wazuh Server | Collect and analyze security logs | Configured |
| VMware Workstation | Host the virtual machines | Configured |

**Network:** VMware VMnet1 (Host-Only), `192.168.159.0/24`

## Project Milestones

- [x] **Milestone 1 – Planning and Network Design**  
  Reviewed hardware requirements, allocated VM resources, and created the network diagram.  
  [View Milestone 1](milestone-1-planning/)

- [x] **Milestone 2 – Wazuh Server and Endpoint Setup**  
  Installed Wazuh, configured the Ubuntu endpoint, connected the Wazuh agent, and verified security event collection.  
  [View Milestone 2](milestone-2-setup/)

- [ ] **Milestone 3 – Generate Security Events**  
  Set up Kali Linux and generate controlled security activity.

- [ ] **Milestone 4 – Review and Investigate Wazuh Alerts**  
  Analyze the collected alerts and investigate suspicious activity.

- [ ] **Milestone 5 – Final Testing and Documentation**  
  Complete testing and document the final project results.

## Current Progress

Milestones 1 and 2 are complete.

So far, I have:

- Planned the Mini SOC architecture and created a network diagram.
- Configured the Wazuh server and Ubuntu endpoint virtual machines.
- Assigned static IP addresses on the isolated host-only network.
- Installed Wazuh and connected the Ubuntu endpoint using the Wazuh agent.
- Verified that the endpoint appears as active in the Wazuh dashboard.
- Confirmed that Wazuh is collecting security events, including login activity, sudo commands, and system configuration checks.
- Troubleshot Netplan configuration errors and an Ubuntu package manager lock during installation.

The next step is to introduce Kali Linux and test how Wazuh detects controlled security activity.
