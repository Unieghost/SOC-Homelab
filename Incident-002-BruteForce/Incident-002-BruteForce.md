# Incident Report 002

## Incident Name

Brute Force Attack Detection Simulation

## Date

01/06/2026

## Analyst

Fernando Andrade

## Severity

Medium

## Status

Closed

## Executive Summary

An exercise was done to detect, correlate, and create alerts for brute force attacks. Multiple failed login attempts were carried out against a privileged account in a lab environment to test this capability.

Event ID 4625 was created for the activity performed and logged. Wazuh gathered this information, applied a detection rule and mapped the attack to MITRE ATT&CK technique T1110 (Brute Force). An alert was automatically forwarded to Discord through its integration.

The aim of this exercise was to verify the detection and correlation of the SOC laboratory.

## Environment

### Infrastructure

- Wazuh Manager
- Windows LTSC Workstation
- Sysmon
- Windows Security Logs
- Active Directory
- Discord Integration

### Hosts

- WIN-LTSC1

## Attack Simulation

This was simulated using the Windows Runas tool.

The command was run multiple times as follows:

runas /user:LAB\Administrator cmd

Invalid credentials were intentionally provided in order to generate multiple failed authentication events.

The goal of this attack was to simulate a brute force attempt against a privileged account.

## Evidence Collection

### Evidence 1 - Brute Force Simulation

Command used to simulate the attack:

runas /user:LAB\Administrator cmd

Screenshot:

![Brute Force Simulation](screenshots/01-bruteforce-simulation.png)

### Evidence 2 – Wazuh Detection

Wazuh was able to detect multiple failed login attempts and trigger a custom correlation rule.

Image:

![Wazuh Brute Force Alert](screenshots/02-wazuh-bruteforce-alert.png)

### Evidence 3 – Failed Logon Event (4625)

The Windows Security event ID 4625 confirmed multiple failed logon attempts to the administrator account.

Image:

![Failed Logon Event](screenshots/03-failed-logon-event-4625.png)

### Evidence 4 – Discord Alert

The custom Wazuh integration successfully sent an alert via Discord.

Image:

![Discord Alert](screenshots/04-discord-bruteforce-alert.png)

### Evidence 5 – Dashboard Correlation

A custom dashboard displayed the brute force attack and corresponding MITRE ATT&CK mappings.

Image:

![Brute Force Dashboard](screenshots/05-mitre-bruteforce-dashboard.png)

## Analysis

The observed activity is consistent with a brute force attack against a privileged account.

Multiple failed login attempts resulted in multiple entries in Windows Security Event IDs 4625.

A correlation was made by Wazuh based on the custom correlation rule and generated an alert.

Even though the above-mentioned activity was carried out in a lab setting, if it happened in a production environment, it might suggest:

- Password spraying activities
- Credential guesses attempts
- Unsuccessful unauthorized login attempts
- Initial access attempts

Key characteristics noticed:

- Multiple failed logon attempts
- Windows Event ID 4625
- Target account: Administrator
- Wazuh Rule: 100520
- MITRE ATT&CK: T1110
- Alert level: 12

## MITRE ATT&CK Mapping

### T1110 - Brute Force

The test consisted of repeated attempts at authentication with incorrect credentials targeting a privileged account.

### Credential Access

The goal of the simulated activity was to gain access using password guessing techniques.

## Detection Flow

The detection process was carried out according to the following steps:

1. Multiple failed login attempts were performed.
2. Windows logged event ID 4625.
3. Events were collected by Wazuh.
4. Custom Rule 100520 correlated multiple failed attempts within the given timeframe.
5. An alert was mapped to MITRE ATT&CK technique T1110.
6. An alert was sent to Discord via webhooks.

## Response Actions

The following activities were performed in order to investigate the case:

- Checking the occurrence of repeated failed login attempts.
- Verifying the creation of Windows Event ID 4625.
- Confirming Wazuh rules correlating repeated failures.
- Checking MITRE ATT&CK technique mapping.
- Confirming alert delivery to Discord.
- Identifying the simulation activity.

## Conclusion

The SOC laboratory successfully detected and correlated a simulated brute force attack against a privileged account.

The environment showed its capability to detect:

- Windows Security Log monitoring.
- Failed login detections.
- Correlation using custom Wazuh rules.
- MITRE ATT&CK technique mapping.
- Sending alerts automatically using Discord integration.

The simulation validated the effectiveness of the monitoring pipeline and improved understanding of brute force detection workflows.


