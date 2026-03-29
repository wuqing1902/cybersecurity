# Lab Module 2: Internal IT Audit Documentation – Botium Toys

This lab documents an internal IT audit conducted on Botium Toys. The purpose is to evaluate the organization’s security posture, identify risks, assess controls, check compliance, and provide recommendations to improve overall security.

---

## 1. Audit Scope and Goals

**Scope:**  
- Entire security program at Botium Toys.  
- Assessment of all assets, systems, internal processes, and controls.  
- Review of compliance with regulatory standards and best practices.

**Goals:**  
- Assess existing assets and internal controls.  
- Identify gaps in security controls and compliance adherence.  
- Recommend improvements to mitigate high-risk vulnerabilities.  
- Align with the **NIST Cybersecurity Framework (CSF)** and industry best practices.  

---

## 2. Risk Assessment

### Current Assets
- Employee equipment: desktops, laptops, smartphones, peripherals, remote workstations, docking stations, headsets.  
- Internal network: storage of customer, vendor, and organizational data.  
- Storefront products: on-site and online inventory.  
- Systems/software: accounting, database, telecommunication, ecommerce, inventory management.  
- Internet access, legacy system maintenance, and data retention/storage.

### Risk Description
- Inadequate asset management.  
- Lack of proper controls (technical, administrative, and physical).  
- Employees have access to sensitive customer data including PII/SPII and cardholder information.  
- Encryption is not applied for sensitive data.  
- No disaster recovery plans or intrusion detection system (IDS).  

### Control Best Practices
- Dedicate resources to identify and classify assets.  
- Implement controls to reduce likelihood of breaches.  
- Evaluate business impact if assets or systems are lost.  
- Maintain compliance with GDPR, PCI DSS, and SOC standards.

### Risk Score
- **8/10 (High risk)** due to lack of controls and insufficient adherence to compliance standards.  
- **Comments:** High risk of data loss or regulatory penalties if corrective actions are not implemented.  

---

## 3. Control Categories

| Category | Examples | Purpose |
|----------|---------|--------|
| **Administrative/Managerial** | Password policies, least privilege, account management, separation of duties | Define responsibilities and policies to manage data and protect assets |
| **Technical** | Firewalls, IDS/IPS, antivirus, encryption, backups, password management | Prevent, detect, or correct security incidents |
| **Physical** | Locks, CCTV, alarm systems, safes, lighting | Limit unauthorized physical access to assets |

**Control Types:**  
- **Preventative:** Prevent incidents (e.g., firewall, password policy).  
- **Detective:** Identify incidents (e.g., IDS, CCTV).  
- **Corrective:** Restore assets after incidents (e.g., backups, disaster recovery).  
- **Deterrent:** Discourage attacks (e.g., signage, locks, safes).  

---

## 4. Controls Assessment Checklist

| Yes | No | Control | Explanation |
|-----|----|---------|-------------|
|     | X  | Least Privilege | All employees have access to customer/internal data; privileges need limiting. |
|     | X  | Disaster recovery plans | No plans in place; needed for business continuity. |
|     | X  | Password policies | Minimal requirements; higher complexity needed. |
|     | X  | Separation of duties | CEO currently manages multiple critical operations; risk of insider threats/fraud. |
| X   |    | Firewall | Blocks traffic according to defined rules. |
|     | X  | IDS | Not implemented; needed for intrusion detection. |
|     | X  | Backups | Critical data not backed up; needed for recovery. |
| X   |    | Antivirus software | Installed and monitored regularly. |
|     | X  | Manual monitoring & legacy system maintenance | Monitoring exists but not scheduled; intervention unclear. |
|     | X  | Encryption | Not implemented; needed to secure sensitive info. |
|     | X  | Password management system | Not implemented; would improve productivity. |
| X   |    | Locks (offices/storefront/warehouse) | Physical locations secured. |
| X   |    | CCTV surveillance | Installed and functioning. |
| X   |    | Fire detection/prevention | Functional fire alarm and sprinkler systems. |

---

## 5. Compliance Checklist

| Standard | Yes | No | Best Practice | Explanation |
|----------|-----|----|---------------|-------------|
| PCI DSS |     | X  | Only authorized users access credit card info | All employees currently have access to internal data. |
| PCI DSS |     | X  | Data accepted, processed, transmitted, and stored securely | Encryption missing; all employees can access sensitive info. |
| PCI DSS |     | X  | Implement encryption for transactions | Not implemented; needed for confidentiality. |
| PCI DSS |     | X  | Adopt secure password management policies | Password policies minimal; no management system. |
| GDPR | X   |    | Notify E.U. customers within 72 hours of breach | Plan exists and enforced. |
| GDPR |     | X  | Keep E.U. customer data private/secured | Encryption missing; data confidentiality at risk. |
| GDPR |     | X  | Properly classify and inventory data | Assets listed but not classified. |
| GDPR | X   |    | Enforce privacy policies and procedures | Policies enforced among IT staff and employees. |
| SOC 1 & SOC 2 |     | X  | User access policies | Least Privilege and Separation of Duties missing. |
| SOC 1 & SOC 2 |     | X  | Sensitive data confidential/private | Encryption missing. |
| SOC 1 & SOC 2 | X   |    | Data integrity ensured | Measures are in place. |
| SOC 1 & SOC 2 |     | X  | Data available to authorized users | Needs restriction to authorized personnel only. |

---

## 6. Recommendations

- Implement **critical administrative controls**: Least Privilege, Separation of Duties, Disaster Recovery Plans, Password Policies.  
- Deploy **technical controls**: IDS, Encryption, Password Management System, Regular Legacy System Monitoring.  
- Maintain and strengthen **physical controls**: Locks, CCTV, Fire Detection/Prevention.  
- Improve **compliance**: GDPR, PCI DSS, and SOC adherence; classify assets and enforce encryption and access restrictions.  
- Overall, addressing these gaps will **reduce risks**, protect sensitive information, and improve Botium Toys’ security posture.

---

## 7. Reflection

Conducting this audit reinforced the importance of a **holistic cybersecurity approach**, combining administrative, technical, and physical controls. I learned to:  

- Identify and classify assets, evaluate risks, and assign risk scores.  
- Assess existing controls and determine gaps in practice.  
- Apply compliance frameworks (GDPR, PCI DSS, SOC) in a practical scenario.  
- Provide actionable recommendations to improve security posture and business continuity.  

This lab demonstrates **practical application of cybersecurity principles**, problem-solving, and analytical thinking—skills that are directly relevant for professional roles in IT security.
