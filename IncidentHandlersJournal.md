# Scenario
A small U.S. health care clinic specializing in delivering primary-care services experienced a security incident on a Tuesday morning, at approximately 9:00 a.m. Several employees reported that they were unable to use their computers to access files like medical records. Business operations shut down because employees were unable to access the files and software needed to do their job.

Additionally, employees also reported that a ransom note was displayed on their computers. The ransom note stated that all the company's files were encrypted by an organized group of unethical hackers who are known to target organizations in healthcare and transportation industries. In exchange for restoring access to the encrypted files, the ransom note demanded a large sum of money in exchange for the decryption key. 

The attackers were able to gain access into the company's network by using targeted phishing emails, which were sent to several employees of the company. The phishing emails contained a malicious attachment that installed malware on the employee's computer once it was downloaded.

Once the attackers gained access, they deployed their ransomware, which encrypted critical files. The company was unable to access critical patient data, causing major disruptions in their business operations. The company was forced to shut down their computer systems and contact several organizations to report the incident and receive technical assistance.
# Journal entry
## Date: 07/02/2025
## Entry: #1
## Description: 
This entry is to document the incident that happened at a small U.S. health care clinic. 
## Tool(s) used:
Not applicable.
## The 5 W's:
### Who caused the incident?
An organized group of unethical hackers.
### What happened?
Business operations were severely disrupted after several computers in the network were basically inoperable. This is due to a ransomware taking place; the organized group of unethical hackers were able to gain access into the company's network by using a social engineering tactic known as phishing. Several computers has had their files encrypted, and the hackers demanded a large sum of money in exchange for the decryption key. Because of this, many employees could not do their jobs since they couldn't access important files (like medical records), and important software.
### When did the incident occur?
The incident took place on Tuesday, at 9:00 a.m.
### Where did the incident happen?
The incident happened at a small U.S. health care clinic.
### Why did the incident happen?
The incident happened because employees clicked on the malicious attachment in a phishing email from the group of hackers. This allowed them to access the company's systems and launch their ransomware.
### Additional notes:
- Employees need proper training on social engineering tactics.
- Better email filters likely needed.
- How did so many of them not determine that the email is likely malicious?
---
# Scenario
You are a level one security operations center (SOC) analyst at a financial services company. You have received an alert about a suspicious file being downloaded on an employee's computer. 

You investigate this alert and discover that the employee received an email containing an attachment. The attachment was a password-protected spreadsheet file. The spreadsheet's password was provided in the email. The employee downloaded the file, then entered the password to open the file. When the employee opened the file, a malicious payload was then executed on their computer.

You retrieve the malicious file and create a SHA256 hash of the file. Now that you have the file hash, you will use VirusTotal to uncover additional IoCs that are associated with the file.
## Details of the alert
The following information contains details about the alert. The details include a file hash and a timeline of the event.

SHA256 file hash: 54e6ea47eb04634d3e87fd7787e2136ccfbcc80ade34f246a12cf93bab527f6b

Here is a timeline of the events leading up to this alert:

- 1:11 p.m.: An employee receives an email containing a file attachment.

- 1:13 p.m.: The employee successfully downloads and opens the file.

- 1:15 p.m.: Multiple unauthorized executable files are created on the employee's computer.

- 1:20 p.m.: An intrusion detection system detects the executable files and sends out an alert to the SOC.
 # Journal entry
## Date: 07/16/2025
## Entry: #2
## Description:
This entry is to document an incident where an employee compromised their computer due to a phishing attack.
## Tool(s) used:
1. VirusTotal.
## The 5 W's:
### Who caused the incident?
The malicious actor that sent the phishing email.
### What happened?
An employee's computer was compromised after opening a suspicious file from a phishing email. After the damage was done, the intrusion detection system alerted me about suspicious executable files being downloaded and opened.
### When did the incident occur?
The incident occured around 1:11 p.m. when the employee first received the phishing email.
### Where did the incident happen?
The incident happened at the employee's computer.
### Why did the incident happen?
The incident happened because the employee opened the file without first determining whether the email was suspicious in the first place or not. The email contained various errors, indicating red flags. However, the employee still downloaded the file, entered the password to unlock the password protected malicious file, and got their computer compromised.
### Additional notes:
- VirusTotal determined that the file is malicious. 58 out of 72 vendors deemed the file malicious. The community score is also well in the negative 250s.
- The file has been identified as being a malware known as "Flagpro".
---
# Scenario
You recently joined the security team as a level-one security operation center (SOC) analyst at a mid-sized retail company. Along with its physical store locations, your company also conducts operations in e-commerce, which account for 80% of its sales.

You are spending your first week of training becoming familiar with the company's security processes and procedures. Recently, the company experienced a major security incident involving a data breach of over one million users. Because this was a recent and major security incident, your team is working to prevent incidents like this from happening again. This breach happened before you began working at the company. You have been asked to review the final report.
# Journal entry
## Date: 07/22/2025
## Entry: #3
## Description: 
Reviewing a final report of an incident. Post-incident activity.
## Tool(s) used: 
N/A
## The 5 W's:
### Who caused the incident?
An external malicious actor.
### What happened?
A security received an alert from an employee who received two emails from the malicious actor saying they have extracted confidential customer data. The malicious actor asked that the company pay a ransom otherwise the data will be public.
### When did the incident occur?
The first email was received on December 22, 2022, at 3:13 p.m. PT. It is likely the incident occured sometime prior to this.
### Where did the incident happen?
It happened in the e-commerce web application.
### Why did the incident happen?
The incident happened because of a vulnerability in the e-commerce web application. This vulnerability allowed the attacker to perform a forced browsing attack and access customer transaction data by modifying the order number included in the URL string of a purchase confirmation page. This vulnerability allowed the attacker to access customer purchase confirmation pages, exposing customer data, which the attacker then collected and exfiltrated.