# Physhing Analysis Lab Findings 

<img width="800" height="450" alt="BTLO Banner" src="https://github.com/user-attachments/assets/94c2ac7b-153c-4017-92d7-ea8ee1d94015" />

BTLO (Blue Team Labs Online) Challenge - The Planet's Prestige

### Sources Used
 - [Lab](https://blueteamlabs.online/home/challenge/the-planets-prestige-e5beb8e545) - CTF challenge by Blue Team Labs Online.
 - [Cyberchef](https://cyberchef.org/) - Data analysis and decoding platform that helps data formats, encryption and compression of data.
 - [File Signature Table](https://www.garykessler.net/library/file_sigs_GCK_latest.html) - To identify the signature and exact file type of the attachment.
 - [Any Run](https://app.any.run/) - Platform used to run the malicious files in a sandboxed environment.

## Analysis Methodology

Analysed the SPF, DKIM and DMARC failures in the mail headers to see if the mail is suspicious or not. Doing further analysis by carefully identifying the mail server and performing OSINT on the server to check the authenticity. 
