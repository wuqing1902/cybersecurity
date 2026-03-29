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
