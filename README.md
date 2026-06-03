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

### Incident 003 - Detection of PowerShell Encoded Command Execution

Description:

Simulation of a PowerShell command executed through the EncodedCommand parameter using a Base64-encoded payload.

Skills demonstrated:

- PowerShell monitoring
- Sysmon Event ID 1 analysis
- Wazuh alert investigation
- MITRE ATT&CK mapping
- Dashboard correlation
- Discord alert validation

Techniques:

- T1059.001 PowerShell

Report:

[Incident-003-PowerShell-Encoded](Incident-003-PowerShell-Encoded/Incident-003-PowerShell-Encoded.md)

--------------------------------------------------

### Incident 004 – User Account Creation Detection

Description:

Simulation of a new domain user account being created and detected through Windows Security Event logs.

Skills demonstrated:

- Windows Security Monitoring
- User Account Auditing
- Event ID 4720 Investigation
- Wazuh Alert Analysis
- MITRE ATT&CK Mapping

Techniques:

- T1098 Account Manipulation


[Incident-004-User-Account-Creation-Detection](Incident-004-User-Account-Creation-Detection/Incident-004-User-Account-Creation-Detection.md)

--------------------------------------------------

### Incident 005 – Privileged Group Membership Change

Description:

Simulation of a user being added to the Domain Admins group within an Active Directory environment.

Skills demonstrated:

- Active Directory Security Monitoring
- Privileged Group Auditing
- Windows Security Log Analysis
- Event ID 4728 Investigation
- Wazuh Alert Correlation
- MITRE ATT&CK Mapping
- Discord Alert Validation

Techniques:

- T1484 Domain Policy Modification

[Incident-005-Privileged-Group-Membership-Change](Incident-005-Privileged-Group-Membership-Change/Incident-005-Privileged-Group-Membership-Change.md)

--------------------------------------------------


## Future Incident Reports

- Incident 006 - Scheduled Task Persistence (T1053)
- Incident 007 - Registry Modification (T1112)
- Incident 008 - Service Creation Detection (T1543)
- Incident 009 - RDP Logon Monitoring (4624 Type 10)
- Incident 010 - PowerShell Download Cradle
