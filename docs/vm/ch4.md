# Chapter 4: Vulnerability Assessment and Prioritization

---

## Overview

After identifying vulnerabilities, the next crucial step is to **assess** their risk and **prioritize** remediation efforts. Prioritization ensures that limited resources focus first on vulnerabilities that pose the greatest threat to the organization’s most important assets.

This chapter covers key concepts, methodologies, and tools to evaluate vulnerabilities based on severity, exploitability, business impact, and threat intelligence.

---

## 1. Vulnerability Assessment

Vulnerability assessment involves determining the **severity and potential impact** of each identified vulnerability. It helps answer questions such as:

- How critical is the vulnerability?
- How easily can it be exploited?
- What assets are affected?

### Common Assessment Criteria

- **Severity Score (CVSS):**  
  The Common Vulnerability Scoring System scores vulnerabilities on a scale from 0 to 10 based on factors like attack vector, complexity, privileges required, and impact on confidentiality, integrity, and availability.

- **Exploitability:**  
  Evaluates how feasible it is for attackers to exploit the vulnerability. Factors include availability of exploit code (proof of concept), attack complexity, and attacker skill level needed.

- **Age of Vulnerability:**  
  Older vulnerabilities with known exploits may require urgent attention.

- **Asset Criticality:**  
  How important the affected asset is to business operations (e.g., public-facing servers vs. internal test machines).

### Tools Supporting Assessment

- Vulnerability scanners can automatically assign CVSS scores.
- Threat intelligence platforms provide exploit details and real-world attack data.
- Vulnerability management solutions combine these data points for richer assessment.

---

## 2. Vulnerability Prioritization

Prioritization ranks vulnerabilities to guide remediation efforts effectively. Organizations use various strategies and factors:

### 2.1 Risk-Based Prioritization

- Combines CVSS scores with **business context** such as asset value and exposure.
- Factors include:
  - Whether the asset is internet-facing.
  - The asset’s role in critical business functions.
  - Compliance and regulatory requirements.

### 2.2 Context and Threat Awareness

- Understand how an asset operates within environments and the likelihood of real-world exploitation.
- Real-time threat intelligence helps identify vulnerabilities actively exploited in the wild.
- Example: CISA’s Known Exploited Vulnerabilities (KEV) catalog lists vulnerabilities that require immediate attention based on actual attacks.

### 2.3 Combining Multiple Frameworks

- Some organizations merge CVSS, Exploit Prediction Scoring System (EPSS), and cloud-provider specific risk frameworks to get a comprehensive view.
- This layered approach reduces false positives and better reflects operational risk.

### 2.4 Incorporating DevSecOps and Automation

- Integrating vulnerability checks and prioritization into CI/CD pipelines allows early identification and remediation before deployment.
- Automated tools can continuously update prioritization based on new intelligence.

---

## 3. Steps to Effective Vulnerability Prioritization

1. **Gather all vulnerability data** from scanners and threat feeds.
2. **Assign severity scores** (e.g., CVSS).
3. **Enrich data with context** — asset criticality, network exposure, compliance impact.
4. **Incorporate threat intelligence** — check for active exploit reports or proof-of-concept codes.
5. **Rank vulnerabilities** based on risk score combining all factors.
6. **Plan remediation** focusing first on highest-risk vulnerabilities.
7. **Document decisions and review regularly** to adapt to changing threat landscape.

---

## 4. Best Practices in Assessment and Prioritization

- Maintain **visibility of all assets and attack vectors** to avoid gaps.
- Use a **risk-based approach** rather than relying solely on severity scores.
- Leverage **threat intelligence feeds** and curated lists like CISA KEV.
- Consider the **business impact** of exploited vulnerabilities on operations.
- Regularly **reevaluate priorities** with updated intelligence and environment changes.
- Align prioritization with organizational **risk appetite** and compliance mandates.

---

## 5. Example: Prioritizing Vulnerabilities Using CVSS and Asset Context

| Vulnerability                   | CVSS Score | Asset Type          | Exposure          | Threat Intelligence | Priority   |
|--------------------------------|------------|---------------------|-------------------|---------------------|------------|
| Remote Code Execution on Web Server | 9.8        | Internet-facing Web Server | Public Internet    | Exploited in Wild    | Critical   |
| Outdated Software on Test Machine   | 7.2        | Internal Test Server          | Internal Network   | No Current Exploit   | Medium     |
| Missing Patch on Database Server   | 8.5        | Critical DB Server           | Internal Network   | Proof of Concept     | High       |

---

## References and Tools Mentioned

- Common Vulnerability Scoring System (CVSS)  
- CISA Known Exploited Vulnerabilities (KEV) Catalog  
- Exploit Prediction Scoring System (EPSS)  
- Threat intelligence platforms (e.g., Vulners, Rapid7 InsightVM)  
- Open-source and commercial vulnerability management solutions

---

Prioritization is the key to making vulnerability management practical and effective. By focusing on the highest-risk vulnerabilities first, organizations can better protect critical assets and reduce the chance of compromise.

---