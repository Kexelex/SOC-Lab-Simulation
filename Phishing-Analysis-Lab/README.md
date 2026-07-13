# Physhing Analysis Lab Findings 

<img width="800" height="450" alt="BTLO Banner" src="https://github.com/user-attachments/assets/94c2ac7b-153c-4017-92d7-ea8ee1d94015" />

 - Investigated a suspicious phishing email. 
 - Analyzed sender information, email content, and suspicious attachments. 
 - Identified Indicators of Compromise (IOCs).
 - Documented findings and security recommendations.

### Email Headers

   <img width="800" height="250" alt="image" src="https://github.com/user-attachments/assets/b42a4a94-47b2-4a42-92d0-4ecbd46dbe68" />

### Lab Environment & Source Used

| Component | Purpose |
| --- | --- |
| Ubuntu Desktop | Investigation Workstation |
| Terminal | Investigating files and performing hex dumps | 
| exiftool | Malicious attachment's meta data checker | 
| [BTLO Challenge](https://blueteamlabs.online/) | Simulated phishing scenario. |
| [Cyberchef](https://cyberchef.org/) | Data analysis and decoding platform. |
| [VirusTotal](https://www.virustotal.com/gui/home/upload) | IOC reputation lookup | 
| [File Signature Table](https://www.garykessler.net/library/file_sigs_GCK_latest.html) | To identify the signature and exact file type of the attachment. |
| [Any Run](https://app.any.run/) | Platform used to run the malicious attachment in a sandboxed environment. |
| [MITRE ATT&CK](https://attack.mitre.org/techniques/T1566/) | Phishing for initial access (T1566)

### Email Header Analysis

#### Objective 
The email headers were analyzed to verify the sender's authenticity, identify the origin of the message, examine email authentication results, and detect indicators commonly associated with phishing emails.

### Analysis Performed
The following email header fields were reviewed during the investigation:

 - From
 - Return-Path
 - Reply-To
 - Received headers
 - SPF authentication
 - Message-ID
 - MIME structure
 - Content-Type
 - Content-Transfer-Encoding

### Investigation Findings
#### Sender Information
###### The email claimed to originate from Bill using the address:
       billjobs@microapple.com
###### However, the Reply-To header pointed to a completely different email address:
       negeja3921@pashter.com

This mismatch indicates that any reply from the recipient would be sent to a different mailbox rather than the displayed sender, which is a common phishing technique.

#### SPF Authentication
###### The email failed Sender Policy Framework (SPF) validation.
       SPF = FAIL
The sending IP address was not authorized to send emails on behalf of the claimed sender domain (microapple.com), indicating possible sender spoofing.

#### Mail Server Analysis
###### The Received headers showed that the message originated from the IP address:
       93.99.104.210
The message was relayed through Google's mail infrastructure before reaching the recipient's inbox.\
Tracing the Received headers helps identify the origin of suspicious emails and validate the message delivery path.

#### Message-ID Analysis
###### The email contained the following Message-ID pattern:
       @localhost
Legitimate organizations typically generate Message-IDs that reference their own mail domains. The use of localhost is unusual for an externally delivered email and may indicate that the message was generated from a locally configured mail server rather than an organization's production mail infrastructure.

#### MIME Structure
The email used a multipart/mixed MIME format, indicating that the message contained one or more file attachments.
\
This was consistent with the phishing email encouraging the recipient to interact with an attached file.

#### Content Transfer Encoding
The email body used Base64 encoding.
\
Base64 is commonly used for transporting email content and attachments safely through mail systems. During the investigation, the encoded content was decoded to recover the original email body for analysis.

### Indicators Identified
| Indicators | Observation |
| --- | --- |
| Sender Display Name | Claimed to be "Bill" |
| From Address | billjobs@microapple.com |
| Reply-To Address | Different from sender (pashter.com) |
| SPF Result | Failed |
| Originating IP | 93.99.104.210 |
| MIME Type | multipart/mixed |
| Content Encoding | Base64 |
| Attachment Present | Yes |

### Attachment Investigation Process
A suspicious email claiming responsibility for the kidnapping of the President's daughter was received. The sender demanded a ransom in exchange for the victims' release and instructed the recipient to solve a puzzle attached to the email. The message contained informal language, emotional manipulation, and references to an attachment as the next step in the attack.

### Analysis Performed
  - Inspected the attachment's hexadecimal representation.
  - Verified the file signature (magic bytes) using CyberChef.
  - Compared the file signature against known file signatures.
  - Determined that the file contents did not match a standard PDF document.
  - The signature indicated that the attachment was actually a ZIP archive despite having a PDF extension.
  - The Base64-encoded data was decoded using CyberChef.
  - The decoded output was exported as a ZIP archive for further investigation.

### Attachment Analysis
After reviewing the email, the attached file was analyzed to verify whether its file type matched the advertised format.\
The attachment appeared to be a PDF document based on its file extension. To validate its actual file type, the file signature (magic bytes) was examined using CyberChef. After identifying the attachment as a ZIP archive, the archive was extracted in a sandboxed environment for further investigation.

##### The extracted archive contained three files:
| File | Purpose | 
| --- | --- |
| Image | Visual evidence |
| PDF document | Message from adversary |
| Excel workbook | Additional investigation artifacts |

#### Image Analysis
The image contained what appeared to be the victim's crown, supporting the claims made in the email and serving as visual evidence intended to increase the credibility of the message.

##### Findings
 - Image appeared consistent with the narrative presented in the email.
 - Used as psychological reinforcement to persuade the recipient.
 - No suspicious file signature mismatch was identified.

#### PDF Analysis
The PDF document contained additional instructions directing the investigator toward the remaining files contained within the archive.
##### FIndings
 - Continued the social engineering narrative established in the original email.
 - Directed attention toward the spreadsheet for additional information.
 - Contained no executable or active content during analysis.

#### Spreadsheet Analysis
The Excel workbook contained multiple worksheets requiring further examination. \
Initial inspection did not reveal any obvious indicators; therefore, additional analysis techniques were performed.

##### Analysis Performed
 - Verified the spreadsheet file signature to confirm the actual file type.
 - Reviewed all worksheets contained within the workbook.
 - Inspected workbook formatting and cell contents.
 - Selected all worksheet cells and cleared direct formatting to identify any concealed information.
 - Identified previously hidden data that had been camouflaged using formatting techniques.
 - The concealed data was found to be Base64 encoded.
 - Decoded the Base64 data using CyberChef for further analysis.

#### Sandbox Analysis
Before interacting extensively with the spreadsheet, the document was opened inside the Any.Run sandbox environment.
##### Purpose
 - Observe file behavior in an isolated environment.
 - Reduce the risk of executing potentially malicious content on the host system.
 - Verify whether the document attempted to perform suspicious actions.
##### Findings
 - The workbook was safely analyzed inside an isolated environment.
 - No direct impact to the investigation workstation occurred during analysis.

#### File Validation 
Every extracted file was validated using file signature analysis rather than relying solely on file extensions.
##### Verification Performed
 - Compared magic bytes against known file signatures.
 - Confirmed the actual file type for each extracted artifact.
 - No additional file extension mismatches were identified after extraction.

#### Investigation Findings
 - The original attachment used file extension masquerading to conceal its true format.
 - The archive contained multiple artifacts designed to guide the investigation.
 - Hidden information within the spreadsheet relied on formatting-based obfuscation rather than encryption.
 - Encoded data required additional decoding before meaningful information could be obtained.
 - An isolated sandbox environment was used to safely inspect potentially malicious documents.

### Security Assessment
The header analysis identified several indicators consistent with phishing activity:

 - SPF authentication failed, suggesting the sending server was not authorized to send email for the claimed domain.
 - The Reply-To address differed from the displayed sender, indicating an attempt to redirect responses.
 - The email originated from an external IP address rather than trusted mail infrastructure.
 - The use of a multipart MIME structure with an attachment aligned with the social engineering objectives of the message.
 - Base64-encoded content required decoding before analysis, highlighting the importance of inspecting encoded email content during phishing investigations.


