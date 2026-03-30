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
