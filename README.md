# My-SOC-Lab-Simulation

Built a personal SOC lab environment to practice security monitoring, log ingestion, SIEM configuration, and incident analysis using Splunk and security tools in a simulated environment.

<h2>My Lab Structure</h2>

<img width="1028" height="620" alt="Lab Diagram" src="https://github.com/user-attachments/assets/c2b3fcf2-f20d-443a-a810-e196cfbccb21" />

<h3>Setup and Configuration</h3>

- Installed Splunk Enterprise on my ubuntu server (Victim VM) and configured it from scratch. 
- I configured a safe lab environment where all my VMs and my host machine communicates with each other and can use internet.
- Setup and configured my splunk forwarder on my host OS to forward my host OS logs to splunk.

<h3>What skills I gained</h3>

- How SPL (Splunk Search Processing Language) works and how to use it to detect various events and incidents.
- How networking effects the working of chained operations.
- Saving queries and dashboards for later use and how to share them with senior management while having full control over who can see sensitive information like as a owner or as a user.
- Detection and dashboard creation of a specific incident, mapped with MITRE ATT&CK Framework and understand what things to look for in logs for IOC (indicators of compromise) and linking events back and forth. 
