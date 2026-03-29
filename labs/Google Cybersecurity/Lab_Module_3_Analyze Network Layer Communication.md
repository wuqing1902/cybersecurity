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

