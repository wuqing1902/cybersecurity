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
