# Project Module 4: Apply Filters to SQL Queries

## Project Description
In this activity, I used SQL queries to investigate potential security incidents involving login attempts and employee devices. By applying filtering techniques such as AND, OR, NOT, and LIKE, I retrieved relevant records from the database. This analysis helped identify suspicious activity, ensured proper targeting for security updates, and supported incident response efforts, demonstrating practical cybersecurity skills.

---

## Retrieve After Hours Failed Login Attempts

A potential security incident occurred after business hours (after 18:00). To investigate, I filtered for failed login attempts that occurred after 18:00.

### Query:
```sql
SELECT *
FROM log_in_attempts
WHERE login_time > '18:00:00'
AND success = 0;
```
### Explanation:
- login_time > '18:00:00' filters for login attempts after 6 PM.
- success = 0 ensures only failed login attempts are returned.
- AND combines both conditions to refine the results.

**Security Impact:** This query helps identify potentially unauthorized access attempts outside normal working hours, which supports timely incident response.

---

## Retrieve Login Attempts on Specific Dates

A suspicious event occurred on May 9, 2022. To investigate, I retrieved login attempts on May 8 and May 9, 2022.

### Query:
```sql
SELECT *
FROM log_in_attempts
WHERE login_date = '2022-05-09'
OR login_date = '2022-05-08';
```

### Explanation:
- Filters records for the two specific dates.
- OR ensures results include login attempts from either date.

**Security Impact:** This allows analysis of events surrounding a specific incident to determine patterns or anomalies.

---

## Retrieve Login Attempts Outside of Mexico

Some suspicious activity did not originate from Mexico. I needed to investigate all login attempts outside Mexico.

### Query:
```sql
SELECT *
FROM log_in_attempts
WHERE country NOT LIKE 'MEX%';
```

### Explanation:
- NOT LIKE 'MEX%' excludes any country starting with MEX (e.g., MEX, MEXICO).
- % is a wildcard representing any number of characters.

**Security Impact:** This helps focus on non-local login attempts that may indicate unauthorized or unusual access.

---

## Retrieve Employees in Marketing

To perform security updates, I identified employees in the Marketing department located in the East building.

### Query:
```sql
SELECT *
FROM employees
WHERE department = 'Marketing'
AND office LIKE 'East%';
```

### Explanation:
- department = 'Marketing' filters employees by department.
- office LIKE 'East%' matches all offices in the East building.
- AND ensures both conditions are applied.

**Security Impact:** This query targets only relevant employees for security updates, minimizing disruption while maintaining system security.

---

## Retrieve Employees in Finance or Sales

To apply a different security update, I needed all employees in Finance or Sales.

### Query:
```sql
SELECT *
FROM employees
WHERE department = 'Finance'
OR department = 'Sales';
```

### Explanation:
- Filters employees in either the Finance or Sales departments.
- OR allows results to include either condition.

**Security Impact:** Ensures updates are applied to the correct employee groups without affecting unrelated departments.

---

## Retrieve All Employees Not in IT

Employees outside the Information Technology (IT) department required a specific security update. I retrieved all employees not in IT.

### Query:
```sql
SELECT *
FROM employees
WHERE department != 'Information Technology';
```

### Explanation:
- != 'Information Technology' excludes IT employees.
- This is an efficient way to target all non-IT employees.

**Security Impact:** This ensures updates are applied only where needed, maintaining operational stability in IT systems while enforcing security measures.

---

### Summary

In this activity, I applied SQL filtering techniques to investigate security-related data and target specific employee machines for updates. I utilized AND, OR, and NOT operators, as well as LIKE with wildcards, to refine query results. By combining date, time, and department filters, I was able to identify suspicious login attempts and ensure security updates were applied efficiently. These skills are essential for cybersecurity analysts to support incident response and maintain system integrity.










# Project Module 4: File Permissions in Linux

## Project Description
In this activity, I performed file permission analysis and management using Linux commands as part of a security role supporting a research team. The objective was to review existing permissions, identify unauthorized access, and apply appropriate restrictions to ensure system security. This task demonstrates practical skills in access control and Linux system administration.

