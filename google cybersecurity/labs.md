# Lab Module 2: Internal IT Audit Documentation – Botium Toys

This lab documents an internal IT audit conducted on Botium Toys. The purpose is to evaluate the organization’s security posture, identify risks, assess controls, check compliance, and provide recommendations to improve overall security.

---

## 1. Audit Scope and Goals

**Scope:**  
- Entire security program at Botium Toys.  
- Assessment of all assets, systems, internal processes, and controls.  
- Review of compliance with regulatory standards and best practices.

**Goals:**  
- Assess existing assets and internal controls.  
- Identify gaps in security controls and compliance adherence.  
- Recommend improvements to mitigate high-risk vulnerabilities.  
- Align with the **NIST Cybersecurity Framework (CSF)** and industry best practices.  

---

## 2. Risk Assessment

### Current Assets
- Employee equipment: desktops, laptops, smartphones, peripherals, remote workstations, docking stations, headsets.  
- Internal network: storage of customer, vendor, and organizational data.  
- Storefront products: on-site and online inventory.  
- Systems/software: accounting, database, telecommunication, ecommerce, inventory management.  
- Internet access, legacy system maintenance, and data retention/storage.

### Risk Description
- Inadequate asset management.  
- Lack of proper controls (technical, administrative, and physical).  
- Employees have access to sensitive customer data including PII/SPII and cardholder information.  
- Encryption is not applied for sensitive data.  
- No disaster recovery plans or intrusion detection system (IDS).  

### Control Best Practices
- Dedicate resources to identify and classify assets.  
- Implement controls to reduce likelihood of breaches.  
- Evaluate business impact if assets or systems are lost.  
- Maintain compliance with GDPR, PCI DSS, and SOC standards.

### Risk Score
- **8/10 (High risk)** due to lack of controls and insufficient adherence to compliance standards.  
- **Comments:** High risk of data loss or regulatory penalties if corrective actions are not implemented.  

---

## 3. Control Categories

| Category | Examples | Purpose |
|----------|---------|--------|
| **Administrative/Managerial** | Password policies, least privilege, account management, separation of duties | Define responsibilities and policies to manage data and protect assets |
| **Technical** | Firewalls, IDS/IPS, antivirus, encryption, backups, password management | Prevent, detect, or correct security incidents |
| **Physical** | Locks, CCTV, alarm systems, safes, lighting | Limit unauthorized physical access to assets |

**Control Types:**  
- **Preventative:** Prevent incidents (e.g., firewall, password policy).  
- **Detective:** Identify incidents (e.g., IDS, CCTV).  
- **Corrective:** Restore assets after incidents (e.g., backups, disaster recovery).  
- **Deterrent:** Discourage attacks (e.g., signage, locks, safes).  

---

## 4. Controls Assessment Checklist

| Yes | No | Control | Explanation |
|-----|----|---------|-------------|
|     | X  | Least Privilege | All employees have access to customer/internal data; privileges need limiting. |
|     | X  | Disaster recovery plans | No plans in place; needed for business continuity. |
|     | X  | Password policies | Minimal requirements; higher complexity needed. |
|     | X  | Separation of duties | CEO currently manages multiple critical operations; risk of insider threats/fraud. |
| X   |    | Firewall | Blocks traffic according to defined rules. |
|     | X  | IDS | Not implemented; needed for intrusion detection. |
|     | X  | Backups | Critical data not backed up; needed for recovery. |
| X   |    | Antivirus software | Installed and monitored regularly. |
|     | X  | Manual monitoring & legacy system maintenance | Monitoring exists but not scheduled; intervention unclear. |
|     | X  | Encryption | Not implemented; needed to secure sensitive info. |
|     | X  | Password management system | Not implemented; would improve productivity. |
| X   |    | Locks (offices/storefront/warehouse) | Physical locations secured. |
| X   |    | CCTV surveillance | Installed and functioning. |
| X   |    | Fire detection/prevention | Functional fire alarm and sprinkler systems. |

---

## 5. Compliance Checklist

| Standard | Yes | No | Best Practice | Explanation |
|----------|-----|----|---------------|-------------|
| PCI DSS |     | X  | Only authorized users access credit card info | All employees currently have access to internal data. |
| PCI DSS |     | X  | Data accepted, processed, transmitted, and stored securely | Encryption missing; all employees can access sensitive info. |
| PCI DSS |     | X  | Implement encryption for transactions | Not implemented; needed for confidentiality. |
| PCI DSS |     | X  | Adopt secure password management policies | Password policies minimal; no management system. |
| GDPR | X   |    | Notify E.U. customers within 72 hours of breach | Plan exists and enforced. |
| GDPR |     | X  | Keep E.U. customer data private/secured | Encryption missing; data confidentiality at risk. |
| GDPR |     | X  | Properly classify and inventory data | Assets listed but not classified. |
| GDPR | X   |    | Enforce privacy policies and procedures | Policies enforced among IT staff and employees. |
| SOC 1 & SOC 2 |     | X  | User access policies | Least Privilege and Separation of Duties missing. |
| SOC 1 & SOC 2 |     | X  | Sensitive data confidential/private | Encryption missing. |
| SOC 1 & SOC 2 | X   |    | Data integrity ensured | Measures are in place. |
| SOC 1 & SOC 2 |     | X  | Data available to authorized users | Needs restriction to authorized personnel only. |

---

## 6. Recommendations

- Implement **critical administrative controls**: Least Privilege, Separation of Duties, Disaster Recovery Plans, Password Policies.  
- Deploy **technical controls**: IDS, Encryption, Password Management System, Regular Legacy System Monitoring.  
- Maintain and strengthen **physical controls**: Locks, CCTV, Fire Detection/Prevention.  
- Improve **compliance**: GDPR, PCI DSS, and SOC adherence; classify assets and enforce encryption and access restrictions.  
- Overall, addressing these gaps will **reduce risks**, protect sensitive information, and improve Botium Toys’ security posture.

---

## 7. Reflection

Conducting this audit reinforced the importance of a **holistic cybersecurity approach**, combining administrative, technical, and physical controls. I learned to:  

- Identify and classify assets, evaluate risks, and assign risk scores.  
- Assess existing controls and determine gaps in practice.  
- Apply compliance frameworks (GDPR, PCI DSS, SOC) in a practical scenario.  
- Provide actionable recommendations to improve security posture and business continuity.  

This lab demonstrates **practical application of cybersecurity principles**, problem-solving, and analytical thinking—skills that are directly relevant for professional roles in IT security.










# Lab Module 3: Analyze Network Layer Communication

## 1. Objective
The objective of this lab is to analyze network traffic using `tcpdump` to identify issues related to DNS and ICMP communication. The goal is to determine why users are receiving a **“destination port unreachable”** error when attempting to access a website.

---

## 2. Tools Used
- tcpdump (Network Protocol Analyzer)
- DNS Protocol
- ICMP Protocol

---

## 3. Scenario Overview
Users reported that they were unable to access the website **yummyrecipesforme.com** and encountered the error message **“destination port unreachable.”**  

As a cybersecurity analyst, I used `tcpdump` to capture and analyze network traffic while attempting to access the website.

---

## 4. Captured tcpdump Log

```bash
13:24:32.192571 IP 192.51.100.15.35084 > 203.0.113.2.domain: 35084+ A? yummyrecipesforme.com. (28)
13:24:32.192600 IP 192.51.100.15.35084 > 203.0.113.2.domain: 35084+ A? yummyrecipesforme.com. (28)

13:24:32.193400 IP 203.0.113.2 > 192.51.100.15: ICMP 203.0.113.2 udp port 53 unreachable, length 92
13:24:32.193420 IP 203.0.113.2 > 192.51.100.15: ICMP 203.0.113.2 udp port 53 unreachable, length 92

13:24:32.194100 IP 192.51.100.15.35084 > 203.0.113.2.domain: 35084+ A? yummyrecipesforme.com. (28)
13:24:32.194130 IP 203.0.113.2 > 192.51.100.15: ICMP 203.0.113.2 udp port 53 unreachable, length 92
```

---

## 5. Traffic Analysis Findings

### a. Protocols Identified
- **UDP (DNS):** Used to send requests to the DNS server for domain name resolution  
- **ICMP:** Used to return error messages when communication fails  

---

### b. Log Analysis Summary
- The client system (**192.51.100.15**) sent DNS queries via UDP to the DNS server (**203.0.113.2**) on **port 53**  
- Each request included an **“A?” flag**, indicating a request for an A record (domain-to-IP mapping)  
- Instead of receiving a valid DNS response, the server returned: "ICMP: udp port 53 unreachable"
- Multiple attempts produced the same error, confirming the issue is persistent  

---

### c. Key Observations
- **Port 53** is used for DNS services  
- The DNS server responded with ICMP errors instead of DNS replies  
- The repeated failures indicate that the DNS service is **not reachable or not functioning properly**

---

## 6. Incident Timeline
- **Time Detected:** ~13:24 (1:24 p.m.) based on tcpdump logs  
- **Initial Trigger:** Users reported inability to access the website  
- **Detection Method:** Packet analysis using tcpdump  

---

## 7. Investigation Process
1. Attempted to access the website and reproduced the error  
2. Captured network traffic using `tcpdump`  
3. Identified DNS requests sent via UDP  
4. Observed ICMP error responses indicating **port 53 unreachable**  
5. Verified repeated failure across multiple attempts  

---

## 8. Root Cause Analysis

### Likely Causes:
- **DNS server is down or not running**
- **Firewall is blocking traffic on port 53**
- **Misconfiguration of DNS service**
- Possible **Denial of Service (DoS) attack** affecting the DNS server  

---

## 9. Conclusion
The issue is caused by a failure in DNS communication. The client is unable to retrieve the IP address of the domain because **UDP port 53 on the DNS server is unreachable**. This prevents successful domain resolution, resulting in users being unable to access the website.

---

## 10. Recommended Next Steps
- Verify that the DNS server is running and properly configured  
- Check firewall rules to ensure port 53 is not blocked  
- Monitor for unusual traffic patterns indicating a DoS attack  
- Restart or reconfigure DNS services if necessary  

---

## 11. Skills Demonstrated
- Network traffic analysis using tcpdump  
- Understanding of TCP/IP protocols (UDP, ICMP, DNS)  
- Log interpretation and incident investigation  
- Root cause analysis in cybersecurity incidents










# Lab Module 3: Analyzing Network Attacks Using Wireshark

## 1. Overview

In this lab, we analyzed a cybersecurity incident involving a travel agency's website. The website experienced connection timeouts, preventing employees and customers from accessing its sales pages. Using Wireshark logs, we identified the type of network attack, examined its impact, and explained how it disrupted the web server's functionality.  

---

## 2. Scenario

You work as a security analyst for a travel agency that advertises vacation packages on its website. One afternoon, automated alerts indicate a problem with the web server. When attempting to access the site, you receive a connection timeout error.  

A packet sniffer captures network traffic, revealing a large number of TCP SYN requests from an unfamiliar IP address. The web server is overwhelmed by the volume of requests, causing legitimate employee connections to fail.  

---

## 3. ## Example Wireshark Log (TCP/HTTP)

