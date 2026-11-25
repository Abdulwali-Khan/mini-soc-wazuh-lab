# Mini SOC Lab Using Wazuh

## Project Overview

I'm building a small Security Operations Center (SOC) lab using VMware Workstation, Kali Linux, Ubuntu Linux, and Wazuh. The goal is to gain hands-on experience with security monitoring, log analysis, and detecting suspicious activity.

The Wazuh server and Ubuntu endpoint are configured and communicating over an isolated VMware host-only network. The Ubuntu endpoint runs a Wazuh agent that sends security events to the server for monitoring and analysis.

I've configured Kali Linux and completed the attack simulation portion of the lab, including Nmap scans and controlled failed SSH login attempts against the Ubuntu endpoint.

I've also completed the security alert investigation using Wazuh Threat Hunting. I identified 12 authentication failure alerts associated with six failed SSH login attempts, analyzed detection rules, correlated related events, and reviewed MITRE ATT&CK classifications. I also identified potential limitations in my current monitoring configuration.

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

- [x] **Milestone 4 – Review and Investigate Wazuh Alerts**  
  Investigated historical security alerts, analyzed SSH and PAM authentication failures, correlated related events, reviewed MITRE ATT&CK classifications, and identified potential detection limitations.  
  [View Milestone 4](milestone-4-alert-analysis/)

- [ ] **Milestone 5 – Final Testing and Documentation**  
  Complete testing, evaluate detection consistency, and document the final project results.

## Current Progress

Milestones 1, 2, 3, and 4 are complete.

**Project Completion: 80% (4 of 5 milestones)**

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
- Resolved a VMware host-only network subnet mismatch and restored dashboard connectivity.
- Investigated historical security events using Wazuh Threat Hunting.
- Used DQL queries to isolate alerts associated with Kali's source IP address.
- Identified 12 authentication failure alerts associated with six failed SSH login attempts.
- Analyzed Wazuh detection rules, severity levels, decoders, and original system logs.
- Correlated SSH and PAM alerts using source IP addresses, usernames, process IDs, and timestamps.
- Reviewed MITRE ATT&CK classifications for Password Guessing and SSH.
- Investigated potential limitations in network reconnaissance detection.

## Security Detection Results

| Security Activity | Detection Result |
|---|---|
| Failed SSH login attempts | Detected |
| PAM authentication failures | Detected |
| Brute-force correlation | No separate matching alert identified |
| Nmap SYN scan | No matching alert identified |
| Nmap version detection scan | No matching alert identified |

### Wazuh Alert Summary

| Rule ID | Description | Severity Level | Alert Count |
|---|---|---:|---:|
| 5760 | SSH authentication failed | 5 | 6 |
| 5503 | PAM user login failed | 5 | 6 |
| **Total** | | | **12** |

### MITRE ATT&CK Techniques Identified

| Technique ID | Technique | Tactic |
|---|---|---|
| T1110.001 | Password Guessing | Credential Access |
| T1021.004 | SSH | Lateral Movement |

These classifications represent potential attacker behavior and do not indicate successful unauthorized access.

## Next Steps

During Milestone 5, I plan to repeat selected security tests to verify detection consistency, investigate brute-force correlation alerts, explore additional network monitoring options, and evaluate the overall effectiveness and limitations of my Mini SOC.

The final milestone will focus on completing the testing process and documenting the overall project results.
