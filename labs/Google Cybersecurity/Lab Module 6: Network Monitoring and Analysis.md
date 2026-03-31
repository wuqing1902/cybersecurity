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

### Key Findings
- Identified communication between local system and external IP (142.250.1.139)  
- Observed ICMP (ping), DNS queries, and HTTP traffic  
- DNS queries revealed domain resolution for `opensource.google.com`  
- TCP traffic showed web requests and responses over port 80  
- Packet inspection revealed protocol layering (Ethernet → IP → TCP/UDP → Application)

---

## Activity 2: Capture Your First Packet (tcpdump)

### Description
In this activity, I captured live network traffic using tcpdump in a Linux environment. I also saved and analyzed captured packets for further inspection.

### Key Tasks Performed
- Identified network interfaces using:
  - `ifconfig`
  - `tcpdump -D`
- Captured live traffic:
  - `sudo tcpdump -i eth0 -v -c5`
- Captured and saved packets:
  - `sudo tcpdump -i eth0 -nn -c9 port 80 -w capture.pcap &`
- Generated traffic using:
  - `curl opensource.google.com`
- Analyzed saved packets:
  - `sudo tcpdump -nn -r capture.pcap -v`
  - `sudo tcpdump -nn -r capture.pcap -X`

### Key Findings
- Successfully captured HTTP traffic over port 80  
- Observed TCP handshake behavior (SYN, SYN-ACK, ACK)  
- Identified packet metadata such as TTL, flags, sequence numbers  
- Verified captured data using `.pcap` file analysis  
- Learned importance of disabling name resolution (`-nn`) for security  

---

## Activity 3: Research Network Protocol Analyzers

### Description
This activity involved researching and comparing two widely used network protocol analyzers: Wireshark and tcpdump.

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

### Analysis
Wireshark is more suitable for detailed analysis and beginners due to its visual interface, while tcpdump is ideal for quick captures, remote systems, and low-resource environments.

---

## Key Skills Demonstrated

- Network traffic analysis  
- Packet inspection and protocol understanding  
- Use of filtering techniques for investigation  
- Linux command-line proficiency  
- Use of cybersecurity tools (Wireshark, tcpdump)  
- Analytical thinking in identifying network behavior  

---

## Reflection

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