| No.  | Time       | Source       | Destination | Protocol | Info                                | Status |
|------|------------|--------------|-------------|---------|-------------------------------------|--------|
| 47   | 3.144521   | 198.51.100.23 | 192.0.2.1  | TCP     | 42584->443 [SYN] Seq=0 Win=5792 Len=120 | 🟢 Normal |
| 48   | 3.195755   | 192.0.2.1   | 198.51.100.23 | TCP   | 443->42584 [SYN, ACK] Seq=0 Win=5792 Len=120 | 🟢 Normal |
| 49   | 3.246989   | 198.51.100.23 | 192.0.2.1  | TCP     | 42584->443 [ACK] Seq=1 Win=5792 Len=120 | 🟢 Normal |
| 50   | 3.298223   | 198.51.100.23 | 192.0.2.1  | HTTP    | GET /sales.html HTTP/1.1            | 🟢 Normal |
| 51   | 3.349457   | 192.0.2.1   | 198.51.100.23 | HTTP   | HTTP/1.1 200 OK (text/html)         | 🟢 Normal |
| 52   | 3.390692   | 203.0.113.0 | 192.0.2.1  | TCP     | 54770->443 [SYN] Seq=0 Win=5792 Len=0 | 🔴 Attack |
| 53   | 3.441926   | 192.0.2.1   | 203.0.113.0 | TCP     | 443->54770 [SYN, ACK] Seq=0 Win=5792 Len=120 | 🔴 Attack |
| 54   | 3.493160   | 203.0.113.0 | 192.0.2.1  | TCP     | 54770->443 [ACK] Seq=1 Win=5792 Len=0 | 🔴 Attack |
| 55   | 3.544394   | 198.51.100.14 | 192.0.2.1 | TCP     | 14785->443 [SYN] Seq=0 Win=5792 Len=120 | 🟢 Normal |
| 56   | 3.599628   | 192.0.2.1   | 198.51.100.14 | TCP   | 443->14785 [SYN, ACK] Seq=0 Win=5792 Len=120 | 🟢 Normal |
| 77   | 7.330577   | 192.0.2.1   | 198.51.100.5 | HTTP   | HTTP/1.1 504 Gateway Time-out (text/html) | 🟡 Timeout/Error |

---

## 4. Analysis of Network Traffic

### Normal TCP/HTTP Traffic

A normal connection between an employee visitor and the web server involves a **three-way handshake** using TCP:

| Step | Description |
|------|-------------|
| 1. SYN | Visitor sends a synchronize packet to initiate connection. |
| 2. SYN-ACK | Server acknowledges the request and reserves resources. |
| 3. ACK | Visitor confirms the connection; communication proceeds. |

Once established, the HTTP protocol is used for web page requests:
Employee → Server: GET /sales.html HTTP/1.1
Server → Employee: HTTP/1.1 200 OK (text/html)


---

### Indicators of the Attack

The Wireshark log shows abnormal patterns:

- Repeated SYN packets from the attacker IP `203.0.113.0`.
- Legitimate employee traffic (e.g., `198.51.100.14`) is initially processed but later fails.
- Failed communications highlighted as yellow in the logs indicate `[RST, ACK]` packets or HTTP `504 Gateway Time-out` errors.

These symptoms indicate that the server was **overloaded with SYN requests**, exhausting resources needed for legitimate connections.

---

## 5. Identification of the Attack

Based on the traffic patterns:

- **Attack Type:** Direct Denial of Service (DoS)  
- **Specific Variant:** SYN Flood Attack

**Evidence:**

1. Single attacking IP address sending repeated SYN packets.  
2. Server becomes unable to respond to legitimate connection requests.  
3. Logs show resource exhaustion leading to timeout errors for employees.  

---

## 6. How the Attack Works

1. **SYN Flood Attack** exploits the TCP handshake by sending a high volume of SYN packets to the server.  
2. Each SYN request consumes server resources in anticipation of completing the handshake.  
3. When server resources are exhausted, legitimate SYN requests cannot be processed, resulting in connection failures.  

**Impact on the website:**

- Employees cannot access the sales webpage.  
- Browsers display connection timeout errors.  
- Web server becomes unresponsive to all incoming requests from legitimate users.  

---

## 7. Consequences

- Disrupted business operations due to inaccessible website.  
- Negative user experience for customers.  
- Potential financial and reputational losses for the organization.  

---

## 8. Mitigation Strategies

To reduce the risk of future SYN flood attacks:

- Implement **rate limiting** and **connection throttling**.  
- Configure **firewall rules** to detect and block malicious IPs.  
- Use **SYN cookies** to manage TCP handshake resources efficiently.  
- Deploy **DDoS protection services** if facing large-scale distributed attacks.  

---

<!--
## 9. References

