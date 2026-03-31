# Module 5: Assets, Threats And Vulnerabilities

## Overview

This document summarizes my learning on the topic of **Assets, Threats, and Vulnerabilities** from foundational cybersecurity modules, including Operating Systems, Linux, command-line usage, and database fundamentals. It highlights both **theoretical understanding** and **practical application**, emphasizing the identification, management, and mitigation of risks in real-world scenarios.

---

## Section 1: Introduction to Asset Security

### Key Concepts
- **Security Risk Planning**: Involves managing assets, threats, and vulnerabilities.  
  Risk = Likelihood × Impact.  
  Focuses on protecting Confidentiality, Integrity, and Availability (CIA) of assets.
- **Asset Management**: Tracking assets and associated risks through an asset inventory and classification.  
  Classification levels:  
  - Restricted – highest sensitivity, strict need-to-know  
  - Confidential – significant negative impact if disclosed  
  - Internal-only – accessible to employees/partners  
  - Public – no negative impact if released
- **Data States**: Protection applies to data:
  - At Rest – stored, not being accessed  
  - In Transit – traveling across networks  
  - In Use – currently being accessed
- **Cloud Security**: Shared responsibility model in SaaS, PaaS, IaaS; clients handle identity and data, providers secure infrastructure.
- **NIST Cybersecurity Framework (CSF)**: Functions: Identify, Protect, Detect, Respond, Recover, Govern
- **Risk Register**: Central record of vulnerabilities prioritized by likelihood and impact
- **Operational Environment**: Consider local factors such as employee distribution and crime rates in risk assessment

### Real-World Example
- A company moving sensitive financial data to the cloud must classify data, track its assets, and assign responsibilities under the shared responsibility model to avoid breaches.  
- Using NIST CSF, the IT team can systematically identify vulnerabilities, protect systems, and recover quickly from incidents.

### My Practical Understanding
- I understand how to categorize assets, quantify risk, and consider environmental factors in making risk management decisions.  
- Awareness of the differences in data states helps me choose the right security controls for storage, transmission, and active processing.

### How I Apply This
- In lab exercises, I maintain a complete asset inventory and create a risk register to prioritize vulnerabilities.  
- When experimenting with cloud platforms, I document which responsibilities are mine (data, identity) versus the provider’s (infrastructure).

---

## Section 2: Protect Organizational Assets

### Key Concepts
- **Security Controls**:  
  - Technical: Encryption, firewalls  
  - Operational: Routine scans, monitoring  
  - Managerial: Security awareness training
- **Access Principles**:  
  - Principle of Least Privilege (PoLP)  
  - Separation of Duties to prevent misuse
- **Data Roles & Governance**:  
  - Data Owner: Decides access and destruction  
  - Data Custodian: Maintains safe storage and handling  
  - Data Lifecycle: Collect → Store → Use → Archive → Destroy
- **Regulations**: GDPR (EU), PCI DSS (credit card), HIPAA (health information)
- **Cryptography**:  
  - Symmetric (AES, Triple DES), Asymmetric (RSA, DSA), Hashing with Salting
- **Authentication Systems**:  
  - MFA (Knowledge, Ownership, Characteristic)  
  - SSO to consolidate logins
- **Authorization Frameworks**: MAC, DAC, RBAC
- **NIST SP 800-53 (AC-6)**: Guidelines for least privilege, auditing, and access revocation

### Real-World Example
- A healthcare company implementing HIPAA must enforce MFA and encrypt sensitive patient records.  
- Role-based access ensures only doctors can view patient histories, while administrative staff can only schedule appointments.

### My Practical Understanding
- I know how to map controls to risks, configure authentication methods, and implement encryption strategies in labs.  
- I understand the interplay between organizational policy and technical enforcement.

### How I Apply This
- Implemented PoLP in lab environments, created role-based access control models, and applied encryption to sample datasets.  
- Designed workflows that align with GDPR and PCI DSS requirements for secure data handling.

---

## Section 3: Vulnerabilities in Systems

