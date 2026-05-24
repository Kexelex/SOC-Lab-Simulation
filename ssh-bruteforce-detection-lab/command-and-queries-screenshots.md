## Hydra Command Used
    hydra -l wordlist.txt -P wordlist.txt 192.168.1.166 ssh
    
<img width="800" height="144" alt="hydra-attack" src="https://github.com/user-attachments/assets/a0e48730-4734-479f-9b86-1df55e6e73af" />

## Splunk Authentication Logs
<img width="800" height="450" alt="splunk-logs" src="https://github.com/user-attachments/assets/f2326717-18e5-4b56-830f-c5d9772365e1" />

## Failed Login Detection Query
<img width="800" height="79" alt="failed-login-query" src="https://github.com/user-attachments/assets/fdaf5954-4e3a-4f9a-852b-31f614ed2ea0" />

## SIEM Dashboard
<img width="800" height="501" alt="dashoard" src="https://github.com/user-attachments/assets/d1deca99-8179-4d1c-84dd-d8f64b880f6c" />

## Creating Alert
<img width="800" height="648" alt="creating-alert" src="https://github.com/user-attachments/assets/13b2611f-4a03-4c44-b92a-03189675b2e1" />


## Report
On May 16, 2026, at 23:11 UTC, multiple failed authentication attempts were detected against the SSH service (sshd) on host soc-analyst (192.168.1.166). The activity originated from source IP 192.168.1.67, identified as a remote machine within the lab environment.
Analysis of the logs revealed a high frequency of failed login attempts, averaging approximately 250 attempts per minute, indicating the likely use of an automated brute-force tool utilizing a custom password dictionary against the SSH service.

### Indicators of Compromise (IOCs) observed:
  - Multiple failed SSH authentication attempts
  - Repetitive login failures from a single source IP
  - High-speed authentication requests consistent with automation activity

The attack was unsuccessful, and no unauthorized access was achieved. The targeted system remained secure throughout the incident.
A detection rule and alert were subsequently created in Splunk to identify similar brute-force behavior in future events.
