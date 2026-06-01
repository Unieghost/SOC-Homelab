# SOC Homelab

Personal Security Operations Center (SOC) laboratory focused on:

- Wazuh
- Sysmon
- Active Directory
- Detection Engineering
- Threat Hunting
- Incident Response
- MITRE ATT&CK

## Lab Environment

### Infrastructure

- Wazuh Manager
- Windows Server Domain Controller
- Windows LTSC Workstation
- Sysmon
- Active Directory
- Discord Alerting Integration

### Objectives

- Build practical SOC skills
- Develop detection engineering capabilities
- Simulate adversary techniques
- Create custom detection rules
- Document investigations and findings

---

# Incident Reports

## Incident 001 – PsExec Lateral Movement Simulation

A simulated lateral movement attack using PsExec was executed in a controlled environment.

The activity was detected through Sysmon telemetry, correlated by Wazuh, mapped to MITRE ATT&CK techniques and forwarded through Discord integration.

📄 Report:

[Incident-001-PsExec](Incident-001-PsExec/Incident-001-PsExec.md)

---

## Skills Demonstrated

- Windows Event Analysis
- Sysmon Monitoring
- Wazuh SIEM
- Detection Engineering
- MITRE ATT&CK Mapping
- Incident Documentation
- Active Directory Monitoring
- Alert Triage

---

## Future Incident Reports

- Incident 003 – Privilege Escalation
- Incident 004 – PowerShell Abuse
- Incident 005 – Active Directory Enumeration