---

## Check File and Directory Details

To view file and directory permissions, I used the following command:

`ls -la`

This command lists all files (including hidden files) with detailed information such as permissions, ownership, and file type.

### Example Output (Based on Scenario)
```bash
-rw-rw-rw- 1 researcher2 research 1234 project_k.txt
-rw-r----- 1 researcher2 research 1234 project_m.txt
-rw-rw-r-- 1 researcher2 research 1234 project_r.txt
-rw-rw-r-- 1 researcher2 research 1234 project_t.txt
-rw--w---- 1 researcher2 research 1234 .project_x.txt
drwx--x--- 2 researcher2 research 4096 drafts
```

---

## Describe the Permissions String

Example selected:  
`-rw-rw-r--`

This is a 10-character string that represents file type and permissions.

Breakdown:
- `-` → File type (regular file)
- `rw-` → User (owner) permissions: read and write
- `rw-` → Group permissions: read and write
- `r--` → Others permissions: read only

This string helps determine who can access and modify a file.

---

## Change File Permissions

The organization does not allow **others to have write access**.

### File Identified:
`project_k.txt` (others had write permission)

### Command Used:
`chmod o-w project_k.txt`

### Explanation:
- `chmod` → Change file permissions  
- `o-w` → Remove write permission from others  

### Result:
Permissions changed from:
-rw-rw-rw-
To: 
-rw-rw-r--


---

## Change File Permissions on a Hidden File

The file `.project_x.txt` is hidden and should:
- NOT allow write access
- Allow read access for user and group

### Command Used:
`chmod ug+r,u-w,g-w,o-rwx .project_x.txt`

### Explanation:
- `ug+r` → Add read permission for user and group  
- `u-w,g-w` → Remove write permission from user and group  
- `o-rwx` → Remove all permissions from others  

### Result:
Permissions updated to:
-r--r-----

---

## Change Directory Permissions

The `drafts` directory should only be accessible by the owner (`researcher2`).

### Command Used:
`chmod 700 drafts`

### Explanation:
- `7` → read, write, execute (user)
- `0` → no permissions (group)
- `0` → no permissions (others)

### Result:
Permissions changed to:
drwx------

---

## Summary

In this activity, I used Linux commands to review and modify file and directory permissions to meet security requirements. I applied `ls -la` to inspect permissions and `chmod` to enforce proper access control. This ensured that unauthorized users could not modify files or access restricted directories. These skills are essential in cybersecurity roles to maintain system integrity and protect sensitive data.











# Project Module 5: Analyze a vulnerable system for a small business

## Project Description

This project involves conducting a vulnerability assessment of a small business’s publicly accessible database server. The server stores sensitive customer, campaign, and analytic data that are critical to business operations. The assessment evaluates potential threats, identifies vulnerabilities, and provides actionable recommendations to secure the system and minimize the risk of data breaches, operational disruptions, or unauthorized access.

---

## Objective

The objective of this project is to assess the security posture of the database server, quantify potential risks, and recommend effective remediation strategies. This assessment aims to protect sensitive data, ensure the integrity and availability of business operations, and support decision-making by providing stakeholders with a clear understanding of the system’s vulnerabilities and the measures needed to mitigate them.

---

### Vulnerability Assessment Report
Date: 1st January 20XX

#### System Description

The server hardware consists of a high-performance CPU and 128GB of memory. It runs the latest version of the Linux operating system and hosts a MySQL database management system. The server is connected to a stable network using IPv4 addresses and interacts with other servers on the company’s network. Security measures include SSL/TLS encrypted connections. The server stores customer, campaign, and analytic data, which are essential for business operations.

#### Scope

The scope of this assessment focuses on the access controls and data security of the database server over a three-month period (June 20XX to August 20XX). The assessment uses NIST SP 800-30 Rev. 1 to guide the risk analysis, focusing on the confidentiality, integrity, and availability of the information stored on the server.

#### Purpose