### Key Concepts
- **Vulnerability Management**: Continuous identification, analysis, and remediation
- **Zero-day Exploit**: Unknown vulnerabilities exploited before patches exist
- **Defense in Depth**: Layered security (Perimeter → Network → Endpoint → Application → Data)
- **Vulnerability Assessment**: Internal reviews, risk assessment, remediation strategies
- **Scanning Strategies**: External/Internal, Authenticated/Unauthenticated, Limited/Comprehensive
- **Penetration Testing**: Open-box, Closed-box, Partial knowledge
- **Reporting Resources**: CVE, CVSS, OWASP Top 10
- **CI/CD Pipeline Security**: Automating software releases introduces risks like exposed secrets

### Real-World Example
- A developer patching web applications follows OWASP Top 10 guidance to prevent SQL injection and XSS attacks in the CI/CD pipeline.  
- Vulnerability assessments reveal misconfigured servers before they can be exploited.

### My Practical Understanding
- Understanding the difference between scanning types allows me to simulate attacks accurately and prioritize remediation.  
- Knowledge of CVE and CVSS helps me communicate risk severity effectively.

### How I Apply This
- Conduct vulnerability scans in lab environments, document findings, and propose remediation strategies.  
- Perform mock penetration tests using limited and full-knowledge scenarios to evaluate defense mechanisms.

---

## Section 4: Threats to Asset Security

### Key Concepts
- **Social Engineering**: Exploiting human behavior (Baiting, Phishing, Quid Pro Quo, Tailgating, Watering Hole)  
  Variants: Smishing, Vishing, Spear Phishing, Whaling
- **Malware Types**: Virus, Worm, Trojan, Ransomware, Spyware, Rootkit, Botnet
- **Web-Based Exploits**: XSS (Reflected, Stored, DOM-based), SQLi (In-band, Out-of-band, Inferential)  
  Mitigation: Input validation, prepared statements
- **Threat Modeling**: Proactive risk assessment (PASTA, STRIDE frameworks)
- **Additional Threats**: USB baiting, brute-force attacks, insider threats, shadow IT

### Real-World Example
- Phishing emails targeting employees can lead to ransomware infection and data exfiltration.  
- STRIDE threat modeling helps IT teams anticipate attacks and plan countermeasures before incidents occur.

### My Practical Understanding
- Recognizing attack vectors allows me to design defenses not just for systems, but for people.  
- Threat modeling frameworks help me prioritize mitigations based on likely risks.

### How I Apply This
- Conduct tabletop exercises simulating social engineering attacks to test policies.  
- Configure lab environments to test malware containment and apply web exploit prevention strategies.

---

## Additional Notes & Professional Enhancements
- Demonstrated understanding of **security frameworks** (NIST, OWASP, PASTA, STRIDE) aligns with industry standards.  
- Awareness of **regulatory compliance** makes my portfolio relevant to employers in finance, healthcare, and cloud industries.  
- Practical exercises (scans, penetration tests, encryption, access control) showcase applied technical skills, not just theory.  

---

## Reflection

Studying the module of **Assets, Threats, and Vulnerabilities** has deepened my understanding of how critical it is to recognize and protect organizational resources. I realized that cybersecurity is not solely about implementing technical controls, but also about adopting a holistic approach that accounts for people, processes, and technology. Through practical exercises, such as creating asset inventories, performing vulnerability scans, and simulating threat scenarios, I gained hands-on experience in identifying weaknesses and implementing effective safeguards. These activities highlighted that even seemingly minor vulnerabilities, such as weak passwords or outdated software, can expose an organization to significant risks if left unaddressed. Additionally, I learned the importance of prioritizing risks based on their likelihood and potential impact, ensuring that critical assets receive the highest level of protection. Overall, this topic has emphasized the importance of proactive thinking, anticipating threats before they occur, and continuously learning and adapting to an ever-evolving cybersecurity landscape.  

---

## Conclusion

Understanding **Assets, Threats, and Vulnerabilities** is foundational to effective cybersecurity management. By identifying valuable assets, evaluating potential threats, and addressing system vulnerabilities, organizations can implement targeted measures to safeguard their resources. This knowledge has direct real-world applicability, from securing databases and cloud environments to developing policies that mitigate both human and technical risks. Through my practical experience with risk assessment, threat modeling, and vulnerability management, I am better equipped to contribute to organizational security initiatives. Mastery of this topic strengthens my ability to analyze risks comprehensively, implement protective strategies, and maintain resilience against evolving cyber threats, demonstrating both technical competence and a strategic understanding of cybersecurity.
