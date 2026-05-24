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
On May 16, 2026 at 23:11 (UTC), logs reported unusual multiple failed attempts on sshd service from unknown IP (192.168.1.67) trying to log in from remote machine on host "soc-analyst" (192.168.1.166). After analying IOC (multiple failed attempts at a superhuman speed, average nearly 250 attempts per minute) confirms some automation tools being used by adversary trying to guess the password using custom dictionary to bruteforce ssh service. Adversary failed everytime so system is still secured.
