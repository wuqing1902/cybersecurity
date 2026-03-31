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
