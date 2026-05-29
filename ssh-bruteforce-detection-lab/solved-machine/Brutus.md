<img width="800" height="336" alt="image" src="https://github.com/user-attachments/assets/8842175d-6973-4451-97f8-43e01431e718" />

# HackTheBox X Brutus
## SSH bruteforce simulation
  - Analyzed the raw auth.log file using terminal
  - Detected, responded and reported to SSH bruteforce attack using
  - analyzed IOC (indicators of compromise) using raw logs and WTMP file corelating events to each other.

### Discovering SSH bruteforce attack
Hunting and analyzing failed logins to detect if there is any adversary or unknown IP trying to connect with remote ssh server using automated password spraying tool.
Noticed too many failed attempts in a very short time window confirms Bruteforce attack execution by adversary ip (65.2.161.68).

<img width="800" height="406" alt="bruteforce-initail-detection" src="https://github.com/user-attachments/assets/eab71dcd-6757-4ff0-ac15-6ac723479c3f" />

<img width="800" height="406" alt="detected-adversary-ip" src="https://github.com/user-attachments/assets/c8575e13-65ea-413c-8706-1e81b066502a" />

## Indicators of Compromise (IOC)
This log section confirmed that adversary successfully gain control of the victim machine by exploiting SSH services. Adversary created a new user "cyberjunkie" with root access that allowed them the ability to execute commands remotely and succeded in downloading and executing command on victim machine remotely.

<img width="800" height="406" alt="user-added-by-adversary-with-root-privelleges" src="https://github.com/user-attachments/assets/b040b918-0343-4240-a8a5-5b379e2177dc" />
