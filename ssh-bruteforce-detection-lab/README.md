<h1>SSH Brute Force Attack Detection Lab</h1>
<h2>Project Overview</h2>
 This lab simulation demonstrates detection and analysis of an SSH brute-force attack using Splunk Enterprise.
 The objective of this project was to simulate a real-world SSH dictionary brute-force attack from an adversary machine and investigate authentication logs within a SIEM environment.

<h2>Lab Environment</h2>
<h3>Infrastructure</h3>

-------------------------------------------------------
|Component	               |Purpose                    |
|-------------------------|---------------------------| 
|Ubuntu Server (TTY)	     |Victim Machine + SIEM Host |
|Splunk Enterprise        |Log Analysis & Monitoring  |
|Kali Linux	              |Adversary Machine          |
|Hydra	                   |Password Brute Force Tool  |
|VirtualBox	              |Virtualization Platform    |
-------------------------------------------------------

<h2>Attack Simulation</h2>
<h3>SSH Brute Force Simulation</h3>
 A dictionary-based SSH brute-force attack was simulated using Hydra from the Kali Linux attacker machine.
 The attack targeted the SSH service running on the Ubuntu Server VM.
 The objective was to simulate adversarial behavior attempting unauthorized remote access when usernames and/or passwords are unknown.

Attack Methodology
Technique Used
SSH Password Brute Force
Dictionary Attack
Credential Guessing
Attack Workflow
Reconnaissance of target SSH service
Hydra dictionary attack execution
Multiple failed login attempts generated
Authentication logs collected by Splunk
Detection and analysis performed within SIEM
