# Lab Module 5: Introduction to Asset Security

This lab focuses on understanding asset management and risk assessment in a cybersecurity context. The lab consists of two activities:  

1. **Classifying assets connected to a home network**  
2. **Scoring risks based on their likelihood and severity**  

---

## Activity 1: Classify the Assets Connected to a Home Network

**Objective:**  
Create an inventory of devices connected to a home network, identify their characteristics, and classify them based on sensitivity to risk.

**Overview:**  
Asset management is critical in cybersecurity. It involves tracking assets, evaluating associated risks, and classifying them according to their importance and sensitivity. In this activity, I identified additional network-connected devices, evaluated their characteristics, and assigned sensitivity levels.

**Asset Inventory Table:**  

| Asset                  | Network Access | Owner       | Location         | Notes                                                    | Sensitivity      |
|------------------------|----------------|------------|----------------|----------------------------------------------------------|----------------|
| Network router         | Continuous     | ISP        | On-premises     | 2.4 GHz and 5 GHz connections; all devices connect to 5 GHz | Confidential   |
| Desktop                | Occasional     | Homeowner  | On-premises     | Contains private information, like photos               | Restricted      |
| Guest smartphone       | Occasional     | Friend     | On/Off-premises | Connects to home network                                 | Internal-only   |
| External hard drive    | Occasional     | Homeowner  | On-premises     | Contains music and movies                                | Confidential    |
| Streaming media player | Continuous     | Homeowner  | On-premises     | Payment card information stored for rentals             | Internal-only   |
| Portable game console  | Occasional     | Friend     | On/Off-premises | Has camera and microphone                                 | Internal-only   |

**Reflection:**  
This activity highlighted the importance of maintaining an accurate inventory of all network-connected devices. Evaluating network access, ownership, location, and stored information helped me classify assets and prioritize their protection. Sensitive devices were labeled with higher sensitivity to enforce a “need-to-know” access approach. Future improvements could include tracking non-networked assets and considering additional security measures for shared devices.

---

## Activity 2: Score Risks Based on Likelihood and Severity

**Objective:**  
Perform a risk assessment for a bank’s operational environment, evaluate the likelihood and severity of potential security risks, and prioritize cybersecurity resources.

**Overview:**  
Risk assessments are essential to identify vulnerabilities threatening business operations. This activity involved evaluating a set of risks using a risk register and applying a risk matrix to calculate scores based on likelihood and severity.  

**Risk Formula:**  
Risk Score = Likelihood × Severity


**Risk Register Table:**  

| Asset | Risk(s)                      | Description                                         | Likelihood | Severity | Priority |
|-------|-------------------------------|---------------------------------------------------|------------|----------|----------|
| Funds | Business email compromise      | An employee is tricked into sharing confidential information | 2          | 2        | 4        |
| Funds | Compromised user database      | Customer data is poorly encrypted                 | 2          | 3        | 6        |
| Funds | Financial records leak         | A database server of backed-up data is publicly accessible | 3          | 3        | 9        |
| Funds | Theft                          | The bank's safe is left unlocked                  | 1          | 3        | 3        |
| Funds | Supply chain disruption        | Delivery delays due to natural disasters         | 1          | 2        | 2        |

**Likelihood and Severity Explanation Table:**  

| Risk                           | Likelihood (Chance of Occurring)                                     | Severity (Impact if Occurs)                                         |
|--------------------------------|----------------------------------------------------------------------|----------------------------------------------------------------------|
| Business email compromise       | 2 – Likely: Employees occasionally fall for phishing attempts       | 2 – Moderate: Could cause data loss or minor financial impact       |
| Compromised user database       | 2 – Likely: Customer data may be targeted or poorly secured          | 3 – High: Could result in regulatory fines and reputational damage  |
| Financial records leak          | 3 – High: Database is publicly accessible, so risk is frequent      | 3 – High: Severe financial, operational, and reputational impact   |
| Theft                           | 1 – Rare: Bank in low-crime coastal area                              | 3 – High: Loss of funds could critically impact operations          |
| Supply chain disruption         | 1 – Rare: Natural disasters unpredictable, but possible              | 2 – Moderate: Could delay operations and cash availability          |

**Notes:**  
The bank interacts with multiple external entities, increasing the risk of data compromise. While theft is possible, the low crime rate reduces its priority. Risks like financial records leaks require immediate attention due to regulatory, financial, and reputational impacts.

**Reflection:**  
This activity demonstrated the process of evaluating security risks systematically. By assigning likelihood and severity scores, I calculated overall risk priorities to guide cybersecurity decision-making. The highest priority risk was a financial records leak, aligning with the critical nature of the bank's data. This reinforces proactive security planning and the importance of regular risk assessments. Future improvements could include integrating historical incident data to refine likelihood estimates.

---

## Conclusion

The **Introduction to Asset Security** lab emphasized foundational skills in asset management and risk assessment. By classifying network-connected devices and performing structured risk evaluations, I learned to identify critical assets, assess vulnerabilities, and prioritize protective measures. Completing these activities strengthened my ability to create detailed asset inventories and perform informed, data-driven risk assessments, which are essential skills in both home and organizational cybersecurity environments.
