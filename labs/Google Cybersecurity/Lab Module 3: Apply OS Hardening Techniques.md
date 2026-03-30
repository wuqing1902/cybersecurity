# Lab Module 3: Apply OS Hardening Technique

## 1. Overview
This lab simulates a real-world cybersecurity incident where a production website, yummyrecipesforme.com, was compromised by a malicious actor.

As a cybersecurity analyst, I investigated the incident using network traffic analysis techniques, identified the attack vector, and provided remediation recommendations to prevent similar incidents.

---

## 2. Objectives
1. Analyze network traffic using tcpdump  
2. Identify network protocols involved in the attack  
3. Investigate and document a security incident  
4. Recommend mitigation strategies against brute force attacks  

---

## 3. Network Protocol Identified

**Protocol:** Hypertext Transfer Protocol (HTTP)

### 3.1 Justification
- The interaction between the user and the website occurred over HTTP  
- Packet capture logs showed HTTP requests when accessing the web server  
- The malicious file was delivered through HTTP responses  
- Redirection to a malicious domain also occurred via HTTP  

### 3.2 Supporting Evidence
- DNS queries resolved domain names into IP addresses  
- HTTP was used to:
  - Load the legitimate website  
  - Deliver the malicious executable file  
  - Redirect users to the malicious domain (greatrecipesforme.com)  

---

## 4. Incident Documentation

### 4.1 Initial Report
Multiple users reported that:
- They were prompted to download a file when visiting the website  
- Their systems slowed down after executing the file  
- They were redirected to a different and suspicious domain  

Additionally, the website administrator was unable to access the admin panel.

---

### 4.2 Investigation Process
To safely analyze the issue:
1. A sandbox environment was created  
2. Network traffic was captured using tcpdump  
3. The website was accessed in a controlled environment

Sample tcpdump logs:
```bash
12:34:56 IP 192.168.1.2.54321 > 8.8.8.8.53: DNS query A yummyrecipesforme.com
12:34:56 IP 8.8.8.8.53 > 192.168.1.2.54321: DNS response A 93.184.216.34
12:34:57 IP 192.168.1.2.54322 > 93.184.216.34.80: HTTP GET /index.html
12:34:58 IP 93.184.216.34.80 > 192.168.1.2.54322: HTTP 200 OK (malicious file download)
12:35:02 IP 192.168.1.2.54323 > 8.8.8.8.53: DNS query A greatrecipesforme.com
12:35:02 IP 8.8.8.8.53 > 192.168.1.2.54323: DNS response A 203.0.113.45
12:35:03 IP 192.168.1.2.54324 > 203.0.113.45.80: HTTP GET /index.html
````

---

### 4.3 Observed Behavior
1. A DNS request resolved yummyrecipesforme.com  
2. An HTTP request loaded the website  
3. A download prompt appeared for an executable file  
4. The file was executed  
5. A DNS request resolved greatrecipesforme.com  
6. The browser redirected to the malicious website via HTTP  

---

### 4.4 Root Cause Analysis
- The web server was compromised through a brute force attack  
- The attacker exploited a default administrator password  
- After gaining access:
  - Malicious JavaScript was injected into the website  
  - Users were prompted to download malware  
  - Administrator credentials were modified  

---

### 4.5 Network Traffic Analysis Summary

The following sequence represents the interpreted network activity observed during packet analysis:

1. The browser initiates a DNS request to resolve the IP address of yummyrecipesforme.com  
2. The DNS server responds with the corresponding IP address  
3. The browser sends an HTTP request to access the website  
4. The website prompts the download of a malicious executable file  
5. The browser initiates a DNS request for greatrecipesforme.com  
6. The DNS server responds with the IP address for the malicious domain  
7. The browser sends an HTTP request and is redirected to the malicious website

---

## 5. Impact Assessment
1. End users executed malicious software unknowingly  
2. Systems experienced performance degradation  
3. Website integrity was compromised  
4. Unauthorized administrative access occurred  

---

## 6. Recommendation

### 6.1 Implement Two-Factor Authentication (2FA)

Two-factor authentication adds an additional layer of security beyond passwords. Even if an attacker successfully obtains login credentials, access cannot be granted without the second authentication factor.

### 6.2 Effectiveness
1. Prevents unauthorized access using stolen credentials  
2. Reduces the success rate of brute force attacks  
3. Strengthens administrative account security  
4. Aligns with industry security best practices  

---

## 7. Skills Demonstrated
1. Network traffic analysis using tcpdump  
2. Understanding of TCP/IP model and protocols (DNS, HTTP)  
3. Security incident investigation and documentation  
4. Threat identification and root cause analysis  
5. Security control recommendation  

---

## 8. Tools and Concepts
1. tcpdump  
2. DNS (Domain Name System)  
3. HTTP (Hypertext Transfer Protocol)  
4. Sandbox environment analysis  
5. Brute force attack techniques  
6. Malware behavior analysis  

---

## 9. Conclusion
This lab demonstrates the importance of secure authentication practices, network monitoring, and layered security controls.

The investigation highlights how weak password policies and lack of access control mechanisms can lead to full system compromise.

---

## 10. Future Improvements
1. Implement login attempt rate limiting  
2. Enforce strong password policies  
3. Monitor and alert on suspicious login attempts  
4. Conduct regular security audits
