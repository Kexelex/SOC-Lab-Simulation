# My-SOC-Lab-Simulation
Built a personal Security Operations Center (SOC) lab environment to simulate real-world cyber attacks, perform security monitoring, investigate incidents, and practice detection engineering using Splunk Enterprise and offensive security tooling in an isolated virtualized environment.

## Lab Structure
<img width="1028" height="620" alt="Lab Diagram" src="https://github.com/user-attachments/assets/c2b3fcf2-f20d-443a-a810-e196cfbccb21" />

## Lab Environment

Component                   |  Purpose
-------------------------------------------------------------------------------------------------------------
Ubuntu Desktop              |   Main Host OS
Windows 11 Laptop           |   Separate Endpoint Device for Windows Log Monitoring & Security Event Analysis
Ubuntu Server (TTY)         |   Victim Machine + Splunk SIEM
Kali Linux                  |   Adversary Simulation Machine
Splunk Enterprise           |   Log Collection & SIEM Analysis
Splunk Universal Forwarder  |   Log Forwarding
VirtualBox                  |   Virtualization Platform
------

### Setup & Configuration
  - Installed and configured Splunk Enterprise on the Ubuntu Server VM from scratch.
  - Configured a secure isolated virtual lab environment enabling communication between VMs and host systems while maintaining internet access.
  - Installed and configured Splunk Universal Forwarder to forward endpoint logs into Splunk for centralized monitoring.
  - Configured Linux log ingestion and monitoring for authentication and system activity.
  - Created custom dashboards, searches, and alerts for incident detection and analysis.
  - Practiced secure network segmentation and VM communication management within a virtualized environment.

## Simulated Attack Scenarios
This SOC lab is used to simulate and analyze various attacker techniques and security incidents.

### SSH Brute Force Attack Simulation
  - Simulated SSH dictionary brute-force attacks using Hydra from Kali Linux.
  - Monitored failed authentication attempts in Splunk.
  - Created SPL detection queries and brute-force alerts.
  - Mapped attack activity to the MITRE ATT&CK framework (T1110 — Brute Force).

### Phishing Analysis
  - Investigated phishing email indicators and suspicious links/files.
  - Practiced identifying indicators of compromise (IOCs).
  - Analyzed phishing-related artifacts and attack behaviors.
  - Learned how phishing attempts can lead to credential compromise and initial access.

### Reverse Shell Detection
  - Simulated reverse shell activity between attacker and victim systems.
  - Investigated suspicious outbound connections and shell behavior.
  - Monitored logs for abnormal process execution and network activity.
  - Practiced identifying persistence and remote access techniques.

### Network Reconnaissance & Nmap Scanning
  - Simulated reconnaissance activities using Nmap.
  - Performed service discovery and port scanning against lab systems.
  - Investigated scan patterns and network enumeration activity in logs.
  - Learned how reconnaissance activity appears from a defensive monitoring perspective.

### Privilege Escalation Analysis
  - Simulated privilege escalation scenarios within Linux environments.
  - Investigated suspicious sudo activity and privilege abuse attempts.
  - Analyzed authentication and authorization logs.
  - Practiced identifying indicators of privilege escalation and unauthorized access

## Detection Engineering & SIEM Operations

### Splunk Skills Practiced
  - SPL (Splunk Search Processing Language)
  - Log ingestion and parsing
  - Field extraction using regex (rex)
  - Dashboard creation and visualization
  - Real-time alert configuration
  - Event correlation
  - IOC investigation
  - Authentication log analysis
  - Security event monitoring
  - Detection rule creation
  - Threat hunting basics

## MITRE ATT&CK Mapping
The simulated attacks and detections are mapped to the MITRE ATT&CK framework to better understand attacker tactics, techniques, and procedures (TTPs).

-------------------------------------------------
| Technique                             |  ID   |
-------------------------------------------------
| Brute Force                           | T1110 |
| Phishing                              | T1566 |
| Command and Scripting Interpreter     | T1059 |
| Network Service Scanning              | T1046 |
| Exploitation for Privilege Escalation | T1068 |
-------------------------------------------------
[MITRE ATT&CK](https://attack.mitre.org/).

## ISO 27001:2022 Security Control Alignment
The SOC lab environment was also used to understand how security monitoring and incident response activities align with real-world information security governance practices defined in ISO/IEC 27001.

The simulations helped reinforce concepts related to:

- access control
- authentication security
- logging and monitoring
- incident detection and response
- threat analysis
- privileged access management
- network segregation
- evidence collection
- continual security improvement