The database server is a critical component for storing and managing large volumes of business data. Its security is essential because it contains sensitive customer information and operational data that drive business decisions. If compromised, the server could disrupt marketing campaigns, impact customer trust, and lead to potential financial losses. Conducting this vulnerability assessment allows stakeholders to understand the risks and implement effective security measures to protect business operations.

#### Risk Assessment
| Threat Source | Threat Event                                  | Likelihood (1-3) | Severity (1-3) | Risk (LxS) |
| ------------- | --------------------------------------------- | ---------------- | -------------- | ---------- |
| Hacker        | Obtain sensitive information via exfiltration | 3                | 3              | 9          |
| Employee      | Disrupt mission-critical operations           | 2                | 3              | 6          |
| Customer      | Alter/Delete critical information             | 1                | 3              | 3          |

#### Notes:
- Hackers could exploit publicly accessible databases to steal sensitive customer and business data.
- Employees with improper access could unintentionally or maliciously disrupt operations.
- Customers might accidentally or deliberately manipulate data if access controls are weak.

#### Approach

The three threats were selected based on the open accessibility of the database server and the potential impact on business operations. Likelihood scores were determined by assessing the ease with which an attacker could exploit each vulnerability, while severity scores were based on the potential operational and reputational damage. This qualitative analysis highlights the most critical risks that require immediate attention and helps prioritize security efforts.

#### Remediation Strategy

To mitigate the identified risks, several security controls are recommended. Implement strong authentication, authorization, and auditing mechanisms to ensure only authorized users can access the database. Apply the principle of least privilege to limit user permissions and reduce the potential impact of insider threats. Multi-factor authentication (MFA) should be enabled for all users, and data in transit should use TLS encryption. Additionally, IP allow-listing can prevent unauthorized external access.

---

## Reflection

This activity emphasized the importance of conducting thorough vulnerability assessments to identify weaknesses in a system before they are exploited. By evaluating both external and internal threats, I learned how to quantify risks using likelihood and severity, prioritize remediation efforts, and recommend practical controls. The exercise reinforced how critical proper access management and monitoring are for protecting sensitive information and maintaining operational continuity.

---

## Conclusion

The vulnerability assessment revealed that the publicly accessible database server is exposed to high-impact threats that could compromise data integrity and business operations. Implementing the recommended security controls will significantly reduce these risks. Regular assessments, combined with strong operational and technical controls, are essential for maintaining the security of critical systems and protecting the organization from potential cyber threats.











# Project Module 6: Documenting a Security Incident

## Project Description:
This project involved documenting a ransomware security incident experienced by a small U.S. health care clinic. The activity required using an incident handler’s journal to capture key details of the scenario, including detection, analysis, and containment efforts. Accurate documentation helps incident responders track events, analyze incidents, and improve security measures.

---

## Objective:
- Develop professional incident documentation skills.  
- Record detailed information about security incidents using the 5 W’s framework (Who, What, When, Where, Why).  
- Demonstrate the ability to reflect on security processes, tools, and preventive measures.  

---

## Incident Handler’s Journal Entries

### Entry #1

| Field | Details |
|-------|---------|
| **Date** | July 23, 2024 |
| **Description** | Documenting a ransomware security incident at a healthcare company. |
| **Tool(s) used** | None |
| **Who** | An organized group of unethical hackers |
| **What** | Ransomware security incident causing system-wide file encryption |
| **When** | Tuesday at 9:00 a.m. |
| **Where** | Small U.S. health care clinic |
| **Why** | Attackers gained access via a phishing email with a malicious attachment. They deployed ransomware to encrypt critical files and demanded a ransom for decryption. |
| **Additional Notes** | - How could the healthcare company prevent this type of incident in the future?<br>- Should the company pay the ransom to retrieve encrypted files? |

---

### Entry #2

