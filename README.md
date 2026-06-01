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


### Incident 001 – PsExec Lateral Movement Detection

Description:

Simulation of lateral movement using PsExec between Windows hosts.

Skills demonstrated:

- Sysmon telemetry analysis
- Wazuh custom rule creation
- MITRE ATT&CK mapping
- Discord alert integration
- Incident investigation

Techniques:

- T1059.003 Windows Command Shell

Report:

[Incident-001-PsExec](Incident-001-PsExec/Incident-001-PsExec.md)

--------------------------------------------------

### Incident 002 – Brute Force Attack Detection

Description:

Simulation of repeated failed authentication attempts against a privileged account.

Skills demonstrated:

- Windows Security Log analysis
- Event ID 4625 investigation
- Wazuh correlation rules
- MITRE ATT&CK mapping
- Alert validation

Techniques:

- T1110 Brute Force

Report:

[Incident-002-BruteForce](Incident-002-BruteForce/Incident-002-BruteForce.md)

--------------------------------------------------

## Future Incident Reports

- Incident 003 – Privilege Escalation
- Incident 004 – PowerShell Abuse
- Incident 005 – Active Directory Enumeration
