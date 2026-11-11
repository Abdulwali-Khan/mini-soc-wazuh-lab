# Mini SOC Lab Using Wazuh

## Project Overview

I'm building a small Security Operations Center (SOC) lab using VMware Workstation, Kali Linux, Ubuntu Linux, and Wazuh. The goal is to gain hands-on experience with security monitoring, log analysis, and detecting suspicious activity.

The Wazuh server and Ubuntu endpoint are configured and communicating over an isolated VMware host-only network. The Ubuntu endpoint runs a Wazuh agent that sends security events to the server for monitoring and analysis.

I've also configured Kali Linux and completed the attack simulation portion of the lab. I ran Nmap scans against the Ubuntu endpoint and generated failed SSH login attempts to create security events. Next, I'll review these events in the Wazuh dashboard to see what was detected.

## Lab Environment

| System | Purpose | Status |
|---|---|---|
| Kali Linux | Generate controlled security events | Configured |
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

- [x] **Milestone 3 – Generate Security Events**  
  Configured Kali Linux, ran Nmap scans against the Ubuntu endpoint, and generated failed SSH login attempts.  
  [View Milestone 3](milestone-3-attacks/)

- [ ] **Milestone 4 – Review and Investigate Wazuh Alerts**  
  Analyze the collected alerts and investigate suspicious activity.

- [ ] **Milestone 5 – Final Testing and Documentation**  
  Complete testing and document the final project results.

## Current Progress

Milestones 1, 2, and 3 are complete.

So far, I have:

- Planned the Mini SOC architecture and created a network diagram.
- Configured the Wazuh server and Ubuntu endpoint virtual machines.
- Assigned static IP addresses on the isolated host-only network.
- Installed Wazuh and connected the Ubuntu endpoint using the Wazuh agent.
- Verified that the endpoint appears as active in the Wazuh dashboard.
- Confirmed that Wazuh is collecting security events, including login activity, sudo commands, and system configuration checks.
- Troubleshot Netplan configuration errors and an Ubuntu package manager lock during installation.
- Configured Kali Linux with a static IP address of `192.168.159.10`.
- Installed OpenSSH Server on the Ubuntu endpoint for authentication testing.
- Ran Nmap SYN and version detection scans against the Ubuntu endpoint.
- Generated controlled failed SSH login attempts from Kali Linux.
- Verified that the failed login attempts were recorded in the Ubuntu endpoint's system logs.
- Confirmed that the Wazuh agent reconnected after restarting the Wazuh server.

Next, I'll review the security events in the Wazuh dashboard and investigate the alerts for Milestone 4.
