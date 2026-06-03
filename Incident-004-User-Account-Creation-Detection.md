# Incident Report 004

## Incident Name

User Account Creation Detection

## Date

03/06/2026

## Analyst

Fernando Andrade

## Severity

Medium

## Status

Closed

## Executive Summary

A simulation of a new Active Directory user account creation event was carried out in a SOC laboratory environment in order to assess detection, monitoring, and investigation capabilities.

The activity generated Windows Security Event ID 4720, which was collected by Wazuh and correlated through Rule 60109. The event was mapped to the MITRE ATT&CK framework as T1098 - Account Manipulation.

The purpose of this exercise was to validate the SOC lab's capability to detect account creation activity that could indicate persistence, privilege abuse, or unauthorized access within an Active Directory environment.

## Environment

### Infrastructure

* Wazuh Manager
* Active Directory
* Domain Controller
* Windows Security Logs
* Windows Event Viewer

### Hosts

* DC01.corp.local

## Attack Simulation

The following command was executed on the Domain Controller to create a new domain user account:

```cmd
net user soc_test01 Password123! /add /domain
```

The command was executed using administrative privileges.

The objective of the exercise was to simulate user account creation activity and verify whether security monitoring systems could successfully detect, collect, and correlate the generated telemetry.

## Evidence Collection

### Evidence 1 – User Account Creation Command

A new domain user account was created using the Windows command line.

**Image:**

![User Account Creation](screenshots/01-command-user-created.png)

### Evidence 2 – Windows Security Event ID 4720

Windows Security Logs recorded Event ID 4720, indicating that a new user account had been created.

**Image:**

![Event ID 4720](screenshots/02-event-viewer-4720.png)

### Evidence 3 – Wazuh Detection

Wazuh successfully collected the event and triggered Rule 60109, identifying account creation activity.

**Image:**

![Wazuh Detection](screenshots/03-wazuh-alert-4720.png)

### Evidence 4 – Alert Details

Alert metadata confirmed the created account, source host, responsible user, and event attributes.

**Image:**

![Alert Details](screenshots/04-alert-details.png)

### Evidence 5 – MITRE ATT&CK Mapping

The event was mapped to the MITRE ATT&CK framework as Account Manipulation under the Persistence tactic.

**Image:**

![MITRE Mapping](screenshots/05-mitre-mapping.png)

## Analysis

The activity generated Windows Security Event ID 4720, which is logged whenever a new user account is created within the environment.

User account creation events are highly relevant from a security monitoring perspective because attackers frequently create accounts to establish persistence, maintain access, or facilitate later stages of an intrusion.

Although the account creation performed during this exercise was legitimate and executed in a controlled laboratory environment, the generated telemetry closely resembles activity that would require investigation in a production network.

The event was successfully recorded by Windows Security Logs, collected by the Wazuh agent, and correlated through Rule 60109.

Important indicators observed during the investigation included:

* Event ID 4720
* New user account creation
* Administrative account activity
* Rule 60109
* MITRE ATT&CK T1098
* Persistence tactic

## Attack Timeline

**10:43:33 UTC** - User account creation command executed.

**10:43:33 UTC** - Windows Security Event ID 4720 generated.

**10:43:37 UTC** - Wazuh collected the event.

**10:43:37 UTC** - Rule 60109 triggered.

**10:43:37 UTC** - MITRE ATT&CK mapping applied.

**10:43:37 UTC** - Event indexed and displayed within the Wazuh Dashboard.

## MITRE ATT&CK Mapping

### T1098 – Account Manipulation

The activity involved creation of a new account within an Active Directory environment.

### Persistence

Attackers may create accounts to maintain long-term access to compromised systems and networks.

## Detection Workflow

The detection workflow occurred as follows:

1. A new domain user account was created.
2. Windows generated Security Event ID 4720.
3. The Wazuh agent collected the generated telemetry.
4. Wazuh correlated the event with Rule 60109.
5. MITRE ATT&CK technique T1098 was identified.
6. The event was indexed and displayed in the dashboard.
7. The activity was reviewed and validated by the analyst.

## Response Actions

The following investigation activities were performed:

* Verified user account creation activity.
* Reviewed Windows Security Event ID 4720.
* Confirmed Active Directory account creation.
* Validated Wazuh detection.
* Verified MITRE ATT&CK mapping.
* Reviewed alert metadata and event details.
* Confirmed the activity as part of a controlled SOC laboratory exercise.

## Conclusion

The SOC laboratory successfully detected and correlated a user account creation event within an Active Directory environment.

The exercise demonstrated:

* Active Directory monitoring
* Windows Security Log analysis
* Event ID 4720 investigation
* SIEM-based detection using Wazuh
* MITRE ATT&CK mapping
* Security event correlation
* Incident documentation procedures

In conclusion, the SOC lab successfully demonstrated its capability to detect, investigate, and document user account creation activity within a Windows domain environment.