| Field | Details |
|-------|---------|
| **Date** | July 25, 2024 |
| **Description** | Analyzing a packet capture file |
| **Tool(s) used** | Wireshark |
| **Who** | N/A |
| **What** | N/A |
| **When** | N/A |
| **Where** | N/A |
| **Why** | N/A |
| **Additional Notes** | Learned how Wireshark captures and analyzes network traffic. Initially overwhelming but highlighted the value of network traffic analysis for detecting malicious activity. |

---

### Entry #3

| Field | Details |
|-------|---------|
| **Date** | July 25, 2024 |
| **Description** | Capturing first packet using tcpdump |
| **Tool(s) used** | tcpdump |
| **Who** | N/A |
| **What** | N/A |
| **When** | N/A |
| **Where** | N/A |
| **Why** | N/A |
| **Additional Notes** | Experienced challenges with command-line syntax, but successfully captured network traffic after careful instruction review. |

---

### Entry #4

| Field | Details |
|-------|---------|
| **Date** | July 27, 2024 |
| **Description** | Investigating a suspicious file hash |
| **Tool(s) used** | VirusTotal |
| **Who** | Unknown malicious actor |
| **What** | Email contained a malicious file attachment (SHA-256: 54e6ea47eb04634d3e87fd7787e2136ccfbcc80ade34f246a12cf93bab527f6b) |
| **When** | Alert at 1:20 p.m. |
| **Where** | Employee's computer at a financial services company |
| **Why** | Employee downloaded and executed the malicious attachment |
| **Additional Notes** | How can future incidents be prevented? Consider improving security awareness training to reduce likelihood of executing malicious attachments. |

---

## Reflections and Notes

1. **Challenging Activities:**  
   Using tcpdump on the command line was challenging due to unfamiliar syntax. Repeating steps and careful instruction reading helped overcome this challenge.  

2. **Understanding Growth:**  
   My understanding of incident detection and response has improved. I now appreciate the complexity of incident lifecycle management, including the importance of tools, processes, and proper documentation.  

3. **Favorite Tools/Concepts:**  
   Network traffic analysis was especially interesting. Using Wireshark and tcpdump to capture and analyze real-time network traffic was both challenging and rewarding, sparking further interest in this area of cybersecurity.

---

## Conclusion

Documenting incidents using an incident handler’s journal is an essential part of professional cybersecurity practice. This activity helped me develop skills in structured incident documentation, critical analysis, and reflection. By capturing key details through the 5 W’s framework and analyzing incidents with tools like Wireshark, tcpdump, and VirusTotal, I gained practical experience that reinforces theoretical knowledge.  

This journal entry demonstrates my ability to:  
- Professionally document and organize incident data.  
- Reflect on lessons learned and challenges encountered.  
- Apply cybersecurity tools and concepts effectively.  

Overall, this activity strengthens my portfolio and showcases my preparedness for roles in cybersecurity incident detection and response.











# Project Module 7: Update A File Through A Python Algorithm
## Project Description
At my organization, access to restricted content is controlled via an allow list of IP addresses stored in the allow_list.txt file. A separate remove list identifies IP addresses that should no longer have access.

I created a Python algorithm to automate updating the allow list file. This algorithm checks whether any IP addresses on the remove list exist in the allow list, removes them if present, and updates the file accordingly. This project demonstrates file handling, string manipulation, list operations, and iteration in Python.

---

## Project Objective

The objective of this project is to create a Python algorithm that automates the management of an allow list of IP addresses. Specifically, it aims to:

- Identify and remove IP addresses from the allow list that are no longer authorized.
- Demonstrate practical file handling and data manipulation skills in Python.
- Provide a reproducible workflow that can be added to a cybersecurity portfolio to showcase coding proficiency in automation tasks.

---

## Example 1: Single Folder Version
### Python Algorithm
```python
# Step 1: Open the file that contains the allow list
import_file = "allow_list.txt"

with open(import_file, "r") as file:
    # Step 2: Read the file contents into a string
    ip_addresses = file.read()

# Step 3: Convert the string into a list of IP addresses
ip_addresses = ip_addresses.split()

# Example remove list
remove_list = ["192.168.1.10", "10.0.0.5"]

# Step 4: Iterate through the remove list
for element in remove_list:
    # Step 5: Remove IP addresses that are on the remove list
    if element in ip_addresses:
        ip_addresses.remove(element)  # Works because there are no duplicates

# Step 6: Update the file with the revised list of IP addresses
ip_addresses = "\n".join(ip_addresses)  # Convert list back to string with newlines

with open(import_file, "w") as file:
    file.write(ip_addresses)
```

