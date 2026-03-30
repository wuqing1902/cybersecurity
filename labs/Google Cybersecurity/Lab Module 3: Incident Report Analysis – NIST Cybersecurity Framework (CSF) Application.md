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
