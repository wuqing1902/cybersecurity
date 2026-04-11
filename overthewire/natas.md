# Natas
## Introduction 
The OverTheWire Natas wargame focuses on introducing the fundamentals of server-side web security. It is designed to help learners understand common web vulnerabilities and how they can be exploited through practical, hands-on challenges.

## Structure and Access
Each level in Natas is presented as a standalone web application, accessible via a unique URL following the format:
http://natasX.natas.labs.overthewire.org, where X represents the level number.
Unlike other wargames, Natas does not require SSH access. Instead, users log in through the web interface using the designated username (e.g., natas0 for Level 0) along with the corresponding password.

## Objective
The main objective of each level is to retrieve the password for the next level. This typically involves analyzing the web application, identifying vulnerabilities, and exploiting them to gain access to restricted information.
- Passwords for each level are stored on the server in the directory: `/etc/natas_webpass/`
- For example, the password for natas5 is stored in: `/etc/natas_webpass/natas5`, and can only be accessed by specific permission levels (e.g., natas4 and natas5). This reinforces the concept of access control and privilege separation.

## Getting Started
To begin the challenge:
- Username: natas0
- Password: natas0
- URL: http://natas0.natas.labs.overthewire.org

Learners are encouraged to explore each level carefully, inspect web elements, and apply logical thinking to uncover hidden information. Each challenge builds upon previous knowledge, gradually strengthening understanding of web security concepts.

---

