# Wazuh SIEM Home Lab

## Objective
Build a SIEM environment using Wazuh to detect and analyze simulated attack activity.

## Lab Architecture
- Wazuh Server (Linux)
- Windows Target Machine
- Kali Linux Attacker
- Sysmon for enhanced logging

## Attack Scenario Tested
- Brute force login attempts

## Detection & Analysis
- Alert review in Wazuh dashboard
- Log correlation
- MITRE ATT&CK mapping
- Investigation documentation
  
- ## Example Alert: Failed Login (Event ID 4625)

### Alert Summary
This screenshot shows the Wazuh dashboard detecting multiple failed login attempts:

![Alert Summary](Alert%20Summary.png)

### Rule Description
The rule that triggered this alert, with its ID and description:

![Rule Description](Rule%20Description.png)

### Raw Log (JSON)
The raw JSON event captured by Wazuh:

![Raw Log JSON Part 1](JSON1.png)
![Raw Log JSON Part 2](JSON2.png)
![Raw Log JSON Part 3](JSON3.png)
![Raw Log JSON Part 4](JSON4.png)
![Raw Log JSON Part 5](JSON5.png)

**Key Fields Observed:**
- `win.system.eventID`: 4625
- `win.eventdata.TargetUserName`: testuser
- `win.eventdata.IpAddress`: 127.0.0.1
- `agent.name`: LAPTOP-RQLL4265
- `rule.id`: 100001

### MITRE ATT&CK Mapping
**T1110 – Brute Force**

### Analyst Conclusion
Multiple failed login attempts were observed within a short time window.  
No successful authentication detected.  
Behavior consistent with brute-force simulation.

## Skills Demonstrated
- SIEM configuration
- Log analysis
- Threat detection
- Incident response workflow
