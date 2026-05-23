# SSH Brute Force Attack Detection Lab
## Project Overview
   - This lab simulation demonstrates detection and analysis of brute-force attack on SSH service running on ubuntu server (TTY) using Splunk Enterprise.
   - The objective of this project was to simulate a real-world SSH dictionary brute-force attack from an adversary machine and investigate authentication logs within a SIEM environment.

## Lab Environment
### Infrastructure

-------------------------------------------------------
|Component	               |Purpose                    |
|-------------------------|---------------------------| 
|Ubuntu Server (TTY)	     |Victim Machine + SIEM Host |
|Splunk Enterprise        |Log Analysis & Monitoring  |
|Kali Linux	              |Adversary Machine          |
|Hydra	                   |Password Brute Force Tool  |
|VirtualBox	              |Virtualization Platform    |
-------------------------------------------------------

## Attack Simulation
### SSH Brute Force Simulation
   - A dictionary-based SSH brute-force attack was simulated using Hydra from the Kali Linux attacker machine.
   - The attack targeted the SSH service running on the Ubuntu Server VM.
   - The objective was to simulate adversarial behavior attempting unauthorized remote access when usernames and/or passwords are unknown.

## Attack Methodology
### Technique Used
   - SSH Password Brute Force
   - Dictionary Attack
   - Credential Guessing
### Attack Workflow
   - Reconnaissance of target SSH service
   - Hydra dictionary attack execution
   - Multiple failed login attempts generated
   - Authentication logs collected by Splunk
   - Detection and analysis performed within SIEM

## Detection Criteria
  - Identified password spraying and bruteforce attempt
  - detected automated attacks failure / success
  - Monitored repeated login attempts from a single source IP address
  - Identified abnormal spikes in “Failed password” authentication events

## Splunk Log Analysis
  - Authentication logs from the Ubuntu Server were ingested into Splunk Enterprise using the Universal Forwarder.
  - The primary focus of investigation was SSH authentication logs (/var/log/auth.log).
  - Multiple failed login attempts were observed originating from the Kali Linux attacker machine.
  - The logs showed repeated “Failed password” events indicating unsuccessful authentication attempts.
  - A noticeable spike in failed login activity was detected within a short time window, confirming automated attack behavior.

## Splunk Queries Used
  - Authentication logs from the Ubuntu Server were ingested into Splunk Enterprise using the Universal Forwarder.
  - The primary focus of investigation was SSH authentication logs (/var/log/auth.log).
  - Multiple failed login attempts were observed originating from the Kali Linux attacker machine.
  - The logs showed repeated “Failed password” events indicating unsuccessful authentication attempts.
  - A noticeable spike in failed login activity was detected within a short time window, confirming automated attack behavior.

### Failed SSH Login Detection Query
     index=* "Failed Password"

### Identfied Source IP with Most Failures
     index=* sourcetype=syslog "Failed password"
     |stats count by src_ip
     |sort - count

### Brute Force Pattern Detection (Based on IP)
     index=* sourcetype=syslog "Failed password"
     |rex "frem(?<src_ip>\d+\.\d+\.\d+\.\d+"
     |stats count by src_ip
     |where count > 10

## Security Observations
  - Repeated authentication failures are a strong indicator of automated brute-force activity.
  - Single-source IP generating high-frequency login attempts confirms attack automation.
  - Splunk successfully provided centralized visibility into SSH authentication logs.
  - Log correlation allowed clear identification of malicious behavior patterns.
  - Detection logic effectively separated normal login activity from attack traffic.

## Mitigation Strategies
  - SSH authentication logs were continuously monitored using Splunk SIEM.
  - Threshold based detection rules were implemented for brute-force identification.
  - Failed login patterns were used to trigger real-time alerting.
  - System remained protected as all authentication attempts failed.
  - This scenario highlights the importance of monitoring authentication services in real time.





     
