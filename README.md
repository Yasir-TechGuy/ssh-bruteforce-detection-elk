# SSH Brute Force Detection & Incident Response Using ELK Stack

## Project Overview

This project demonstrates the complete lifecycle of detecting, analyzing, and investigating an SSH brute-force attack using the ELK Stack (Elasticsearch, Logstash, and Kibana).

A controlled attack was simulated using Hydra against an SSH service in a lab environment. The generated logs were collected, indexed, and visualized in Kibana to identify attack patterns, validate detection capabilities, and support incident response activities.

The project also includes MITRE ATT&CK mapping and an AI Risk Assessment focused on adversarial machine learning tools and their potential impact on cybersecurity operations.

---

## Objectives

- Simulate an SSH brute-force attack in a controlled environment
- Collect and analyze attack logs
- Visualize security events using Kibana
- Investigate attack indicators and authentication attempts
- Map observed behavior to the MITRE ATT&CK framework
- Conduct an AI Risk Assessment on adversarial machine learning tools
- Document findings and remediation recommendations

---

## Lab Environment

| Component | Technology |
|------------|------------|
| Attacker Machine | Kali Linux |
| Target Service | SSH |
| Attack Tool | Hydra |
| SIEM Platform | ELK Stack |
| Data Visualization | Kibana |
| Search Engine | Elasticsearch |
| Containerization | Docker |
| Framework | MITRE ATT&CK |

---

## Architecture

```text
Hydra (Attacker)
        |
        v
SSH Service (Target)
        |
        v
Log Collection
        |
        v
Elasticsearch
        |
        v
Kibana
        |
        v
Detection & Investigation
```

---

## MITRE ATT&CK Mapping

| Technique | ID |
|------------|------------|
| Brute Force | T1110 |
| Credential Access | TA0006 |

### Description

The attack simulated repeated authentication attempts against an SSH service using Hydra. This behavior aligns with MITRE ATT&CK Technique T1110 (Brute Force), which adversaries use to gain unauthorized access through password guessing.

---

## Attack Summary

### Attack Tool

Hydra

### Target Service

SSH (Port 22)

### Attack Type

Credential Brute Force Attack

### Objective

Obtain valid SSH credentials through repeated password attempts.

### Result

A valid credential pair was successfully discovered during the simulation:

- Username: msfadmin
- Password: redacted

### Sample Hydra Command

```bash
hydra -l msfadmin -P small-wordlist.txt 192.168.223.128 ssh -t 4 -f -V
```

---

## Detection and Analysis

The generated SSH authentication events were collected and indexed into Elasticsearch.

Using Kibana Discover and Data Views, attack activity was analyzed to identify:

- Source IP address
- Target IP address
- Authentication attempts
- Successful login events
- Credentials discovered
- Attack timestamps

The collected logs enabled visibility into attacker behavior and supported incident response analysis.

## Findings

### Key Observations

- Multiple authentication attempts were detected from a single source.
- Hydra generated repeated login attempts against the SSH service.
- Successful authentication was achieved using weak credentials.
- Kibana provided visibility into attack activity and login success events.
- Event correlation enabled rapid identification of suspicious behavior.

### Indicators of Compromise (IOCs)

| Indicator | Value |
|------------|------------|
| Source IP | 192.168.223.128 |
| Target Port | 22 |
| Attack Tool | Hydra |
| Username | msfadmin |
| Attack Type | SSH Brute Force |

---

## AI Risk Assessment

### Tool Assessed

Adversarial Machine Learning Tool

### Risk Description

Adversarial machine learning techniques can manipulate AI-based security systems by crafting malicious inputs designed to evade detection or produce incorrect classifications.

### Potential Risks

- Evasion of AI-powered detection systems
- False negatives during threat detection
- Model poisoning attacks
- Data integrity compromise
- Reduced confidence in automated security decisions

### Risk Rating

**Medium**

### Recommended Mitigations

- Human validation of AI-generated security alerts
- Adversarial testing of AI models
- Regular model retraining
- Data quality monitoring
- Defense-in-depth security controls

---

## Recommendations

Based on the findings, the following security improvements are recommended:

1. Enforce strong password policies.
2. Implement Multi-Factor Authentication (MFA).
3. Disable password-based SSH authentication where possible.
4. Use SSH key-based authentication.
5. Deploy account lockout policies.
6. Implement Fail2Ban or similar protection mechanisms.
7. Enable centralized logging and SIEM monitoring.
8. Configure real-time alerting for authentication anomalies.
9. Conduct periodic password audits.
10. Perform continuous threat monitoring.

---

## Incident Response Actions

- Identified brute-force attack activity.
- Investigated authentication events.
- Verified successful credential compromise.
- Mapped attack behavior to MITRE ATT&CK.
- Documented findings and remediation recommendations.
- Assessed potential AI-related risks.

---

## Lessons Learned

This project strengthened practical skills in:

- Security Information and Event Management (SIEM)
- Threat Detection and Monitoring
- Incident Response
- Log Analysis
- Elasticsearch
- Kibana Visualization
- Docker Deployment
- MITRE ATT&CK Mapping
- AI Risk Assessment
- Cybersecurity Reporting

---

## Skills Demonstrated

- Blue Team Operations
- Security Monitoring
- Threat Hunting
- Log Analysis
- Incident Investigation
- SIEM Engineering
- Docker
- ELK Stack
- MITRE ATT&CK
- Risk Assessment

---

## Disclaimer

This project was conducted in a controlled laboratory environment for educational and defensive cybersecurity purposes only. No unauthorized systems were targeted.

...
