# Physhing Analysis Lab Findings 

<img width="800" height="450" alt="BTLO Banner" src="https://github.com/user-attachments/assets/94c2ac7b-153c-4017-92d7-ea8ee1d94015" />

BTLO (Blue Team Labs Online) Challenge - The Planet's Prestige

### Sources Used
 - [Lab](https://blueteamlabs.online/home/challenge/the-planets-prestige-e5beb8e545) - CTF challenge by Blue Team Labs Online.
 - [Cyberchef](https://cyberchef.org/) - Data analysis and decoding platform that helps data formats, encryption and compression of data.
 - [File Signature Table](https://www.garykessler.net/library/file_sigs_GCK_latest.html) - To identify the signature and exact file type of the attachment.
 - [Any Run](https://app.any.run/) - Platform used to run the malicious files in a sandboxed environment.

## Analysis Methodology

 Analysed the SPF, DKIM and DMARC failures in the mail headers to see if the mail is suspicious or not. Doing further analysis by carefully examining the  

<img width="800" height="60" alt="image" src="https://github.com/user-attachments/assets/133fbef2-6cde-473b-a397-e57cc549966f" />
 - Watched for the SPF (failed), DKIM & DMARC to quickly figure out if the mail is suspicious or not. In this the SPF status is failed that denotes a suspicious mail.

<img width="683" height="151" alt="image" src="https://github.com/user-attachments/assets/e1cc4a57-42cc-4eec-98bf-0f5a2491c1b0" />
