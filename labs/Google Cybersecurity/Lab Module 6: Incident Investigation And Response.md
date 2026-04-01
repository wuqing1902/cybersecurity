# Lab Module 6: Incident Investigation And Response

## Overview
This lab demonstrates practical skills in incident investigation, threat intelligence analysis, and incident response using industry-relevant tools and frameworks. The activities simulate real-world Security Operations Center (SOC) workflows, including malware analysis, phishing investigation, and post-incident reporting.

The lab is structured into three main activities:
1. Investigating a suspicious file hash using VirusTotal
2. Responding to a phishing incident using a playbook
3. Reviewing a final incident report to extract key insights and recommendations

---

## Objectives
- Analyze malicious artifacts using threat intelligence platforms  
- Identify and classify Indicators of Compromise (IoCs)  
- Apply structured incident response using a phishing playbook  
- Evaluate security incidents using the NIST Incident Response Lifecycle  
- Develop professional documentation for incident handling and reporting  

---

## Tools and Frameworks Used
- VirusTotal (Threat Intelligence Platform)  
- Pyramid of Pain (IoC classification model)  
- Phishing Incident Response Playbook  
- NIST Incident Response Lifecycle  
- MITRE ATT&CK Framework  

---

## Activity 1: Investigate a Suspicious File Hash

### Summary
A suspicious file downloaded via an email attachment was analyzed using VirusTotal. The SHA256 hash was used to determine whether the file was malicious and to uncover related indicators of compromise (IoCs).

### Findings
- The file was confirmed malicious, with detections from multiple security vendors  
- High detection rate across antivirus engines in VirusTotal  
- Negative community score indicating consensus of malicious behavior  
- The malware exhibits harmful behavior upon execution  
- Unauthorized system changes were observed, triggering security alerts  

### Observed Behavior
- Executes unauthorized processes on the host system  
- Establishes outbound connections to external IP addresses  
- Sends HTTP requests to a malicious domain  
- May perform input capture to collect sensitive user information  

### Indicators of Compromise (IoCs)
- Hash Value:  
  SHA256: `54e6ea47eb04634d3e87fd7787e2136ccfbcc80ade34f246a12cf93bab527f6b`  
  MD5: `287d612e29b71c90aa54947313810a25`

- IP Address:  
  `207.148.109.242`

- Domain Name:  
  `org.misecure.com`

- Network Artifact:  
  HTTP requests to a malicious domain

- Tool Used by Attacker:  
  Input capture (credential/data harvesting)

- TTP Identified:  
  Command and Control (C2 communication)

### IoC Classification (Pyramid of Pain)
- Hash Value: SHA256, MD5  
- IP Address: 207.148.109.242  
- Domain Name: org.misecure.com  
- Network Artifact: HTTP communication  
- Tool: Input capture  
- TTP: Command and Control

---

## Activity 2: Phishing Incident Response

### Summary
A phishing alert was investigated using an organizational playbook. The email contained a malicious attachment (`bfsvc.exe`) which had already been verified as malicious.

### Key Observations
- Suspicious sender address and IP (`114.114.114.114`)  
- Mismatch between sender identity and email content  
- Grammatical errors in subject and message body  
- Password-protected attachment (evasion technique)  
- Executable file disguised as a resume  

### Response Actions
- Verified malicious file hash using threat intelligence tools  
- Identified phishing characteristics in the email  
- Followed playbook procedures for escalation  

### Justification / Evidence
- Confirmed malicious attachment  
- Clear indicators of phishing attempt  
- Potential system compromise due to file execution
- Sender's email "76tguyhh6tgftrt7tg.su" does not match the displayed name "Def Communications"  
- Email body and subject contain grammatical errors  
- Attachment "bfsvc.exe" is password-protected and confirmed malicious via SHA256 hash  
- Executable disguised as a resume, downloaded and opened by the user  
- Alert severity Medium, indicating potential organizational impact  

### 5 W's of the Incident
- **Who:** Unknown external attacker sending phishing emails  
- **What:** Employee downloaded and opened a malicious file attachment  
- **When:** Wednesday, July 20, 2022, 09:30 AM (email received)  
- **Where:** HR department employee workstation  
- **Why:** Attempt to deliver malware and potentially compromise sensitive systems

### Escalation Summary
Based on the investigation and evidence, the ticket was escalated to a level-two SOC analyst for further investigation, following the organization's phishing playbook. This ensures prompt containment and reduces risk of malware spreading across the network.

### Final Decision
- Ticket Status: Escalated  

---

## Activity 3: Review of Incident Final Report

### Incident Type
- Data breach involving unauthorized access to customer PII and financial data  

### Root Cause
- Vulnerability in the e-commerce web application  
- Exploited through a forced browsing attack  

### Attack Method
- Manipulation of URL parameters to access restricted customer data  

### Incident Timeline
| Date | Event |
|------|-------|
| Dec 22, 2022 | Initial extortion email received and ignored |
| Dec 28, 2022 | Second email received with proof of data breach |
| Dec 28, 2022 | Incident reported to the security team |
| Dec 28–31, 2022 | Investigation conducted and vulnerability identified |

### Response Actions
- Analyzed web server logs to identify abnormal access patterns  
- Investigated sequential customer order access to determine data exfiltration  
- Coordinated with public relations for customer notification  
- Provided identity protection services to affected customers  

### Recommendations
- Perform routine vulnerability scans and penetration testing  
  *→ Detect vulnerabilities before attackers exploit them*  
- Implement stronger access control mechanisms:
  - URL allowlisting  
    *→ Restricts access to authorized pages only*  
  - Authentication enforcement  
    *→ Ensures only verified users can access sensitive data*

### Lessons Learned
- Prompt response to phishing/extortion emails is critical to limit potential damage  
- Strong access control and monitoring prevent unauthorized access to sensitive data  
- Post-incident documentation and reporting improve organizational security posture and future prevention

---

## Reflection
This lab provided hands-on experience in analyzing real-world security incidents using structured methodologies. It strengthened my understanding of how threat intelligence tools support malware analysis and how indicators of compromise can be classified using the Pyramid of Pain.

Applying a phishing playbook highlighted the importance of standardized incident response procedures. Additionally, reviewing the final report emphasized how unpatched vulnerabilities in web applications can lead to significant data breaches.

---

## Conclusion
Through this lab, I developed practical skills in:
- Malware analysis  
- Phishing detection and response  
- Incident investigation and escalation  
- Security reporting and documentation  

These competencies are essential for a Security Operations Center (SOC) analyst and contribute to improving an organization's ability to detect, respond to, and prevent cybersecurity incidents.