- Microsoft. *Introduction to Network Trace Analysis.*  
- Wireshark Documentation: [https://www.wireshark.org/docs/](https://www.wireshark.org/docs/)
-->











# Lab Module 3: Apply OS Hardening Technique

## Overview
In this lab, you assume the role of a cybersecurity analyst investigating a security incident for **yummyrecipesforme.com**, a website hosting recipes and cookbooks. Visitors experienced a security issue when accessing the main webpage. The objective of this lab is to:

1. Identify the network protocol involved in the incident.
2. Document the incident in detail.
3. Recommend a security measure to prevent future attacks.

A former employee executed a brute force attack to gain administrative access and modified the website to distribute malware. Visitors were redirected to a malicious website, **greatrecipesforme.com**, after downloading a disguised executable file.

---

## Section 1: Identify the Network Protocol

The primary protocol identified during the investigation is the **Hypertext Transfer Protocol (HTTP)**. HTTP is used to request and receive web content, including the malicious file downloaded by users. Additionally, the **Domain Name System (DNS)** protocol is observed in the logs, which resolves website URLs to IP addresses.

**Evidence from tcpdump logs:**
```bash
12:34:56 IP 192.168.1.2.54321 > 8.8.8.8.53: DNS query A yummyrecipesforme.com
12:34:56 IP 8.8.8.8.53 > 192.168.1.2.54321: DNS response A 93.184.216.34
12:34:57 IP 192.168.1.2.54322 > 93.184.216.34.80: HTTP GET /index.html
12:34:58 IP 93.184.216.34.80 > 192.168.1.2.54322: HTTP 200 OK (malicious file download)
12:35:02 IP 192.168.1.2.54323 > 8.8.8.8.53: DNS query A greatrecipesforme.com
12:35:02 IP 8.8.8.8.53 > 192.168.1.2.54323: DNS response A 203.0.113.45
12:35:03 IP 192.168.1.2.54324 > 203.0.113.45.80: HTTP GET /index.html
```

**Analysis:**

- The browser initially queries the DNS server for **yummyrecipesforme.com**, receives the IP address, and initiates an HTTP request to access the website.  
- The user is prompted to download an executable file via HTTP.  
- After execution, the browser queries the DNS server for **greatrecipesforme.com** and connects via HTTP, indicating redirection to a malicious site.  

---

## Section 2: Incident Documentation

**Summary of the Incident:**

- Multiple customers reported that visiting **yummyrecipesforme.com** prompted them to download an executable file claiming to provide free recipes.  
- The downloaded file caused their computers to slow down and redirected their browsers to **greatrecipesforme.com**.  
- The website owner was locked out of the admin panel and contacted the hosting provider.  

**Investigation Steps:**

1. A sandbox environment was created to safely interact with the suspicious website.  
2. The analyst ran **tcpdump** to capture network traffic while visiting the website.  
3. The executable file was downloaded and executed in the sandbox, confirming malicious redirection.  
4. DNS and HTTP logs indicated requests to **yummyrecipesforme.com** and subsequent redirection to **greatrecipesforme.com**.  
5. Source code inspection revealed embedded JavaScript that prompted file downloads.  

**Analysis and Findings:**

- The attacker performed a **brute force attack** on the administrative account, exploiting a default password and absence of login attempt controls.  
- Malicious JavaScript modified the website to deliver an executable file that redirected users to a fake website.  
- The security incident compromised end users’ computers and the integrity of the web server.

**Sources of Evidence:**

- TCP/IP traffic captured via **tcpdump**  
- Website source code analysis  
- Customer reports and hosting provider feedback  

---

## Section 3: Recommended Security Measure

**Recommendation:** Implement **Two-Factor Authentication (2FA)** for all administrative accounts.  

**Rationale:**

- The brute force attack succeeded because the admin password was predictable and no additional verification was required.  
- 2FA adds a second layer of authentication, requiring a one-time passcode (OTP) sent to the user’s phone or email.  
- Even if a password is compromised, an attacker cannot access the account without the OTP.  

**Additional Recommendations (supportive):**

- Enforce strong, non-default passwords  
- Require regular password updates  
- Limit login attempts to mitigate brute force attacks  

Implementing these measures will significantly reduce the likelihood of unauthorized administrative access and protect both the website and its users.

---

## Conclusion

This lab reinforced the importance of **network protocol analysis**, **incident documentation**, and **preventive security measures**. Proper investigation and reporting allow cybersecurity analysts to identify the root cause, mitigate threats, and implement safeguards to prevent future incidents.  

---

## References

- TCP/IP Model and Network Protocols  
- How to interpret **tcpdump** logs  
- Best practices for **web server hardening** and **brute force attack mitigation**












# Lab Module 3: Incident Report Analysis – NIST Cybersecurity Framework (CSF) Application

## 1. Overview
This lab demonstrates the analysis of a network security incident using the National Institute of Standards and Technology (NIST) Cybersecurity Framework (CSF).  

A multimedia company experienced a Distributed Denial of Service (DDoS) attack caused by an incoming flood of ICMP packets. The attack disrupted internal network services for two hours, preventing normal operations. The cybersecurity team responded to contain the incident, restored critical services, and analyzed the vulnerability that enabled the attack.

---

## 2. Objectives
1. Summarize the security event  
2. Identify the type of attack and impacted systems  
3. Implement protective measures to prevent similar attacks  
4. Detect potential security threats using monitoring tools  
5. Develop a response plan for future incidents  
6. Outline recovery strategies to restore systems and services  

---

## 3. Summary of Security Event
- **Event:** All internal network services suddenly stopped responding  
- **Cause:** DDoS attack via a flood of ICMP packets  
- **Impact:** Disruption of all internal network services; critical systems temporarily unavailable  
- **Response:** Incoming ICMP traffic was blocked, non-critical services were stopped, and critical services were restored  

---

## 4. Identify – Attack and Affected Systems
1. **Type of Attack:** DDoS attack using ICMP floods  
2. **Targeted Systems:** Entire internal network, including critical servers and network resources  
3. **Scope:** Network-wide disruption; incoming ICMP traffic exploited unconfigured firewall rules  
4. **Actor:** Malicious external actor(s) leveraging the unprotected network  

---

## 5. Protect – Security Measures Implemented
1. **Firewall Rules:** New rule to limit the rate of incoming ICMP packets  
2. **IDS/IPS System:** Filter ICMP traffic based on suspicious characteristics  
3. **Network Security Policies:** Updated to enforce stricter control on incoming traffic  
4. **Continuous Staff Awareness:** Security team trained to respond to unusual traffic patterns  

---

## 6. Detect – Monitoring Methods
1. **Source IP Verification:** Firewall configured to check for spoofed IP addresses  
2. **Network Monitoring Software:** Detect abnormal traffic patterns in real time  
3. **Intrusion Detection System (IDS):** Monitors for suspicious activities and alerts the security team  

---

## 7. Respond – Response Plan for Future Incidents
1. **System Isolation:** Affected systems will be isolated to prevent further disruption  
2. **Restoration of Critical Services:** Critical network resources restored first  
3. **Incident Analysis:** Network logs analyzed to identify suspicious activity and attack patterns  
4. **Reporting:** All incidents documented and reported to management and, if applicable, legal authorities  

---

## 8. Recover – Recovery Plan
1. **Restore Network Services:** Bring all critical services online first, followed by non-critical systems  
2. **Firewall Enforcement:** Block external ICMP flood attacks at the firewall  
3. **Traffic Management:** Temporarily stop non-critical services during future attacks to reduce network load  
4. **Post-Incident Review:** Analyze the incident and implement improvements to prevent recurrence  

---

## 9. Skills Demonstrated
1. Incident analysis using NIST CSF framework  
2. Identification of network vulnerabilities and threats  
3. Implementation of security monitoring and detection tools  
4. Development of response and recovery plans  
5. Professional documentation and reporting of cybersecurity incidents  

---

## 10. Tools and Concepts Used
1. Firewalls and firewall rules  
2. Intrusion Detection and Prevention Systems (IDS/IPS)  
3. Network monitoring and traffic analysis software  
4. DDoS attack mitigation strategies  
5. NIST Cybersecurity Framework (CSF) for incident management  

---

## 11. Conclusion
The DDoS attack highlighted the importance of proactive network monitoring, proper firewall configuration, and rapid incident response. Applying the NIST CSF allowed the cybersecurity team to systematically identify, protect, detect, respond, and recover from the incident.  

Implementing these measures ensures better preparedness for future attacks and strengthens the organization’s overall security posture.

---

## 12. Reflections/Notes
- Continuous monitoring is critical for early detection of unusual network behavior  
- Staff training on cybersecurity awareness reduces the risk of accidental misconfigurations  
- Post-incident reviews allow the organization to learn from incidents and update policies accordingly












# Lab Module 3: Network Hardening Analysis – Security Risk Assessment

## 1. Overview
This lab demonstrates the assessment of network vulnerabilities and the application of network hardening techniques to secure a social media organization's network. 

The organization recently experienced a data breach that compromised personal information, such as user names and addresses. As a cybersecurity analyst, I identified vulnerabilities and recommended security hardening practices to reduce the likelihood of future attacks.

---

## 2. Objectives
1. Identify key network vulnerabilities  
2. Select appropriate network hardening tools and methods  
3. Explain the effectiveness of chosen hardening practices  
4. Document recommendations for network security improvements  

---

## 3. Identified Vulnerabilities
The organization’s network was assessed and the following vulnerabilities were discovered:

1. Employees share passwords  
2. Database administrator account uses default credentials  
3. Firewalls lack rules to filter inbound and outbound traffic  
4. Multifactor authentication (MFA) is not implemented  

If left unaddressed, these vulnerabilities could lead to repeated data breaches and unauthorized network access.

---

## 4. Recommended Network Hardening Tools and Methods

### 4.1 Multi-Factor Authentication (MFA)
- Requires users to provide more than one form of authentication, such as passwords, PINs, ID cards, or biometric scans  
- Reduces the likelihood that unauthorized actors can access the network  
- Discourages password sharing by making single-password access insufficient  

### 4.2 Strong Password Policies
- Enforce password length, complexity, and rotation  
- Prevent password reuse and implement lockouts after multiple failed login attempts  
- Helps prevent brute force attacks and unauthorized access  

### 4.3 Firewall Maintenance
- Regularly review and update firewall rules to reflect current security standards  
- Deny traffic from suspicious or malicious sources  
- Protects the network against unauthorized access, DoS, and DDoS attacks  

---

## 5. Effectiveness of Recommendations

1. **MFA Implementation**  
   - Provides an additional authentication layer beyond passwords  
   - Reduces effectiveness of shared passwords  
   - Makes brute force attacks more difficult to succeed  

2. **Enforcing Strong Password Policies**  
   - Increases the difficulty for attackers to guess credentials  
   - Account lockouts after multiple failed attempts prevent repeated login attempts  
   - Regular password updates mitigate long-term risks of stolen credentials  

3. **Firewall Maintenance**  
   - Ensures that only authorized traffic enters or leaves the network  
   - Keeps security rules up to date to prevent exploitation of vulnerabilities  
   - Provides protection against network-based attacks, such as DoS or DDoS  

---

## 6. Skills Demonstrated
1. Vulnerability assessment and analysis  
2. Knowledge of network hardening tools and methods  
3. Security risk assessment reporting  
4. Practical recommendations for mitigating network threats  
5. Documentation and explanation of cybersecurity measures  

---

## 7. Tools and Concepts Used
1. Multi-Factor Authentication (MFA)  
2. Password Policies and Management  
3. Firewall Rules and Maintenance  
4. Network Vulnerability Assessment Techniques  
5. Security Policy Documentation  

---

## 8. Conclusion
This lab demonstrates the importance of proactive network hardening to prevent unauthorized access and data breaches. Implementing MFA, enforcing strong password policies, and maintaining firewall rules significantly reduce the risk of security incidents.

Regular review and enforcement of these hardening practices ensure the organization maintains a robust security posture against evolving threats.

---

## 9. Future Improvements
1. Conduct regular vulnerability scans and patch updates  
2. Implement network monitoring and intrusion detection systems  
3. Educate employees about secure authentication practices  
4. Establish a formal information security policy outlining hardening practices












# Lab Module 4: Databases And SQL

This lab covers querying, filtering, and joining data from a database using MariaDB SQL. It provides practical experience in retrieving and analyzing information for security purposes.

---

## Table of Contents
1. [Activity 1: Perform a SQL query](#activity-1-perform-a-sql-query)
2. [Activity 2: Filter a SQL query](#activity-2-filter-a-sql-query)
3. [Activity 3: Apply more filters in SQL](#activity-3-apply-more-filters-in-sql)
4. [Activity 4: Filter with AND, OR, and NOT](#activity-4-filter-with-and-or-and-not)
5. [Activity 5: Complete a join](#activity-5-complete-a-join)

---

## Activity 1: Perform a SQL query

**Objectives:**
- Return information on employee devices
- Examine login attempts
- Sort the data returned from a query

**Scenario:**  
Determine which employee devices must be updated and investigate user login activity for unusual events. Data is in the `machines` and `log_in_attempts` tables.

**Sample Tables:**

### `machines` table

| device_id | email_client | operating_system | OS_patch_date |
|-----------|--------------|----------------|---------------|
| 101       | Outlook      | OS 1           | 2023-01-10    |
| 102       | Gmail        | OS 2           | 2022-12-15    |
| 103       | Thunderbird  | OS 2           | 2022-12-20    |
| 104       | Outlook      | OS 3           | 2023-02-01    |

### `log_in_attempts` table

| event_id | username   | login_date | login_time | country | success |
|----------|-----------|------------|------------|---------|--------|
| 1        | alice     | 2022-05-08 | 09:00:00   | USA     | 1      |
| 2        | bob       | 2022-05-09 | 18:30:00   | CAN     | 0      |
| 3        | charlie   | 2022-05-10 | 06:30:00   | MEX     | 1      |
| 4        | diana     | 2022-05-11 | 20:15:00   | USA     | 0      |

**Tasks and SQL Queries:**

1. Retrieve all information about employee devices:
```sql
SELECT * FROM machines;
```
| device_id | email_client | operating_system | OS_patch_date |
| --------- | ------------ | ---------------- | ------------- |
| 101       | Outlook      | OS 1             | 2023-01-10    |
| 102       | Gmail        | OS 2             | 2022-12-15    |
| 103       | Thunderbird  | OS 2             | 2022-12-20    |
| 104       | Outlook      | OS 3             | 2023-02-01    |



2. Select only the device_id and email_client columns:
```sql
SELECT device_id, email_client FROM machines;
```
| device_id | email_client |
| --------- | ------------ |
| 101       | Outlook      |
| 102       | Gmail        |
| 103       | Thunderbird  |
| 104       | Outlook      |



3. Select device_id, operating_system, and OS_patch_date columns:
```sql
SELECT device_id, operating_system, OS_patch_date FROM machines;
```
| device_id | operating_system | OS_patch_date |
| --------- | ---------------- | ------------- |
| 101       | OS 1             | 2023-01-10    |
| 102       | OS 2             | 2022-12-15    |
| 103       | OS 2             | 2022-12-20    |
| 104       | OS 3             | 2023-02-01    |



4. Investigate login attempts by location:
```sql
SELECT event_id, country FROM log_in_attempts;
```
| event_id | country |
| -------- | ------- |
| 1        | USA     |
| 2        | CAN     |
| 3        | MEX     |
| 4        | USA     |



5. Check login attempts outside working hours:
```sql
SELECT username, login_date, login_time FROM log_in_attempts;
```
| username | login_date | login_time |
| -------- | ---------- | ---------- |
| alice    | 2022-05-08 | 09:00:00   |
| bob      | 2022-05-09 | 18:30:00   |
| charlie  | 2022-05-10 | 06:30:00   |
| diana    | 2022-05-11 | 20:15:00   |



6. Select all login attempts:
```sql
SELECT * FROM log_in_attempts;
```
| event_id | username | login_date | login_time | country | success |
| -------- | -------- | ---------- | ---------- | ------- | ------- |
| 1        | alice    | 2022-05-08 | 09:00:00   | USA     | 1       |
| 2        | bob      | 2022-05-09 | 18:30:00   | CAN     | 0       |
| 3        | charlie  | 2022-05-10 | 06:30:00   | MEX     | 1       |
| 4        | diana    | 2022-05-11 | 20:15:00   | USA     | 0       |



7. Order login attempts by date:
```sql
SELECT *
FROM log_in_attempts
ORDER BY login_date;
```
| event_id | username | login_date | login_time | country | success |
| -------- | -------- | ---------- | ---------- | ------- | ------- |
| 1        | alice    | 2022-05-08 | 09:00:00   | USA     | 1       |
| 2        | bob      | 2022-05-09 | 18:30:00   | CAN     | 0       |
| 3        | charlie  | 2022-05-10 | 06:30:00   | MEX     | 1       |
| 4        | diana    | 2022-05-11 | 20:15:00   | USA     | 0       |



8. Order login attempts by date and time:
```sql
SELECT *
FROM log_in_attempts
ORDER BY login_date, login_time;
```
| event_id | username | login_date | login_time | country | success |
| -------- | -------- | ---------- | ---------- | ------- | ------- |
| 1        | alice    | 2022-05-08 | 09:00:00   | USA     | 1       |
| 2        | bob      | 2022-05-09 | 18:30:00   | CAN     | 0       |
| 3        | charlie  | 2022-05-10 | 06:30:00   | MEX     | 1       |
| 4        | diana    | 2022-05-11 | 20:15:00   | USA     | 0       |



---
## Activity 2: Filter a SQL query

**Objectives:**
- Apply filters to SQL queries
- Retrieve information about employees, machines, and departments

**Scenario:** Retrieve specific information about employees, their machines, and departments using filters in SQL.  

**Sample Tables:**

### `machines` table

| device_id | operating_system |
|-----------|----------------|
| 101       | OS 1           |
| 102       | OS 2           |
| 103       | OS 2           |
| 104       | OS 3           |

### `employees` table

| employee_id | name   | department | office   | device_id |
|-------------|--------|-----------|----------|-----------|
| 1           | Alice  | Finance   | North-101 | 101       |
| 2           | Bob    | Sales     | South-109 | 102       |
| 3           | Charlie| Marketing | East-170 | 103       |
| 4           | Diana  | IT        | West-220 | 104       |

**Tasks and SQL Queries:**
1. Retrieve device_id and operating_system columns:
```sql
SELECT device_id, operating_system FROM machines;
```
| device_id | operating_system |
| --------- | ---------------- |
| 101       | OS 1             |
| 102       | OS 2             |
| 103       | OS 2             |
| 104       | OS 3             |



2. Retrieve machines with 'OS 2':
```sql
SELECT device_id, operating_system
FROM machines
WHERE operating_system = 'OS 2';
```
| device_id | operating_system |
| --------- | ---------------- |
| 102       | OS 2             |
| 103       | OS 2             |



3. Retrieve employees in the Finance department:
```sql
SELECT *
FROM employees
WHERE department = 'Finance';
```
| employee_id | name  | department | office    | device_id |
| ----------- | ----- | ---------- | --------- | --------- |
| 1           | Alice | Finance    | North-101 | 101       |



4. Retrieve employees in the Sales department:
```sql
SELECT *
FROM employees
WHERE department = 'Sales';
```
| employee_id | name | department | office    | device_id |
| ----------- | ---- | ---------- | --------- | --------- |
| 2           | Bob  | Sales      | South-109 | 102       |



5. Identify the employee using office 'South-109':
```sql
SELECT *
FROM employees
WHERE office = 'South-109';
```
| employee_id | name | department | office    | device_id |
| ----------- | ---- | ---------- | --------- | --------- |
| 2           | Bob  | Sales      | South-109 | 102       |



6. Retrieve all employees in the South building:
```sql
SELECT *
FROM employees
WHERE office LIKE 'South-%';
```
| employee_id | name | department | office    | device_id |
| ----------- | ---- | ---------- | --------- | --------- |
| 2           | Bob  | Sales      | South-109 | 102       |



---
## Activity 3: Apply more filters in SQL

**Objectives:**
- Filter data by dates, times, and numeric values
- Use operators such as =, >, <, >=, <=, and <>

**Scenario:** Investigate login attempts using filters with numeric and date/time operators to analyze unusual activity.

**Sample Table: `log_in_attempts`**

| event_id | username | login_date | login_time | success | country |
|----------|---------|------------|-----------|--------|---------|
| 100      | Alice   | 2022-05-08 | 08:30:00  | 1      | USA     |
| 101      | Bob     | 2022-05-09 | 06:45:00  | 0      | CAN     |
| 102      | Charlie | 2022-05-10 | 07:15:00  | 1      | MEX     |
| 103      | Diana   | 2022-05-11 | 06:30:00  | 0      | USA     |
| 104      | Bob     | 2022-05-12 | 08:00:00  | 1      | USA     |

**Tasks and SQL Queries:**
1. Retrieve login attempts after '2022-05-09':
```sql
SELECT *
FROM log_in_attempts
WHERE login_date > '2022-05-09';
```
| event_id | username | login_date | login_time | success | country |
| -------- | -------- | ---------- | ---------- | ------- | ------- |
| 102      | Charlie  | 2022-05-10 | 07:15:00   | 1       | MEX     |
| 103      | Diana    | 2022-05-11 | 06:30:00   | 0       | USA     |
| 104      | Bob      | 2022-05-12 | 08:00:00   | 1       | USA     |



2. Retrieve login attempts on or after '2022-05-09':
```sql
SELECT *
FROM log_in_attempts
WHERE login_date >= '2022-05-09';
```
| event_id | username | login_date | login_time | success | country |
| -------- | -------- | ---------- | ---------- | ------- | ------- |
| 101      | Bob      | 2022-05-09 | 06:45:00   | 0       | CAN     |
| 102      | Charlie  | 2022-05-10 | 07:15:00   | 1       | MEX     |
| 103      | Diana    | 2022-05-11 | 06:30:00   | 0       | USA     |
| 104      | Bob      | 2022-05-12 | 08:00:00   | 1       | USA     |



3. Retrieve login attempts between '2022-05-09' and '2022-05-11':
```sql
SELECT *
FROM log_in_attempts
WHERE login_date BETWEEN '2022-05-09' AND '2022-05-11';
```
| event_id | username | login_date | login_time | success | country |
| -------- | -------- | ---------- | ---------- | ------- | ------- |
| 101      | Bob      | 2022-05-09 | 06:45:00   | 0       | CAN     |
| 102      | Charlie  | 2022-05-10 | 07:15:00   | 1       | MEX     |
| 103      | Diana    | 2022-05-11 | 06:30:00   | 0       | USA     |



4. Retrieve login attempts before '07:00:00':
```sql
SELECT *
FROM log_in_attempts
WHERE login_time < '07:00:00';
```
| event_id | username | login_date | login_time | success | country |
| -------- | -------- | ---------- | ---------- | ------- | ------- |
| 101      | Bob      | 2022-05-09 | 06:45:00   | 0       | CAN     |
| 103      | Diana    | 2022-05-11 | 06:30:00   | 0       | USA     |



5. Retrieve login attempts between '06:00:00' and '07:00:00':
```sql
SELECT *
FROM log_in_attempts
WHERE login_time BETWEEN '06:00:00' AND '07:00:00';
```
| event_id | username | login_date | login_time | success | country |
| -------- | -------- | ---------- | ---------- | ------- | ------- |
| 101      | Bob      | 2022-05-09 | 06:45:00   | 0       | CAN     |
| 103      | Diana    | 2022-05-11 | 06:30:00   | 0       | USA     |



6. Retrieve login attempts with event_id ≥ 100:
```sql
SELECT event_id, username, login_date
FROM log_in_attempts
WHERE event_id >= 100;
```
| event_id | username | login_date |
| -------- | -------- | ---------- |
| 100      | Alice    | 2022-05-08 |
| 101      | Bob      | 2022-05-09 |
| 102      | Charlie  | 2022-05-10 |
| 103      | Diana    | 2022-05-11 |
| 104      | Bob      | 2022-05-12 |



7. Retrieve login attempts with event_id between 100 and 150:
```sql
SELECT event_id, username, login_date
FROM log_in_attempts
WHERE event_id BETWEEN 100 AND 150;
```
| event_id | username | login_date |
| -------- | -------- | ---------- |
| 100      | Alice    | 2022-05-08 |
| 101      | Bob      | 2022-05-09 |
| 102      | Charlie  | 2022-05-10 |
| 103      | Diana    | 2022-05-11 |
| 104      | Bob      | 2022-05-12 |



---
## Activity 4: Filter with AND, OR, and NOT

**Objectives:**
- Apply multiple conditions in SQL queries
- Use AND, OR, and NOT operators

**Scenario:** Analyze employee login attempts and departmental information using multiple conditions and negations.

**Sample Tables:**

### Table: `log_in_attempts`

| event_id | username | login_date | login_time | success | country |
|----------|---------|------------|-----------|--------|---------|
| 100      | Alice   | 2022-05-08 | 08:30:00  | 1      | USA     |
| 101      | Bob     | 2022-05-09 | 19:00:00  | 0      | CAN     |
| 102      | Charlie | 2022-05-10 | 17:15:00  | 1      | MEX     |
| 103      | Diana   | 2022-05-11 | 20:30:00  | 0      | USA     |
| 104      | Eve     | 2022-05-12 | 16:00:00  | 1      | MEX     |

### Table: `employees`

| emp_id | username | department          | office     |
|--------|---------|-------------------|-----------|
| 1      | Alice   | Finance           | East-170  |
| 2      | Bob     | Sales             | South-109 |
| 3      | Charlie | Marketing         | East-320  |
| 4      | Diana   | Information Technology | West-205 |
| 5      | Eve     | Marketing         | East-170  |

**Tasks and SQL Queries:**
1. Failed login attempts after 18:00:
```sql
SELECT *
FROM log_in_attempts
WHERE login_time > '18:00' AND success = 0;
```
| event_id | username | login_date | login_time | success | country |
| -------- | -------- | ---------- | ---------- | ------- | ------- |
| 101      | Bob      | 2022-05-09 | 19:00:00   | 0       | CAN     |
| 103      | Diana    | 2022-05-11 | 20:30:00   | 0       | USA     |



2. Failed login attempts on '2022-05-08' or '2022-05-09':
```sql
SELECT *
FROM log_in_attempts
WHERE login_date = '2022-05-08' OR login_date = '2022-05-09';
```
| event_id | username | login_date | login_time | success | country |
| -------- | -------- | ---------- | ---------- | ------- | ------- |
| 100      | Alice    | 2022-05-08 | 08:30:00   | 1       | USA     |
| 101      | Bob      | 2022-05-09 | 19:00:00   | 0       | CAN     |



3. Login attempts not originating in Mexico:
```sql
SELECT *
FROM log_in_attempts
WHERE NOT country LIKE 'MEX%';
```
| event_id | username | login_date | login_time | success | country |
| -------- | -------- | ---------- | ---------- | ------- | ------- |
| 100      | Alice    | 2022-05-08 | 08:30:00   | 1       | USA     |
| 101      | Bob      | 2022-05-09 | 19:00:00   | 0       | CAN     |
| 103      | Diana    | 2022-05-11 | 20:30:00   | 0       | USA     |



4. Employees in Marketing department and East building:
```sql
SELECT *
FROM employees
WHERE department = 'Marketing' AND office LIKE 'East-%';
```
| emp_id | username | department | office   |
| ------ | -------- | ---------- | -------- |
| 3      | Charlie  | Marketing  | East-320 |
| 5      | Eve      | Marketing  | East-170 |



5. Employees in Finance or Sales department:
```sql
SELECT *
FROM employees
WHERE department = 'Finance' OR department = 'Sales';
```
| emp_id | username | department | office    |
| ------ | -------- | ---------- | --------- |
| 1      | Alice    | Finance    | East-170  |
| 2      | Bob      | Sales      | South-109 |



6. Employees not in Information Technology:
```sql
SELECT *
FROM employees
WHERE NOT department = 'Information Technology';
```
| emp_id | username | department | office    |
| ------ | -------- | ---------- | --------- |
| 1      | Alice    | Finance    | East-170  |
| 2      | Bob      | Sales      | South-109 |
| 3      | Charlie  | Marketing  | East-320  |
| 5      | Eve      | Marketing  | East-170  |



---
## Activity 5: Complete a join

**Objectives:**
- Use INNER JOIN, LEFT JOIN, and RIGHT JOIN to combine tables
- Retrieve information from multiple related tables

**Scenario:** Investigate employee machines and login attempts using INNER JOIN, LEFT JOIN, and RIGHT JOIN in SQL.

**Sample Tables:**

### Table: `employees`

| emp_id | username | department | device_id |
|--------|---------|-----------|-----------|
| 1      | Alice   | Finance   | 101       |
| 2      | Bob     | Sales     | 102       |
| 3      | Charlie | Marketing | 103       |
| 4      | Diana   | IT        | NULL      |
| 5      | Eve     | Marketing | 104       |

### Table: `machines`

| device_id | device_name | operating_system |
|-----------|------------|----------------|
| 101       | Laptop-A   | OS 1           |
| 102       | Laptop-B   | OS 2           |
| 103       | Laptop-C   | OS 2           |
| 105       | Laptop-E   | OS 1           |

### Table: `log_in_attempts`

| event_id | username | login_date | login_time | success |
|----------|---------|------------|-----------|--------|
| 100      | Alice   | 2022-05-08 | 08:30:00  | 1      |
| 101      | Bob     | 2022-05-09 | 19:00:00  | 0      |
| 102      | Charlie | 2022-05-10 | 17:15:00  | 1      |
| 103      | Eve     | 2022-05-11 | 20:30:00  | 0      |

**Tasks and SQL Queries:**
1. Inner join between machines and employees on device_id:
```sql
SELECT *
FROM machines
INNER JOIN employees ON machines.device_id = employees.device_id;
```
| device_id | device_name | operating_system | emp_id | username | department | device_id |
| --------- | ----------- | ---------------- | ------ | -------- | ---------- | --------- |
| 101       | Laptop-A    | OS 1             | 1      | Alice    | Finance    | 101       |
| 102       | Laptop-B    | OS 2             | 2      | Bob      | Sales      | 102       |
| 103       | Laptop-C    | OS 2             | 3      | Charlie  | Marketing  | 103       |



2. Left join to show all machines and their assigned employees:
```sql
SELECT *
FROM machines
LEFT JOIN employees ON machines.device_id = employees.device_id;
```
| device_id | device_name | operating_system | emp_id | username | department | device_id |
| --------- | ----------- | ---------------- | ------ | -------- | ---------- | --------- |
| 101       | Laptop-A    | OS 1             | 1      | Alice    | Finance    | 101       |
| 102       | Laptop-B    | OS 2             | 2      | Bob      | Sales      | 102       |
| 103       | Laptop-C    | OS 2             | 3      | Charlie  | Marketing  | 103       |
| 105       | Laptop-E    | OS 1             | NULL   | NULL     | NULL       | NULL      |



3. Right join to show all employees and their assigned machines:
```sql
SELECT *
FROM machines
RIGHT JOIN employees ON machines.device_id = employees.device_id;
```
| device_id | device_name | operating_system | emp_id | username | department | device_id |
| --------- | ----------- | ---------------- | ------ | -------- | ---------- | --------- |
| 101       | Laptop-A    | OS 1             | 1      | Alice    | Finance    | 101       |
| 102       | Laptop-B    | OS 2             | 2      | Bob      | Sales      | 102       |
| 103       | Laptop-C    | OS 2             | 3      | Charlie  | Marketing  | 103       |
| NULL      | NULL        | NULL             | 4      | Diana    | IT         | NULL      |
| 104       | Laptop-D?   | OS ?             | 5      | Eve      | Marketing  | 104       |



4. Inner join between employees and log_in_attempts on username:
```sql
SELECT *
FROM employees
INNER JOIN log_in_attempts ON employees.username = log_in_attempts.username;
```
| emp_id | username | department | device_id | event_id | username | login_date | login_time | success |
| ------ | -------- | ---------- | --------- | -------- | -------- | ---------- | ---------- | ------- |
| 1      | Alice    | Finance    | 101       | 100      | Alice    | 2022-05-08 | 08:30:00   | 1       |
| 2      | Bob      | Sales      | 102       | 101      | Bob      | 2022-05-09 | 19:00:00   | 0       |
| 3      | Charlie  | Marketing  | 103       | 102      | Charlie  | 2022-05-10 | 17:15:00   | 1       |
| 5      | Eve      | Marketing  | 104       | 103      | Eve      | 2022-05-11 | 20:30:00   | 0       |



---

## Reflection

During this lab module, I gained practical experience in using SQL to retrieve, filter, and combine data from relational databases. By performing a series of activities—from basic SELECT queries to applying complex filters and joining multiple tables—I strengthened my understanding of how to analyze and manipulate data efficiently.  

Key skills I developed include:

- **Querying data with SELECT**: I practiced retrieving specific columns or all columns from tables, allowing me to focus on the information relevant to security analysis tasks.  
- **Filtering data with WHERE, AND, OR, NOT, and BETWEEN operators**: I learned how to narrow down query results based on multiple criteria, including numeric, date, and time values, which is crucial when investigating security incidents.  
- **Sorting data using ORDER BY**: I understood how to organize information chronologically or by specific fields to detect patterns or anomalies in employee activity.  
- **Joining tables (INNER, LEFT, RIGHT JOINs)**: I gained hands-on experience combining data from multiple tables, enabling me to obtain a complete picture of employees, their devices, and login attempts.  
- **Using sample data for analysis**: Creating hypothetical tables and reviewing expected query outputs helped me visualize results and anticipate real-world scenarios in a corporate environment.  

Overall, this lab reinforced the importance of structured data retrieval and analysis in cybersecurity. It demonstrated how SQL is a powerful tool to monitor systems, investigate incidents, and support informed decision-making.  

---

## Conclusion

This lab provided a strong foundation in database management and SQL, equipping me with essential skills for a security analyst role. I can now:

1. Efficiently retrieve and filter data to investigate incidents or system activity.  
2. Apply logical operators and conditional statements to extract meaningful insights.  
3. Combine multiple data sources through SQL joins to generate comprehensive reports.  

Mastering these SQL techniques enhances my ability to monitor and secure organizational systems, investigate unusual activities, and maintain data integrity. These skills are fundamental for any cybersecurity professional and will directly support my future work in system administration, security auditing, and data-driven decision-making.













# Lab Module 4: Linux Commands In The Bash Shell

This module demonstrates practical skills in navigating, managing, and analyzing files, users, and permissions in a Linux Bash shell. It includes six lab activities designed to build foundational Linux skills useful for a security analyst.

---

## Table of Contents
1. [Activity 1: Find files with Linux commands](#activity-1-find-files-with-linux-commands)
2. [Activity 2: Filter with grep](#activity-2-filter-with-grep)
3. [Activity 3: Manage files with Linux commands](#activity-3-manage-files-with-linux-commands)
4. [Activity 4: Manage authorization](#activity-4-manage-authorization)
5. [Activity 5: Add and manage users with Linux commands](#activity-5-add-and-manage-users-with-linux-commands)
6. [Activity 6: Get help in the command line](#activity-6-get-help-in-the-command-line)

---

## Activity 1: Find files with Linux commands

**Objective:** Navigate directories, locate files, and read file contents using Linux commands.

### Commands Used
```bash
# Display current working directory
pwd

# List files and directories in the current working directory
ls -l

# Navigate to reports directory
cd /home/analyst/reports

# List subdirectories
ls -l

# Navigate to users subdirectory
cd users

# Display files in the directory
ls

# Display contents of a file
cat Q1_added_users.txt

# Navigate to logs directory
cd /home/analyst/logs

# Display file names
ls

# Display first 10 lines of a file
head -n 10 server_logs.txt
```

### Reflection:
This activity strengthened my ability to navigate Linux directories, locate files, and read contents, which are foundational skills for analyzing system activity or investigating security events.

---

## Activity 2: Filter with grep

**Objective:** Use grep and piping to search for specific information in files.

### Commands Used
```bash
# Navigate to logs directory
cd /home/analyst/logs

# Search for error messages
grep "error" server_logs.txt

# Navigate to users directory
cd /home/analyst/reports/users

# Find files with 'Q1' in their names
ls | grep "Q1"

# Find files with 'access' in their names
ls | grep "access"

# Search deleted users
grep "jhill" Q2_deleted_users.txt

# List users added to Human Resource department
grep "Human Resource" Q4_added_users.txt
```

### Reflection:
Filtering data with grep allows efficient retrieval of relevant information, essential for analyzing logs or auditing user activities in a system.

---

## Activity 3: Manage files with Linux commands

**Objective:** Create, move, remove files and directories, and edit files using nano.

### Commands Used
```bash
# Create new logs subdirectory
mkdir /home/analyst/logs

# List contents to verify
ls -l /home/analyst

# Remove temp directory
rm -r /home/analyst/temp

# Move Q3patches.txt to reports
mv /home/analyst/notes/Q3patches.txt /home/analyst/reports

# Delete tempnotes.txt
rm /home/analyst/notes/tempnotes.txt

# Create tasks.txt
touch /home/analyst/notes/tasks.txt

# Edit tasks.txt with nano
nano /home/analyst/notes/tasks.txt

# Clear screen
clear

# Display contents to verify
cat /home/analyst/notes/tasks.txt
```

### Reflection:
This activity emphasized effective file and directory management, a key skill for organizing system resources and maintaining data integrity.

---

## Activity 4: Manage authorization

**Objective:** Examine and modify file and directory permissions to control access.

### Commands Used
```bash
# Navigate to projects directory
cd /home/researcher2/projects

# List contents with permissions
ls -la

# Remove write permission for others on a file
chmod o-w project_k.txt

# Restrict group permissions on a file
chmod go-rw project_m.txt

# Adjust hidden file permissions
chmod ug=r .project_x.txt

# Remove execute permission for group on drafts directory
chmod g-x drafts
```

### Reflection:
Managing permissions ensures that sensitive files are only accessible to authorized users, reducing the risk of unauthorized changes or data exposure.

---

## Activity 5: Add and manage users with Linux commands

**Objective:** Add, modify, and delete users and groups in Linux.

### Commands Used
```bash
# Add new user researcher9
sudo useradd researcher9

# Add to primary group
sudo usermod -g research_team researcher9

# Change file ownership
sudo chown researcher9 /home/researcher2/projects/project_r.txt

# Add to secondary group
sudo usermod -a -G sales_team researcher9

# Delete user
sudo userdel researcher9

# Delete unused group
sudo groupdel researcher9
```

### Reflection:
This activity provided experience in user management and demonstrated how proper access control aligns with security best practices.

---

## Activity 6: Get help in the command line

**Objective:** Use man, whatis, and apropos to discover commands and options.

### Commands Used
```bash
# Get short description of cat
whatis cat

# Display manual page for cat
man cat

# Search commands with keywords
apropos "first part file"

# Check options for useradd
man useradd

# Compare rm and rmdir
whatis rm
whatis rmdir

# Identify command to create a new group
apropos "create new group"
```

### Reflection:
Learning how to access command documentation and find options efficiently is invaluable for troubleshooting and mastering Linux commands.

---

## Conclusion:
By completing these six activities, I developed core Linux Bash skills, including directory navigation, file management, filtering data, managing permissions, user administration, and accessing command-line help. These skills are fundamental for security analysts working in Linux environments.













# Lab Module 5: Introduction to Asset Security

This lab focuses on understanding asset management and risk assessment in a cybersecurity context. The lab consists of two activities:  

1. **Classifying assets connected to a home network**  
2. **Scoring risks based on their likelihood and severity**  

---

## Activity 1: Classify the Assets Connected to a Home Network

**Objective:**  
Create an inventory of devices connected to a home network, identify their characteristics, and classify them based on sensitivity to risk.

**Overview:**  
Asset management is critical in cybersecurity. It involves tracking assets, evaluating associated risks, and classifying them according to their importance and sensitivity. In this activity, I identified additional network-connected devices, evaluated their characteristics, and assigned sensitivity levels.

**Asset Inventory Table:**  

| Asset                  | Network Access | Owner       | Location         | Notes                                                    | Sensitivity      |
|------------------------|----------------|------------|----------------|----------------------------------------------------------|----------------|
| Network router         | Continuous     | ISP        | On-premises     | 2.4 GHz and 5 GHz connections; all devices connect to 5 GHz | Confidential   |
| Desktop                | Occasional     | Homeowner  | On-premises     | Contains private information, like photos               | Restricted      |
| Guest smartphone       | Occasional     | Friend     | On/Off-premises | Connects to home network                                 | Internal-only   |
| External hard drive    | Occasional     | Homeowner  | On-premises     | Contains music and movies                                | Confidential    |
| Streaming media player | Continuous     | Homeowner  | On-premises     | Payment card information stored for rentals             | Internal-only   |
| Portable game console  | Occasional     | Friend     | On/Off-premises | Has camera and microphone                                 | Internal-only   |

**Reflection:**  
This activity highlighted the importance of maintaining an accurate inventory of all network-connected devices. Evaluating network access, ownership, location, and stored information helped me classify assets and prioritize their protection. Sensitive devices were labeled with higher sensitivity to enforce a “need-to-know” access approach. Future improvements could include tracking non-networked assets and considering additional security measures for shared devices.

---

## Activity 2: Score Risks Based on Likelihood and Severity

**Objective:**  
Perform a risk assessment for a bank’s operational environment, evaluate the likelihood and severity of potential security risks, and prioritize cybersecurity resources.

**Overview:**  
Risk assessments are essential to identify vulnerabilities threatening business operations. This activity involved evaluating a set of risks using a risk register and applying a risk matrix to calculate scores based on likelihood and severity.  

**Risk Formula:**  
Risk Score = Likelihood × Severity


**Risk Register Table:**  

| Asset | Risk(s)                      | Description                                         | Likelihood | Severity | Priority |
|-------|-------------------------------|---------------------------------------------------|------------|----------|----------|
| Funds | Business email compromise      | An employee is tricked into sharing confidential information | 2          | 2        | 4        |
| Funds | Compromised user database      | Customer data is poorly encrypted                 | 2          | 3        | 6        |
| Funds | Financial records leak         | A database server of backed-up data is publicly accessible | 3          | 3        | 9        |
| Funds | Theft                          | The bank's safe is left unlocked                  | 1          | 3        | 3        |
| Funds | Supply chain disruption        | Delivery delays due to natural disasters         | 1          | 2        | 2        |

**Likelihood and Severity Explanation Table:**  

| Risk                           | Likelihood (Chance of Occurring)                                     | Severity (Impact if Occurs)                                         |
|--------------------------------|----------------------------------------------------------------------|----------------------------------------------------------------------|
| Business email compromise       | 2 – Likely: Employees occasionally fall for phishing attempts       | 2 – Moderate: Could cause data loss or minor financial impact       |
| Compromised user database       | 2 – Likely: Customer data may be targeted or poorly secured          | 3 – High: Could result in regulatory fines and reputational damage  |
| Financial records leak          | 3 – High: Database is publicly accessible, so risk is frequent      | 3 – High: Severe financial, operational, and reputational impact   |
| Theft                           | 1 – Rare: Bank in low-crime coastal area                              | 3 – High: Loss of funds could critically impact operations          |
| Supply chain disruption         | 1 – Rare: Natural disasters unpredictable, but possible              | 2 – Moderate: Could delay operations and cash availability          |

**Notes:**  
The bank interacts with multiple external entities, increasing the risk of data compromise. While theft is possible, the low crime rate reduces its priority. Risks like financial records leaks require immediate attention due to regulatory, financial, and reputational impacts.

**Reflection:**  
This activity demonstrated the process of evaluating security risks systematically. By assigning likelihood and severity scores, I calculated overall risk priorities to guide cybersecurity decision-making. The highest priority risk was a financial records leak, aligning with the critical nature of the bank's data. This reinforces proactive security planning and the importance of regular risk assessments. Future improvements could include integrating historical incident data to refine likelihood estimates.

---

## Conclusion

The **Introduction to Asset Security** lab emphasized foundational skills in asset management and risk assessment. By classifying network-connected devices and performing structured risk evaluations, I learned to identify critical assets, assess vulnerabilities, and prioritize protective measures. Completing these activities strengthened my ability to create detailed asset inventories and perform informed, data-driven risk assessments, which are essential skills in both home and organizational cybersecurity environments.













# Lab Module 5: Protect Organizational Assets

This lab focuses on protecting organizational data through secure handling practices, encryption, hashing, and access control improvements. It consists of four activities that simulate real-world cybersecurity scenarios.

---

## Activity 1: Determine Appropriate Data Handling Practices

**Objective:**  
Analyze a data leak incident and recommend improvements using the principle of least privilege.

**Incident Analysis:**  
The data leak occurred because access to a folder containing sensitive internal documents was not properly restricted or revoked. The manager failed to remove access after the meeting, and the employee mistakenly shared the entire folder instead of limited materials. This demonstrates poor enforcement of access control and lack of oversight.

**NIST SP 800-53: AC-6 Summary:**  
NIST SP 800-53 AC-6 defines the principle of least privilege, which ensures users are granted only the minimum access necessary to perform their tasks. It also outlines implementation strategies and enhancements to strengthen access control and reduce the risk of data exposure.

**Recommendations:**  
- Restrict access to sensitive resources based on user roles  
- Automatically revoke access after a defined period  

**Justification:**  
Limiting access based on roles ensures that only authorized users can view sensitive data. Automatic revocation reduces the risk of forgotten permissions, minimizing human error and preventing unintended data exposure.

---

## Activity 2: Decrypt an Encrypted Message

**Objective:**  
Use Linux commands to decrypt encrypted data and recover hidden messages.

**Process Overview:**  
- Listed directory contents using `ls`  
- Read instructions using `cat README.txt`  
- Navigated directories using `cd`  
- Identified hidden files using `ls -a`  
- Decrypted a Caesar cipher using `tr`  
- Decrypted a file using `openssl`  

**Key Commands Used:**  
```bash
ls
cat README.txt
cd caesar
ls -a
cat .leftShift3 | tr "d-za-cD-ZA-C" "a-zA-Z"
cd ~
openssl aes-256-cbc -pbkdf2 -a -d -in Q1.encrypted -out Q1.recovered -k ettubrute
cat Q1.recovered
```

**Reflection:**  
This activity strengthened my understanding of encryption and decryption processes. It demonstrated how classical ciphers and modern encryption techniques can be reversed using the correct tools and commands, reinforcing the importance of protecting sensitive data.

---

## Activity 3: Create Hash Values

**Objective:**  
Generate and compare hash values to verify file integrity.

**Process Overview:**
- Displayed file contents using cat
- Generated SHA-256 hashes using sha256sum
- Saved hashes to files
- Compared hashes manually and using cmp

**Key Commands Used:**
```bash
cat file1.txt
cat file2.txt
sha256sum file1.txt
sha256sum file2.txt
sha256sum file1.txt >> file1hash
sha256sum file2.txt >> file2hash
cat file1hash
cat file2hash
cmp file1hash file2hash
```

**Findings:**  
Although both files appeared identical, their hash values were different. This indicates that even a small unseen difference (such as whitespace or hidden characters) can produce a completely different hash.

**Reflection:**  
This activity highlighted the importance of hashing for ensuring data integrity. It showed how security professionals can detect even the smallest modifications to files, which is critical for identifying tampering or malicious changes.

---

## Activity 4: Improve Authentication, Authorization, and Accounting

**Objective:**  
Analyze an access control incident and recommend improvements.

**Relevant Employee Record:**

| Name              | Role            | Status     | Authorization | IP Address       | End Date   |
|-------------------|----------------|------------|---------------|------------------|------------|
| Robert Taylor Jr. | Legal attorney | Contractor | Admin         | 152.207.255.255  | 12/27/2019 |

**Relevant Log Evidence:**

```plaintext
Event Type: Information  
Date: 10/03/2023  
Time: 8:29:57 AM  
User: Legal\Administrator  
IP Address: 152.207.255.255  
Action: Payroll event added (FAUX_BANK)
```

**Analysis:**  
The event log indicates that a user with administrative privileges performed a payroll-related action. Cross-referencing the IP address with the employee directory shows that the account belongs to a former contractor, Robert Taylor Jr., whose contract ended in 2019. This suggests unauthorized or unmanaged access to critical systems.

**Notes (Investigation Findings):**
- Event occurred on 10/03/2023 using IP address 152.207.255.255
- User identified as Legal/Administrator (Robert Taylor Jr.)

**Issues Identified:**
- Contractor account remained active after contract ended in 2019
- User had excessive privileges (admin access to sensitive systems)

**Recommendations:**
- Implement automatic account expiration for inactive or former employees
- Apply role-based access control (RBAC) with limited privileges
- Enable multi-factor authentication (MFA)

**Reflection:**  
This activity highlights the importance of proper account lifecycle management and access control enforcement. Retaining active accounts for former employees and granting excessive privileges significantly increases security risks. Strengthening authentication and authorization controls can effectively reduce the likelihood of similar incidents.

---

## Conclusion

The Protect Organizational Assets lab provided practical experience in securing data through multiple approaches, including data handling policies, encryption, hashing, and access control mechanisms.

Through these activities, I developed a stronger understanding of how to:
- Prevent data leaks using least privilege principles
- Decrypt and analyze encrypted data
- Verify data integrity using hashing
- Strengthen authentication and authorization controls

These skills are essential for maintaining a secure organizational environment and protecting sensitive information from potential threats.














# Lab Module 5: Threats to Asset Security
This lab focuses on identifying and analyzing threats to organizational assets, with a particular emphasis on social engineering attacks and application security. The lab exercises demonstrate practical skills in detecting phishing attempts and applying structured threat modeling frameworks like PASTA (Process for Attack Simulation and Threat Analysis).

## Objective
The main objectives of this lab are:
- To detect and analyze phishing emails to prevent social engineering attacks.
- To practice applying the PASTA threat model to assess risks and vulnerabilities in a software application.
- To implement professional procedures for documenting and mitigating potential security threats.

### Activity 1: Filter Malicious Emails
#### Scenario
As a security analyst at Imaginary Bank, you were tasked with investigating a suspicious spear phishing email received by an executive. The email claimed the executive was added to a collaboration group, Execs, and prompted them to download ExecuTalk software.

#### Investigation
**1. Email Header Analysis – Indicators of Phishing**
- Sender uses a different domain: The email is from imaginarybank@gmail.org, not the official company domain.
- Misspelling in the subject line: “RE: You are been added to an ecsecutiv's groups.” Phishing emails often contain spelling or grammatical errors.

**2. Email Body Analysis – Legitimate Appearance Tactics**
- Download options for major operating systems – Mac, Windows, Android.
- Title of the group – “Execs” makes it appear official.
- Brand labeling – “ExecuTalk© All rights reserved” adds legitimacy.

**3. Malicious Indicator**
- The URL linked to the downloads was not associated with the organization’s official domain. This is the main clue that the login form is malicious.

#### Outcome
The email was classified as a phishing attempt and should be quarantined. This exercise demonstrates the importance of carefully analyzing sender information, email content, and linked URLs to prevent social engineering attacks.

**1. Threat Actor Tactics and Social Engineering Techniques**  
The attacker used several methods to manipulate the executive:
- Urgency/Pressure: “This invitation will expire in 48 hours so act quickly.”
- Authority/Trust: The email pretended to come from the board of the bank.
- Familiarity: Terms like “Execs” were used to make the message appear internal.
This analysis shows an understanding of why phishing works, not just that it exists.

**2. Risk Assessment**  
If the phishing attempt had been successful, the consequences could have included:
- Compromise of executive credentials, giving attackers access to corporate systems.
- Installation of malware, potentially leading to a data breach or ransomware.
- Financial risk, if sensitive banking information was exposed.
This demonstrates the ability to connect detection to business risk.

**3. Recommended Actions**  
To mitigate the threat and prevent future incidents:
- Block the sender domain and add rules to the email gateway.
- Alert employees about similar phishing attempts.
- Report the incident to the internal security team and log it for threat intelligence purposes.

**4. Lessons Learned / Preventive Measures**  
To reduce the likelihood of future phishing attacks:
- Train employees to recognize phishing emails.
- Enforce email authentication protocols such as SPF, DKIM, and DMARC.
- Use email security tools to filter suspicious attachments and links.

---

### Activity 2: Apply the PASTA Threat Model Framework
#### Scenario
You were part of a security team evaluating a new mobile app for sneaker enthusiasts. The objective was to assess risks and vulnerabilities before launch using the PASTA framework.

#### Assumptions and Scope
- Users will connect via both **iOS and Android devices**.  
- Third-party APIs are used for **payment processing**.  
- All payment transactions are handled within the app, and user data is stored in a central **SQL database**.  

#### PASTA Stages Applied
| Stage | Analysis |
|-------|---------|
| **I. Define Business and Security Objectives** | - Users can create member profiles internally or via external accounts.<br>- The app must process financial transactions securely.<br>- Ensure **PCI-DSS compliance** for payment handling. |
| **II. Define Technical Scope** | Technologies used: **API, PKI, AES, SHA-256, SQL**.<br>**Prioritized:** APIs, because they handle sensitive data between multiple systems, creating a larger attack surface. |
| **III. Decompose Application** | Data flow: **user ↔ product search process ↔ database**.<br>This shows how user search queries access inventory data. |
| **IV. Threat Analysis** | - **Injection attacks:** Possible due to database interactions.<br>- **Session hijacking:** Weak login credentials or insecure cookie handling could be exploited.<br>**Threat Actor Profiles:**<br>• Internal: Disgruntled employees or developers with insufficient access control.<br>• External: Hackers targeting financial data or user credentials. |
| **V. Vulnerability Analysis** | - Lack of prepared statements in SQL queries.<br>- Broken API tokens or session management weaknesses.<br>**Likelihood and Impact:**<br>• SQL Injection → High risk: critical data exposure possible.<br>• Session Hijacking → Medium risk: could affect multiple users. |
| **VI. Attack Modeling** | Attack tree illustrated potential paths to compromise user data: SQL injection, session hijacking. |
| **VII. Risk Analysis and Impact** | Recommended security controls: SHA-256 hashing, incident response procedures, strict password policies, and principle of least privilege.<br>**Additional Security Controls:**<br>• Two-factor authentication (2FA) for users<br>• API rate limiting and monitoring<br>• Regular vulnerability scans and penetration testing<br>• Secure coding practices (input validation, prepared statements) |

#### Outcome
By applying the PASTA framework, the team identified high-risk areas in the application and suggested controls to mitigate potential threats before launch. This exercise demonstrates structured threat modeling as a proactive cybersecurity practice.

#### Lesson Learned
Applying the PASTA framework helped me understand how multiple layers of security interact, from **technical controls** like hashing and encryption to **operational controls** such as incident response. Threat modeling is crucial for proactively reducing risks before a product is deployed.

---

## Reflection
Through these two activities, I enhanced my practical skills in asset security and threat analysis. Activity 1 strengthened my ability to identify phishing attempts and analyze suspicious emails for social engineering indicators. Activity 2 reinforced my understanding of structured threat modeling using the PASTA framework, connecting application architecture to potential vulnerabilities and attack vectors. These exercises helped me appreciate the importance of thinking like both a security analyst and a potential threat actor.

---

## Conclusion
Overall, this lab demonstrates the critical importance of combining technical knowledge, analytical skills, and professional documentation practices to protect organizational assets. By carefully analyzing threats and proactively assessing risks, organizations can ensure the secure deployment of software applications and reduce the likelihood of security incidents.















# Lab Module 5: Vulnerabilities in Systems - Identify the Attack Vectors of a USB Drive

## Objective:
Assess the potential security risks of an unknown USB drive and analyze how sensitive information can be exploited by an attacker.

---

## Contents

The USB drive contained a mixture of personal and work-related files belonging to Jorge Bailey, the Human Resource Manager at Rhetorical Hospital. Personal files included family and pet photos, while work files contained new hire letters and employee shift schedules. Storing personal and sensitive work information on the same device increases the risk of accidental exposure or exploitation.

---

## Attacker Mindset

An attacker could use the information on the USB drive to target Jorge or the hospital. Work documents like timesheets and schedules could reveal operational details or personal identifiers of employees. Personal files could be leveraged to craft phishing attacks or social engineering attempts aimed at Jorge or his family, potentially providing a foothold into the hospital's network.

---

## Risk Analysis

USB baiting attacks could deliver malicious software, including ransomware, spyware, or keyloggers. If discovered by another employee, an infected device could compromise the entire network. Sensitive information found on the USB could be used to manipulate or coerce employees, steal identities, or gain unauthorized access to hospital systems. Mitigating these risks involves technical controls, like disabling AutoPlay on all company PCs; operational controls, such as routine antivirus scans; and managerial controls, including employee training and awareness of USB-based attacks.

---

## Reflection

This activity highlighted the dangers of seemingly harmless devices, like USB drives, and how human behavior can be exploited to gain access to sensitive information. It reinforced the importance of separating personal and work-related files, maintaining awareness of social engineering tactics, and applying strict security measures for device usage. Practicing risk assessment in a controlled environment strengthened my understanding of practical security procedures.

---

## Conclusion

Proper handling of USB drives is critical to prevent potential security breaches. Organizations should enforce employee awareness, implement technical controls, and routinely monitor for unauthorized devices. Combining these measures reduces the likelihood of USB-based attacks and ensures that sensitive information remains protected. This activity demonstrates how careful assessment and mitigation strategies can safeguard both personnel and organizational data.















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















# Lab Module 6: Network Monitoring and Analysis

## Lab Overview

This lab focuses on analyzing and monitoring network traffic using industry-standard tools such as Wireshark and tcpdump. The lab consists of three main activities that demonstrate packet analysis, packet capture, and tool comparison.

Through this lab, I developed practical skills in inspecting network traffic, applying filters, and understanding how data flows across networks—key competencies for a cybersecurity analyst.

---

## Objectives

- Analyze network traffic using packet capture tools  
- Apply filters to identify relevant network data  
- Capture live traffic in a Linux environment  
- Compare network protocol analyzers (Wireshark vs tcpdump)  
- Develop hands-on experience with real-world cybersecurity tools  

---

## Activity 1: Analyze Your First Packet (Wireshark)

### Description
In this activity, I used Wireshark to open and analyze a packet capture (.pcap) file. The goal was to understand packet structure, inspect protocol layers, and apply filters to identify meaningful traffic.

### Key Tasks Performed
- Opened and explored a packet capture file  
- Inspected packet details (Frame, Ethernet, IP, TCP layers)  
- Applied filters to isolate specific traffic  
- Analyzed DNS and HTTP communications  

### Filters Used
- `ip.addr == 142.250.1.139`
- `ip.src == 142.250.1.139`
- `ip.dst == 142.250.1.139`
- `eth.addr == 42:01:ac:15:e0:02`
- `udp.port == 53`
- `tcp.port == 80`
- `tcp contains "curl"`

### Sample Packet Evidence

Below are examples of different types of network traffic observed in Wireshark:

**1. DNS Query (Domain Resolution)**
- Source IP: 172.21.224.2  
- Destination IP: DNS Server  
- Protocol: UDP  
- Destination Port: 53  
- Query: opensource.google.com  

This shows the system resolving a domain name into an IP address.

**2. TCP Communication (Web Traffic)**
- Source IP: 172.21.224.2  
- Destination IP: 142.250.1.139  
- Protocol: TCP  
- Destination Port: 80 (HTTP)  

This indicates web communication between the local system and an external server.

**3. ICMP Packet (Connectivity Check)**
- Source IP: 172.21.224.2  
- Destination IP: 142.250.1.139  
- Protocol: ICMP (Echo Request/Reply)  

This reflects basic network connectivity testing between hosts.

### Packet Structure Analysis
A selected TCP packet was analyzed across multiple layers:
- **Frame Layer:** Displays overall packet size and capture details  
- **Ethernet II Layer:** Contains source and destination MAC addresses  
- **IP Layer (IPv4):** Shows source (172.21.224.2) and destination (142.250.1.139) IP addresses  
- **TCP Layer:** Includes source port (49652), destination port (80), and flags used in communication  
This layered analysis demonstrates how data is encapsulated and transmitted across a network.

### Key Findings
- Identified communication between local system and external IP (142.250.1.139)  
- Observed ICMP (ping), DNS queries, and HTTP traffic  
- DNS queries revealed domain resolution for `opensource.google.com`  
- TCP traffic showed web requests and responses over port 80  
- Packet inspection revealed protocol layering (Ethernet → IP → TCP/UDP → Application)

### Traffic Interpretation
The captured traffic indicates normal web browsing behavior:
- DNS queries resolve domain names (opensource.google.com) into IP addresses  
- TCP connections are established over port 80 for HTTP communication  
- ICMP packets (ping) show connectivity checks between hosts  
No obvious malicious activity was observed in this traffic sample.

### Security Relevance
Understanding packet-level data allows security analysts to:
- Detect abnormal traffic patterns  
- Identify potential intrusions or malware communication  
- Investigate incidents using network evidence  
This skill is essential in Security Operations Center (SOC) environments.

---

## Activity 2: Capture Your First Packet (tcpdump)

### Description
In this activity, I captured live network traffic using tcpdump in a Linux environment. I also saved and analyzed captured packets for further inspection.

### Key Tasks Performed
#### 1. **Identify Network Interfaces**  
Verified available interfaces using:
```bash
ifconfig
sudo tcpdump -D
```
- Selected eth0 as the primary Ethernet interface for packet capture.

#### 2. **Capture Live Traffic**
Captured a small sample of packets for analysis:
```bash
sudo tcpdump -i eth0 -v -c5
```
- -i eth0: Capture packets from eth0 interface.
- -v: Display verbose packet information.
- -c5: Capture 5 packets and exit.

#### 3. **Capture and Save Specific Traffic**
Captured HTTP traffic (TCP port 80) to a file:
```bash
sudo tcpdump -i eth0 -nn -c9 port 80 -w capture.pcap &
```
- -nn: Disable IP and port name resolution for security.
- port 80: Filter only HTTP traffic.
- -w capture.pcap: Save packets to a .pcap file.
- &: Run tcpdump in the background to allow simultaneous traffic generation.

Generated traffic using:
```bash
curl opensource.google.com
```

#### 4. **Analyze Saved Packets**
##### Verbose inspection:
```bash
sudo tcpdump -nn -r capture.pcap -v
```
##### Hexadecimal and ASCII inspection:
```bash
sudo tcpdump -nn -r capture.pcap -X
```

#### 5. **Verify Capture File**
```bash
ls -l capture.pcap
```


<!--
- Captured live traffic:
  - `sudo tcpdump -i eth0 -v -c5`
- Captured and saved packets:
  - `sudo tcpdump -i eth0 -nn -c9 port 80 -w capture.pcap &`
- Generated traffic using:
  - `curl opensource.google.com`
- Analyzed saved packets:
  - `sudo tcpdump -nn -r capture.pcap -v`
  - `sudo tcpdump -nn -r capture.pcap -X`
-->
### Key Findings
- Successfully captured HTTP traffic over port 80  
- Observed TCP handshake behavior (SYN, SYN-ACK, ACK)  
- Identified packet metadata such as TTL, flags, sequence numbers  
- Verified captured data using `.pcap` file analysis  
- Learned importance of disabling name resolution (`-nn`) for security  

### Reflection

This activity highlighted the practical use of tcpdump as a lightweight, command-line network analyzer. By capturing and analyzing packets in real-time, I gained a deeper understanding of TCP/IP behavior, HTTP traffic, and how to efficiently filter and save network traffic for forensic or monitoring purposes. Disabling name resolution and filtering traffic are critical practices for maintaining security during network analysis.

---

## Activity 3: Research Network Protocol Analyzers

### Description
This activity involved researching and comparing two widely used network protocol analyzers: Wireshark and tcpdump.
The goal was to understand the differences and similarities between graphical and command-line tools, and evaluate their suitability for cybersecurity tasks.

### Differences

| Feature | Wireshark | tcpdump |
|--------|----------|---------|
| Interface | Graphical User Interface (GUI) | Command-Line Interface (CLI) |
| Features | Advanced filtering, visualization, colorization | Basic filtering, text-based output |
| Resource Usage | Higher resource consumption | Lightweight and efficient |

### Similarities

- Both are **network protocol analyzers (packet sniffers)**  
- Both are **open-source and free to use**  
- Both support **packet capturing and filtering by protocol**
- Both allow **filtering by protocol, port, and IP address**, helping analysts focus on relevant traffic.  

**Limitations:**  
- **Wireshark:** Requires GUI access and higher system resources.  
- **tcpdump:** CLI-only, requires proficiency with command-line filters to interpret captures effectively.

**Typical Use Cases:**  
- **Wireshark:** Ideal for visual analysis, troubleshooting complex network flows, and analyzing large capture files.  
- **tcpdump:** Preferred for lightweight, automated, or scriptable packet captures on servers or low-resource systems.

### Analysis
Wireshark is more suitable for detailed analysis and beginners due to its visual interface, while tcpdump is ideal for quick captures, remote systems, and low-resource environments.

### Reflection
Comparing Wireshark and tcpdump highlighted how both tools complement each other: Wireshark provides detailed, visual insights, while tcpdump enables efficient, low-overhead captures. Mastering both tools enhances a security analyst’s ability to monitor, troubleshoot, and investigate network traffic effectively.

---

## Key Skills Demonstrated

- Network traffic analysis  
- Packet inspection and protocol understanding  
- Use of filtering techniques for investigation  
- Linux command-line proficiency  
- Use of cybersecurity tools (Wireshark, tcpdump)  
- Analytical thinking in identifying network behavior  

---

## Lesson Learned

This lab significantly improved my understanding of how network traffic operates and how security analysts investigate it. Initially, analyzing packet data was overwhelming due to the complexity of protocols and raw data.

However, by practicing with Wireshark and tcpdump, I developed confidence in:
- Filtering relevant traffic  
- Understanding packet structure  
- Identifying normal vs suspicious behavior  

This hands-on experience reinforced the importance of network monitoring in cybersecurity.

---

## Conclusion

This project provided practical exposure to essential network monitoring and analysis techniques used in cybersecurity. By working with both Wireshark and tcpdump, I gained a deeper understanding of how network traffic is captured, filtered, and analyzed.

The ability to interpret packet-level data is a critical skill for detecting threats, investigating incidents, and maintaining network security. This project demonstrates my capability to use professional tools, analyze real network data, and apply structured investigative techniques.

Overall, this lab strengthens my foundation in network security and prepares me for real-world cybersecurity roles involving traffic analysis and incident detection.















# Lab Module 7: Automate Cybersecuirty Tasks With Pyhton
## Objective
The goal of this portfolio is to demonstrate my understanding and practical application of Python concepts as applied to cybersecurity. This includes automation, data parsing, conditional logic, iterative statements, and file operations—all essential skills for real-world security tasks such as log analysis, threat detection, and system monitoring.

---

## Projects / Labs Included
### 1. Python Section 1 Concepts
**Sections Covered:** Comments, Functions, Conditional Statements, Iterative Statements  
**Description:**
- Explored basic Python syntax and program structure.
- Practiced creating comments, using built-in functions (print(), type(), range()).
- Applied conditional statements (if, elif, else, logical operators) to make decisions in code.
- Used iterative statements (for, while, break, continue) to process sequences.


#### Comments
##### Single-line comment
```python
# Print approved usernames
```
##### Multi-line comment / Docstring
```python
"""
The estimate_attempts() function takes in a monthly
login attempt total and a number of months and
returns their product.
"""
```
#### Conditional Statements
**Keywords and Operators:** if, elif, else, and, or, not  
```python
if username == "bmoreno" and login_attempts < 5:
    print("Access granted")
elif status == 500:
    print("Server error")
else:
    print("Access denied")
```

#### Iterative Statements
**Keywords and Operators:** for, while, break, continue  
```python
for user in ["bmoreno", "tshah", "elarson"]:
    print(user)

while login_attempts < 5:
    login_attempts += 1
    print(login_attempts)
```

#### User-defined Functions
- def to define a function
- return to output values
```python
def calculate_fails(total_attempts, failed_attempts):
    fail_percentage = failed_attempts / total_attempts
    return fail_percentage

print(calculate_fails(50, 5))
```

#### Built-in Functions
**Keywords and Operators:** print(), type(), range(), max(), min(), sorted()  
```python
print(max(10, 15, 5))  # 15
print(type(True))      # <class 'bool'>
print(sorted([10, 15, 5]))  # [5, 10, 15]
```

#### Importing Modules and Libraries
- import keyword
- from module import function
```python
import statistics
from statistics import mean, median

print(mean([1, 2, 3]))
```


---


### 2. Python Section 2 Concepts
**Sections Covered:** User-defined Functions, Built-in Functions, Importing Modules and Libraries  
**Description:**
- Learned to create reusable functions with def and return.
- Explored built-in functions (max(), min(), sorted()).
- Imported Python standard libraries (statistics) and used functions like mean() and median().


#### User-defined Functions
```python
def greet_employee():
    print("Welcome!")

def calculate_fails(total_attempts, failed_attempts):
    fail_percentage = failed_attempts / total_attempts
    return fail_percentage
```

#### Built-in Functions
**Keywords and Operators:** max(), min(), sorted()  
```python
print(max(10, 15, 5))  # 15
print(min(10, 15, 5))  # 5
print(sorted([10, 15, 5]))  # [5, 10, 15]
print(sorted(["bmoreno", "tshah", "elarson"]))  # ['bmoreno','elarson','tshah']
```

#### Importing Modules and Libraries
```python
import statistics
from statistics import mean
from statistics import mean, median
```


---


### 3. Python Section 3 Concepts
**Sections Covered:** String Methods, List Methods, Regular Expressions, Advanced Syntax  
**Description:**
- Manipulated strings (upper(), lower(), index()) and lists (append(), insert(), remove()).
- Applied concatenation (+) and slicing ([]) for strings and lists.


#### Built-in Functions
**Keywords and Operators:** str(), len()
```python
str(10)  # '10'
print(len("security"))  # 8
```

#### String Methods
**Keywords and Operators:** .upper(), .lower(), .index()  
```python
print("Security".upper())  # 'SECURITY'
print("Security".lower())  # 'security'
print("Security".index("c"))  # 2
```

#### List Methods
**Keywords and Operators:** .insert(), .remove(), .append(), .index()  
```python
username_list = ["elarson", "fgarcia", "tshah"]
username_list.insert(2, "wjaffrey")
username_list.remove("elarson")
username_list.append("btang")
print(username_list.index("tshah"))
```

#### Additional Syntax  
Concatenation: +  
Bracket notation: []  
```python
device_id = "IT" + "nwp12"  # 'ITnwp12'
users = ["elarson", "bmoreno"] + ["tshah", "btang"]
print(users[2])  # 'tshah'
```

#### Regular Expressions
re.findall(), \w, \d, ., \s, +, *, {}
```python
import re
re.findall("\w+", "a53-32c .E")  # ['a53','32c','E']
re.findall("\d", "a53-32c .E")    # ['5','3','3','2']
```

---


### 4. Python Section 4 Concepts
**Sections Covered:** File Operations, Parsing  
**Description:**
- Practiced opening, reading, writing, and appending files using open() and with.
- Used .split() and .join() methods to parse and format text data.


#### File Operations
**Keywords and Operators:** `with`, `open()`, `.read()`, `.write()`, `as`
```python
with open("login_attempts.txt", "r") as file:
    file_text = file.read()

with open("access_log.txt", "a") as file:
    file.write("jrafael")
```

#### Parsing
**Keywords and Operators:** .split(), .join()
``` python
approved_users = "elarson,bmoreno,tshah".split(",")
removed_users = "wjaffrey jsoto abernard".split()
approved_users_string = ",".join(["elarson","bmoreno","tshah"])
```

---

## How to Run a Python Script

1. Ensure your Python file(s) are in the same folder as any required input files (e.g., `allow_list.txt`, `remove_list.txt`).
2. Open a terminal and navigate to the project folder.
3. Run any Python file using the following command:

```bash
python <filename>.py
```

**Example:**
```bash
python update_allow_list.py
python calculate_fails.py
python process_logs.py
```

**Hint:** Replace <filename>.py with the name of the Python script you want to execute.

---

## Reflection
This module helped me consolidate fundamental Python concepts while applying them in cybersecurity-related scenarios.
Practicing conditional logic, loops, and file operations gave me insight into automating routine security tasks.
Working with string parsing and regex strengthened my ability to extract and analyze critical data efficiently.
I now feel more confident using Python for incident response, log analysis, and building scripts to support cybersecurity operations.

---

## Conclusion

This module demonstrates a progression from basic Python syntax to practical cybersecurity applications. By combining sections learned in this module, I can showcase my ability to automate tasks, analyze data, and develop Python scripts that enhance operational efficiency and security awareness.















# Lab Module 8: Put It To Work Prepare For Cybersecurity Jobs

## Lab Overview

This lab simulates real-world responsibilities of a junior cybersecurity analyst, including log analysis, professional development through security organizations, and leveraging generative AI for security awareness. The activities demonstrate both technical and analytical skills, as well as the ability to apply modern tools in cybersecurity workflows.

---

## Objectives
- Analyze system logs to identify suspicious activity and potential threats
- Explore cybersecurity organizations aligned with career interests
- Apply generative AI techniques to improve security awareness and productivity

---

## Activity 1: Analyze Event Logs
### Description

In this activity, I analyzed a system log file to identify abnormal behavior, potential security threats, and policy violations. This task simulates real-world Security Operations Center (SOC) monitoring.

### Log Sample
```text
TIMESTAMP           | USER      | SOURCE_IP      | EVENT_TYPE
--------------------|-----------|----------------|-------------
2025-07-30 08:15:00 | guest     | 10.0.0.100     | Login_Failed
2025-07-30 08:20:20 | John.Doe  | 192.168.1.5    | File_Access
2025-07-30 08:30:40 | admin     | 203.0.113.25   | Login_Success
```

### Key Findings
#### Suspicious Events Identified
##### Multiple Failed Login Attempts (Medium Risk)
- Repeated login failures from a single IP address  
- Indicates a potential **brute-force attack attempt**
##### Sensitive File Exposure (High Risk)
- Financial file copied to a public shared location  
- Possible **data exfiltration** or **insider threat**
##### Unusual AUnusual Admin Login (High Risk)
- Admin login from external IP  
- Possible **account compromise**

### Risk Assessment
- High Risk: External admin login, sensitive data exposure
- Medium Risk: Repeated failed login attempts

### Recommendations
- Investigate and verify legitimacy of external admin login
- Reset credentials if compromise is suspected
- Restrict access to sensitive directories
- Monitor and block suspicious IP addresses
- Implement alerting for repeated login failures

---

## Activity 2: Explore Cybersecurity Organizations
### Part 1: Security Interests
- Incident response and threat detection
- Protection of sensitive data
- Security monitoring and log analysis (SIEM tools)

### Part 2: Organizations and Objectives
**ISACA**

Focuses on IT governance, risk management, and cybersecurity. Provides frameworks, certifications, and guidance for managing and securing enterprise systems.

**(ISC)²**

A global nonprofit organization that develops cybersecurity certifications and promotes best practices in information security.

**SANS Institute**

Provides cybersecurity training, certifications, and research with a strong emphasis on hands-on skills such as incident response and threat detection.

---

## Activity 3: Use Generative AI for Security Awareness
### Description
This activity involved using a generative AI tool with the TCREI prompting framework to create a reference guide on phishing and malware awareness.

### Prompting Approach (TCREI Framework)
- **Task:** Create a phishing and malware awareness guide
- **Context:** Target audience is non-technical employees
- **Evaluate:** Reviewed clarity, completeness, and usability
- **Iterate:** Refined prompt to improve structure and relevance

### Final Prompt: 
" As a cybersecurity analyst, create a clear and comprehensive reference guide on identifying phishing emails and malware threats for non-technical employees.
Include common phishing indicators, malware warning signs, real-world examples, and best practices for detection and prevention.
Format the guide using bullet points and ensure the tone is simple and easy to understand. "

### Outcome

The final output was a structured, user-friendly guide that can be used for security awareness training within an organization.

### Reflection

Evaluating and iterating improved the clarity, structure, and effectiveness of the generated content. This process ensured the final output was practical, relevant, and suitable for real-world use.

---

## Skills Demonstrated
- Log analysis and threat identification
- Security risk assessment
- Understanding of cybersecurity organizations and career pathways
- Use of generative AI for cybersecurity tasks
- Analytical thinking and problem-solving

--- 

## Conclusion

This lab strengthened my ability to perform core cybersecurity tasks, including analyzing system activity, identifying potential threats, and applying modern tools such as generative AI. It also helped me align my professional interests with relevant organizations, supporting my long-term career development in cybersecurity.















