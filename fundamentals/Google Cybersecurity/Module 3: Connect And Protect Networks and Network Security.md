# Module 3: Connect And Protect Networks and Network Security

## Section 1: Network Architecture

### Key Concepts
- **Networking Basics:**  
  A network is a group of connected devices.  
  - **LAN (Local Area Network):** Covers small areas like homes or offices.  
  - **WAN (Wide Area Network):** Covers large areas like cities or countries.  

- **Network Devices:**  
  - **Hub:** Broadcasts data to all devices.  
  - **Switch:** Sends data only to the intended device using MAC addresses.  
  - **Router:** Connects multiple networks and directs traffic using IP addresses.  
  - **Modem:** Connects a router to the internet via ISP.  

- **Cloud Computing:**  
  - **SaaS:** Software applications (e.g., Office 365).  
  - **IaaS:** Virtual infrastructure/storage (e.g., AWS EC2).  
  - **PaaS:** Developer platforms (e.g., Google App Engine).  
  - **Benefits:** Scalability, reliability, cost-efficiency.  
  - **SDN (Software-Defined Network):** Uses virtual devices for routing and switching.  

- **TCP/IP Model Layers:**  
  1. **Network Access:** Hardware, ARP, switches, hubs.  
  2. **Internet:** Delivery via IP and ICMP.  
  3. **Transport:** TCP (reliable) vs UDP (fast, connectionless).  
  4. **Application:** Services like HTTP (80), HTTPS (443), DNS (53).  

- **Packet Structure:** Header (addresses & protocol), Body (data), Footer (error checking).  

- **TCP Log Analysis:** Flags: `[S]` Start, `[F]` Finish, `[P]` Push, `[R]` Reset, `[.]` Acknowledgment.  

### Real-World Example
- Home Wi-Fi: Router assigns IP addresses via DHCP, switches connect devices like laptops and printers, and traffic to Google.com is routed via WAN.

### My Practical Understanding
- Understand how each network device functions, TCP/IP layers structure communication, and how cloud computing improves network scalability.

### How I Apply This
- Configuring small office networks and troubleshooting connectivity issues.  
- Analyzing TCP logs to identify connection issues or suspicious traffic.

---

## Section 2: Network Operation

### Key Concepts
- **Management Protocols:**  
  - **NAT:** Translates private IPs to public IP for internet access.  
  - **DHCP:** Auto-assigns IPs, gateways, DNS.  
  - **SNMP:** Monitors devices and bandwidth.  

- **Email Protocols:** POP3 (download, port 110/995), IMAP (sync, port 143/993), SMTP (send, port 25/587).  

- **Wireless Security:** WEP → WPA → WPA2 → WPA3 (SAE prevents KRACK attacks).  

- **Network Segmentation & Zones:** Subnetting for efficiency and security. Security zones: Uncontrolled (Internet), Controlled (internal), Restricted (confidential).  

- **Proxy Servers:** Forward proxies control user internet access; reverse proxies control external access to internal servers.  

- **VPNs:** Encrypt data and mask virtual locations using encapsulation.  

### Real-World Example
- Company Wi-Fi using WPA3, VPN access for remote employees, and forward proxy limiting social media access during work hours.

### My Practical Understanding
- Recognize importance of network segmentation, secure wireless protocols, and monitoring tools to maintain performance and security.

### How I Apply This
- Configuring DHCP, NAT, and VPN for secure home/office networks.  
- Using SNMP for monitoring traffic and detecting anomalies.

---

## Section 3: Secure Against Network Intrusions

### Key Concepts
- **Common Attacks:** DoS/DDoS, SYN Flood, ICMP Flood/Ping of Death.  

- **Interception Techniques:** Packet Sniffing (tcpdump, Wireshark), IP Spoofing, On-path Attack, Smurf Attack.  

- **Log Analysis:** ICMP errors like `udp port 53 unreachable` may indicate DNS failure or firewall blocking.  

### Real-World Example
- Detecting DDoS traffic in logs at a cloud-hosted web server; analyzing ICMP packet drops to identify network issues.

### My Practical Understanding
- Identify types of attacks and interception methods, and read logs for early warning signs.

### How I Apply This
- Use Wireshark/tcpdump to monitor suspicious traffic.  
- Apply firewall rules to mitigate SYN floods and ICMP attacks.

---

## Section 4: Security Hardening

### Key Concepts
- **Core Concepts:** Hardening reduces attack surface; defense-in-depth uses layered security.  

- **OS Hardening:** Patch updates, baseline configs, remove unused apps.  
- **Authentication Hardening:** MFA (knowledge, possession, inherence).  
- **Brute Force Protection:** Salting/hashing passwords, CAPTCHA, lockout policies.  

- **Hardening Tools:**  
  - **IDS:** Monitors & alerts.  
  - **IPS:** Stops detected anomalies.  
  - **SIEM:** Aggregates logs for analysis.  

- **Cloud Hardening:** IAM for user roles, cryptographic erasure to securely delete data.  

- **NIST CSF Framework:** Identify → Protect → Detect → Respond → Recover.  

- **Testing:** Sandboxes isolate suspicious software for safe testing.  

### Real-World Example
- Corporate servers patched regularly, MFA enabled, SIEM monitoring all logs, sandbox for new software deployment.

### My Practical Understanding
- Understand how layered security reduces risks and how authentication & monitoring tools prevent breaches.

### How I Apply This
- Implement MFA on personal accounts, configure IDS alerts in lab environment, test suspicious apps in sandbox.

---

## Reflection
Through this module, I have gained a comprehensive understanding of how networks are structured, operate, and are protected against intrusions. I learned not only the technical aspects of devices, protocols, and architectures but also the practical importance of securing networks and data. Understanding how LANs, WANs, and cloud computing environments interact has strengthened my foundation in network design, while learning management protocols such as DHCP, NAT, and SNMP has highlighted how devices communicate efficiently and securely. Exploring common network attacks and interception tactics has increased my awareness of potential vulnerabilities, and studying security hardening strategies—including OS hardening, multi-factor authentication, and the use of IDS, IPS, and SIEM tools—has shown me how layered defenses can significantly reduce risk. This module has also enhanced my analytical and problem-solving skills; analyzing TCP/IP logs, configuring security tools, and understanding network segmentation have given me confidence in monitoring and maintaining secure network environments. I now approach network security not just as a theoretical concept but as a practical responsibility. I can apply these skills by setting up and securing networks, monitoring traffic for anomalies, and implementing best practices to mitigate risks. Overall, this knowledge forms a strong foundation for advancing into areas such as cloud security, penetration testing, and enterprise network management, allowing me to contribute effectively to secure and efficient network operations in any organization.
