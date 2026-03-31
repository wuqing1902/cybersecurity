# Lab Module 5: Protect Organizational Assets

This lab focuses on protecting organizational data through secure handling practices, encryption, hashing, and access control improvements. It consists of four activities that simulate real-world cybersecurity scenarios.

---

## Activity 1: Determine Appropriate Data Handling Practices

**Objective:**  
Analyze a data leak incident and recommend improvements using the principle of least privilege.

**Incident Analysis:**  
The data leak occurred because access to a folder containing sensitive internal documents was not properly restricted or revoked. The manager failed to remove access after the meeting, and the employee mistakenly shared the entire folder instead of limited materials. This demonstrates poor enforcement of access control and lack of oversight.

**NIST SP 800-53: AC-6 Summary:**  
NIST SP 800-53 AC-6 defines the principle of least privilege, which ensures users are granted only the minimum access necessary to perform their tasks. It also outlines implementation strategies and enhancements to strengthen access control and reduce the risk of data exposure.

**Recommendations:**  
- Restrict access to sensitive resources based on user roles  
- Automatically revoke access after a defined period  

**Justification:**  
Limiting access based on roles ensures that only authorized users can view sensitive data. Automatic revocation reduces the risk of forgotten permissions, minimizing human error and preventing unintended data exposure.

---

## Activity 2: Decrypt an Encrypted Message

**Objective:**  
Use Linux commands to decrypt encrypted data and recover hidden messages.

**Process Overview:**  
- Listed directory contents using `ls`  
- Read instructions using `cat README.txt`  
- Navigated directories using `cd`  
- Identified hidden files using `ls -a`  
- Decrypted a Caesar cipher using `tr`  
- Decrypted a file using `openssl`  

**Key Commands Used:**  
```bash
ls
cat README.txt
cd caesar
ls -a
cat .leftShift3 | tr "d-za-cD-ZA-C" "a-zA-Z"
cd ~
openssl aes-256-cbc -pbkdf2 -a -d -in Q1.encrypted -out Q1.recovered -k ettubrute
cat Q1.recovered
```

**Reflection:**  
This activity strengthened my understanding of encryption and decryption processes. It demonstrated how classical ciphers and modern encryption techniques can be reversed using the correct tools and commands, reinforcing the importance of protecting sensitive data.

---

## Activity 3: Create Hash Values

**Objective:**  
Generate and compare hash values to verify file integrity.

**Process Overview:**
- Displayed file contents using cat
- Generated SHA-256 hashes using sha256sum
- Saved hashes to files
- Compared hashes manually and using cmp

**Key Commands Used:**
```bash
cat file1.txt
cat file2.txt
sha256sum file1.txt
sha256sum file2.txt
sha256sum file1.txt >> file1hash
sha256sum file2.txt >> file2hash
cat file1hash
cat file2hash
cmp file1hash file2hash
```

**Findings:**  
Although both files appeared identical, their hash values were different. This indicates that even a small unseen difference (such as whitespace or hidden characters) can produce a completely different hash.

**Reflection:**  
This activity highlighted the importance of hashing for ensuring data integrity. It showed how security professionals can detect even the smallest modifications to files, which is critical for identifying tampering or malicious changes.

---

## Activity 4: Improve Authentication, Authorization, and Accounting

**Objective:**  
Analyze an access control incident and recommend improvements.

**Relevant Employee Record:**

| Name              | Role            | Status     | Authorization | IP Address       | End Date   |
|-------------------|----------------|------------|---------------|------------------|------------|
| Robert Taylor Jr. | Legal attorney | Contractor | Admin         | 152.207.255.255  | 12/27/2019 |

**Relevant Log Evidence:**

```plaintext
Event Type: Information  
Date: 10/03/2023  
Time: 8:29:57 AM  
User: Legal\Administrator  
IP Address: 152.207.255.255  
Action: Payroll event added (FAUX_BANK)
```

**Analysis:**  
The log shows that a user with administrative privileges accessed the system and performed a payroll-related action. The IP address matches a contractor account (Robert Taylor Jr.), whose contract ended in 2019, indicating unauthorized or unmanaged access.

**Notes (Investigation Findings):**
- Event occurred on 10/03/2023 using IP address 152.207.255.255
- User identified as Legal/Administrator (Robert Taylor Jr.)

**Issues Identified:**
- Contractor account remained active after contract ended in 2019
- User had excessive privileges (admin access to sensitive systems)

**Recommendations:**
- Implement automatic account expiration for inactive or former employees
- Apply role-based access control (RBAC) with limited privileges
- Enable multi-factor authentication (MFA)

**Reflection:**  
This activity emphasized the importance of proper access control management. Poor account lifecycle management and excessive privileges can lead to serious security incidents. Implementing stricter authentication and authorization controls reduces the risk of unauthorized access.

---

## Conclusion

The Protect Organizational Assets lab provided practical experience in securing data through multiple approaches, including data handling policies, encryption, hashing, and access control mechanisms.

Through these activities, I developed a stronger understanding of how to:
- Prevent data leaks using least privilege principles
- Decrypt and analyze encrypted data
- Verify data integrity using hashing
- Strengthen authentication and authorization controls

These skills are essential for maintaining a secure organizational environment and protecting sensitive information from potential threats.
