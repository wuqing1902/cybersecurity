# Module 2: Play It Save Manage Security Risk

## Module 1: Security Domains

### Key Concepts
- **CISSP 8 Security Domains**:  
  1. **Security and Risk Management** – Security goals, risk mitigation, compliance, business continuity.  
  2. **Asset Security** – Protecting digital and physical assets, proper handling, and secure destruction of data.  
  3. **Security Architecture and Engineering** – Designing secure systems using tools like SIEM.  
  4. **Communication and Network Security** – Securing physical and wireless networks.  
  5. **Identity and Access Management (IAM)** – Identification, authentication, and authorization using least privilege principle.  
  6. **Security Assessment and Testing** – Identifying vulnerabilities through audits and testing.  
  7. **Security Operations** – Managing breaches, implementing preventative measures, and incident handling.  
  8. **Software Development Security** – Applying secure coding practices in the software lifecycle.

- **Security Posture**: Organization’s ability to defend assets and respond to threats.  
- **Risk**: Anything impacting Confidentiality, Integrity, and Availability (CIA triad).  
- **NIST Risk Management Framework (RMF)**: Prepare, Categorize, Select, Implement, Assess, Authorize, Monitor.  
- **Business Continuity**: Maintaining productivity through risk and disaster recovery planning.  
- **Shared Responsibility**: Every individual in an organization contributes to lowering risk.  

### Real-World Example
- Large enterprises use IAM to restrict access to sensitive data, reducing insider threats.  
- Organizations implement business continuity plans to ensure operations continue during cyberattacks or system failures.  

### My Practical Understanding
- Understanding security domains helps identify gaps in organizational defense.  
- Awareness of shared responsibility emphasizes the role of collaboration in risk reduction.  

### How I Apply This
- I practice creating IAM policies and simulate data access scenarios.  
- I draft basic disaster recovery strategies for projects, ensuring continuity under simulated risk conditions.  

---

## Module 2: Security Frameworks and Controls

### Key Concepts
- **Frameworks vs Controls**:  
  - Frameworks: Guidelines for building security programs (e.g., NIST CSF, ISO/IEC 27001).  
  - Controls: Specific safeguards to reduce risks.  

- **Control Categories**:  
  - **Physical**: Gates, locks, CCTV, security personnel.  
  - **Technical**: Firewalls, multi-factor authentication (MFA), encryption.  
  - **Administrative**: Separation of duties, asset classification, authorizations.  

- **CIA Triad**:  
  - **Confidentiality** – Only authorized users access data.  
  - **Integrity** – Data is accurate and reliable.  
  - **Availability** – Data is accessible when needed.  

- **Control Types**: Preventative, Corrective, Detective, Deterrent.  
- **Compliance Standards**: GDPR, PCI DSS, SOC.  
- **NIST CSF v2.0 Functions**: Govern, Identify, Protect, Detect, Respond, Recover.  
- **OWASP Security Principles**: Minimize attack surface, defense in depth, fail securely, avoid security by obscurity.  

### Real-World Example
- Organizations deploy firewalls, MFA, and encryption to protect confidential customer data.  
- Regular audits ensure compliance with GDPR and PCI DSS.  

### My Practical Understanding
- Controls enforce cybersecurity policies; frameworks guide overall strategy.  
- Understanding different control types allows me to select the most effective safeguards for different scenarios.  

### How I Apply This
- I perform simulated access control setups and evaluate firewall policies.  
- I practice documenting security policies in alignment with NIST CSF.  

---

## Module 3: Introduction to Cybersecurity Tools

### Key Concepts
- **Logs**: Event records from firewalls, networks, and servers.  
- **SIEM (Security Information and Event Management)**: Collects and analyzes log data in real-time.  
  - **Types**: Self-hosted, Cloud-hosted, Hybrid.  
  - **Dashboards**: Tools like Splunk or Chronicle visualize alerts and metrics.  

