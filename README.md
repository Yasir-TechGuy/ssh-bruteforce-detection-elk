##SSH Brute Force Detection & Incident Response Using ELK Stack

##Project Overview

This project demonstrates the complete lifecycle of detecting and investigating an SSH brute-force attack using ELK Stack.

The attack was simulated using Hydra against a controlled lab environment. Logs were collected, analyzed, and visualized in Kibana to support incident detection and response activities.

##Objectives
Simulate SSH brute-force attack
Detect attack activity using SIEM
Analyze attack indicators
Create security dashboards
Map findings to MITRE ATT&CK
Conduct AI Risk Assessment

##Tools Used
Kali Linux
Hydra
Elasticsearch
Kibana
Docker

##MITRE ATT&CK
MITRE ATT&CK Mapping
Technique	ID
Brute Force	T1110

#Attack Summary
The SSH service was targeted using Hydra.

Successful credentials discovered:

Username: msfadmin
Password: msfadmin
Screenshots

<img width="1694" height="342" alt="Bruteforce_attack" src="https://github.com/user-attachments/assets/71b70ed4-5d0c-45ac-8470-b34e57501a36" />


##Recommendations
Strong password policy
MFA implementation
SSH key authentication
Fail2Ban
SIEM alerting

##Lessons Learned

This project reinforced practical skills in:

Security monitoring
Incident response
Threat detection
Log analysis
SIEM operations