---

## Example 2: Multiple Folder Version 
### Folder Structure
``` bash
Update-File-Python-Algorithm/
│
├── allow_list.txt             # Sample allow list file
├── remove_list.txt            # Sample remove list file
├── update_allow_list.py       # Python algorithm script
└── README.md                  # Project explanation and portfolio entry
```

### allow_list.txt
Sample IP addresses (one per line):
``` bash
192.168.1.1
192.168.1.10
10.0.0.5
172.16.0.1
```

### remove_list.txt
Sample IP addresses to remove:
``` bash
192.168.1.10
10.0.0.5
```

update_allow_list.py
``` python
# update_allow_list.py
"""
Python algorithm to update an allow list of IP addresses
by removing IPs that appear in a remove list.
"""

# File paths
allow_file = "allow_list.txt"
remove_file = "remove_list.txt"

# Read allow list
with open(allow_file, "r") as file:
    ip_addresses = file.read().split()  # Convert to list

# Read remove list
with open(remove_file, "r") as file:
    remove_list = file.read().split()

# Remove IPs from allow list
for element in remove_list:
    if element in ip_addresses:
        ip_addresses.remove(element)

# Update allow list file
with open(allow_file, "w") as file:
    file.write("\n".join(ip_addresses))

print("Allow list updated successfully!")
```

---

## Explanation of Python Syntax and Functions
- **with open(import_file, "r") as file:**  
  Opens a file for reading ("r" mode) and automatically closes it after the block. `file` represents the file object.
- **.read():**  
  Converts the file contents into a string so it can be processed in Python.
- **.split():**  
  Converts a string into a list of elements. In this case, it splits IP addresses into a list.
- **for element in remove_list:**  
  Iterates over each item in the `remove_list` to process them one by one.
- **if element in ip_addresses:**  
  Checks whether the IP address exists in the allow list before attempting to remove it.
- **.remove(element):**  
  Removes the element from the list. Works correctly here because there are no duplicate IP addresses.
- **"\n".join(ip_addresses):**  
  Converts the list back into a string, adding a newline character between each IP address.
- **with open(import_file, "w") as file:**  
  Opens the file for writing ("w" mode) and overwrites the contents with the updated IP addresses.

---

## How to Run
1. Make sure `allow_list.txt` and `remove_list.txt` are in the same folder as `update_allow_list.py`.
2. Open a terminal and navigate to the folder.
3. Run the script:
```bash
python update_allow_list.py
```
4. Check allow_list.txt to see the updated IP addresses.


---

## Reflection

Working on this project helped me better understand practical applications of Python for file handling and automation in cybersecurity. I learned how to safely read and write files, manipulate strings and lists, and automate repetitive tasks that would otherwise be time-consuming.

It also highlighted the importance of considering potential issues such as duplicates or missing entries, and ensuring scripts handle them gracefully. Overall, this project strengthened my confidence in applying Python to real-world cybersecurity problems.

---

## Summary
This algorithm demonstrates how to manage file-based allow lists using Python. It involves:
- Opening and reading a file using a with statement and .read() method.
- Converting a string of IP addresses into a list with .split().
- Iterating through a remove list using a for loop.
- Removing elements from a list with .remove().
- Converting the list back to a string with .join() and writing it back to the file with .write().
By automating this process, the algorithm ensures that only authorized IP addresses have access to restricted content, improving both efficiency and security.

---

## Conclusion

By automating the process of updating the allow list, this project ensures that only authorized IP addresses have access to restricted content. It improves both efficiency and security, demonstrates key Python programming concepts, and can serve as a professional portfolio piece to showcase my practical coding skills in cybersecurity.