- **Metrics**: Measure software performance (response time, availability, failure rate).  
- **SOAR (Security Orchestration, Automation, and Response)**: Automates repetitive tasks to improve efficiency.  

### Real-World Example
- Security teams use SIEM dashboards to monitor suspicious login attempts or network anomalies.  
- SOAR automates account lockouts after multiple failed login attempts.  

### My Practical Understanding
- Tools like SIEM and SOAR improve monitoring and response efficiency.  
- Logs are the foundation for detecting incidents and understanding attack patterns.  

### How I Apply This
- I practice analyzing logs using Splunk to detect anomalies.  
- I design simple automated responses for repeated security events using SOAR concepts.  

---

## Module 4: Using Playbooks to Respond to Incidents

### Key Concepts
- **Playbooks**: Step-by-step guides for consistent incident response.  
- **Six Phases of Incident Response**:  
  1. Preparation – Planning and user education.  
  2. Detection & Analysis – Identifying breaches.  
  3. Containment – Preventing further damage.  
  4. Eradication & Recovery – Removing threats, restoring systems.  
  5. Post-Incident Activity – Documenting lessons learned.  
  6. Coordination – Sharing findings with stakeholders.  

- **Integration with SIEM & SOAR**: Alerts generated by SIEM, playbooks guide responses, SOAR automates tasks.  
- **Living Documents**: Playbooks require regular updates due to evolving threats.  
- **Common Use Cases**: Ransomware, vishing, Business Email Compromise (BEC), DDoS.  

### Real-World Example
- Organizations respond to ransomware attacks by isolating affected systems, restoring backups, and updating playbooks.  

### My Practical Understanding
- Playbooks ensure uniform response and reduce human error during incidents.  
- Recognizing real-world scenarios helps me contextualize theoretical knowledge.  

### How I Apply This
- I create basic playbooks for simulated attacks and review lessons learned.  
- I practice coordinating responses with teams and automating simple remediation tasks.  

---

## Reflection
Through completing these foundational cybersecurity modules, I have gained a deep understanding of both theoretical frameworks and practical applications essential for protecting organizational assets.

The Security Domains module taught me the importance of a comprehensive security posture, covering risk management, asset protection, identity and access management, and security operations. I now appreciate that cybersecurity is not just a technical challenge but also a strategic and collaborative effort across all levels of an organization. Learning about business continuity and shared responsibility reinforced that security is a team effort and requires proactive planning.

Studying Security Frameworks and Controls enhanced my ability to differentiate between high-level frameworks and specific control mechanisms. Understanding the CIA triad, control types, and compliance standards (e.g., GDPR, PCI DSS) showed me how organizations implement structured safeguards to reduce risk. I also learned how real-world policies and technical controls work together to maintain secure and compliant systems.

The Cybersecurity Tools module provided hands-on exposure to logs, SIEM, and SOAR systems. I realized the critical role these tools play in monitoring, detecting, and automating responses to security events. I gained practical knowledge in analyzing logs, visualizing incidents via dashboards, and automating repetitive security tasks, which strengthened my operational readiness.

Finally, the Playbooks and Incident Response module emphasized the importance of structured, repeatable procedures in responding to security incidents. Understanding the six phases of incident response and the integration of SIEM and SOAR helped me see how theory translates into actionable defense strategies. Creating and practicing playbooks for simulated attacks strengthened my problem-solving and teamwork skills while highlighting the need for continuous learning due to evolving threats.

Overall, these modules have not only improved my technical knowledge but also enhanced my analytical thinking, problem-solving, and ability to apply cybersecurity principles in real-world scenarios. By combining theoretical understanding with hands-on practice, I feel confident in contributing effectively to cybersecurity operations and supporting organizational resilience against cyber threats.


<!--
### ✅ Professional Tips
- Highlight **practical applications** and **tools** you’ve used; employers value hands-on skills.  
- Include **metrics or results** if you can, e.g., “Reduced incident response time by 30% through playbook automation.”  
- Keep **language concise and results-focused**; demonstrate both knowledge and impact.  
-->
