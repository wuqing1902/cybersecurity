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
