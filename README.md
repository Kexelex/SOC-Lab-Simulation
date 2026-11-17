# SOC Lab Simulation | Blue Team & Detection Engineering
A hands-on Security Operations Center (SOC) lab built to simulate attacks, collect endpoint telemetry, investigate security events, and develop detection capabilities using Splunk Enterprise. Included with workflow detection screenshots from simulation lab.  
This project demonstrates practical Blue Team skills through Linux and Windows endpoint monitoring, Sysmon telemetry collection, Splunk SIEM, and adversary emulation using Atomic Red Team.

## Lab Structure
<img width="1920" height="1080" alt="Lab Diagram" src="https://github.com/user-attachments/assets/3624f901-a68a-4fec-8aa5-11dd69c8bea9" />
<I>The diagram represents the intended workflow. Atomic Red Team tests should be run against the appropriate lab endpoint, not assumed to run against every machine.</I>

## Project Objectives
 - Build and maintain a multi-endpoint SOC lab environment.
 - Centralize Windows and Linux security logs using Splunk.
 - Monitor Windows endpoint activity through Sysmon.
 - Perform controlled adversary emulation using Atomic Red Team.
 - Investigate suspicious activities and identify indicators of compromise.
 - Develop SPL queries, detection rules, dashboards, and alerts.
 - Map simulated activities to the MITRE ATT&CK framework.
 - Document investigation procedures and security findings.

## Lab Environment

| Component | Environment | Purpose |
|---|---|---|
| Host Machine | Ubuntu Desktop | Main virtualization Host |
| Hypervisor | VirtualBox | Virtual Lab Inforastructure | 
| SIEM | Splunk Enterprise | Centralized log monitoring and analysis |
| Linux Endpoint | Ubuntu Server (TTY) | Linux security event collection |
| Windows Endpoint | Windows 10 | Windows security monitoring |
| Log Collection | Splunk Universal Forwarder | Endpoint log forwarding |
| Endpoint Monitoring | Sysmon | Detailed Windows system telemetry |
| Adversary Machine | Kali Linux | Controlled attack simulations |
| Adversary Emulation | Atomic Red Team | Atomic Red Team |

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

## MITRE ATT&CK Mapping
The simulated attacks and detections are mapped to the MITRE ATT&CK framework to better understand attacker tactics, techniques, and procedures (TTPs).

| Attack Scenario | Technique | ID |
|---|---|---|
| SSH Brute Force | Brute Force | T1110 |
| Phishing Analysis | Phishing for Initial Access | T1566 |
| Reverse Shell | Command and Scripting Interpreter | T1059 |
| Network Reconnaissance | Network Service Scanning | T1046 |
| Privellege Escalation | Exploitation for Privilege Escalation | T1068 |

[MITRE ATT&CK](https://attack.mitre.org/).

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
- continual improvement
