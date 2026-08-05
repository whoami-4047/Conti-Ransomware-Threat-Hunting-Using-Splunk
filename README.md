# Conti Ransomware Threat Hunting Using Splunk

## Overview

This project demonstrates a threat hunting investigation of a simulated Conti ransomware attack using Splunk Enterprise. During the investigation, Sysmon and IIS logs were analyzed to identify attacker activity, detect indicators of compromise (IOCs), and reconstruct the attack timeline.

The investigation focuses on identifying malicious processes, suspicious file creation events, ransomware notes, web shell activity, process injection, and persistence techniques used by the attacker.

## Scenario

A Microsoft Exchange Server was suspected to be compromised after users experienced issues accessing email services. During the investigation, evidence of ransomware activity was identified, including suspicious process execution, malicious file creation, web shell activity, unauthorized user account creation, and ransomware notes.

As a SOC Analyst, the objective was to analyze Sysmon and IIS logs in Splunk, identify Indicators of Compromise (IOCs), reconstruct the attack timeline, and understand the attacker's techniques and behavior.

## Objectives

- Investigate suspicious activities using Splunk Enterprise.
- Analyze Sysmon and IIS logs for attacker behavior.
- Detect malicious file creation and ransomware notes.
- Identify unauthorized user account creation.
- Detect process injection and possible credential access.
- Investigate web shell activity on the Exchange Server.
- Collect Indicators of Compromise (IOCs).
- Map attacker techniques to the MITRE ATT&CK framework.
- Reconstruct the attack timeline.

## Lab Environment

| Component | Details |
|----------|---------|
| SIEM Platform | Splunk Enterprise |
| Log Source | Microsoft Sysmon |
| Web Server Logs | IIS Logs |
| Operating System | Windows Server |
| Target Application | Microsoft Exchange Server |
| Investigation Type | Threat Hunting |
| Attack Simulation | Conti Ransomware |


## Investigation Workflow

The investigation followed a structured threat hunting approach:

1. Review Sysmon Event ID 11 to identify file creation events.
2. Analyze suspicious executable hashes.
3. Detect ransomware notes (README.txt).
4. Investigate unauthorized local user creation.
5. Identify process injection activity.
6. Detect malicious web shell activity through IIS logs.
7. Verify the uploaded web shell.
8. Collect Indicators of Compromise (IOCs).
9. Map attacker behavior to the MITRE ATT&CK framework.
10. Build the complete attack timeline.

## Tools Used

- Splunk Enterprise
- Microsoft Sysmon
- IIS Logs
- Microsoft Exchange Server
- Windows Event Logs

## Attack Timeline

| Phase | Description |
|-------|-------------|
| Initial Access | Attacker gained access to the Exchange Server. |
| Web Shell | Suspicious ASPX web shell was identified. |
| Execution | Malicious commands were executed using PowerShell and CMD. |
| Persistence | Unauthorized local user account was created. |
| Credential Access | Process injection into LSASS was observed. |
| Impact | Multiple README.txt ransom notes were created. |

## Key Findings

- Investigated Sysmon Event ID 11 to identify suspicious file creation.
- Extracted the SHA256 hash of a suspicious executable.
- Detected multiple README.txt ransom notes.
- Identified unauthorized local user creation for persistence.
- Observed process injection involving PowerShell, unsecapp.exe, and lsass.exe.
- Detected a suspicious ASPX web shell through IIS logs.
- Collected Indicators of Compromise (IOCs).
- Reconstructed the attack timeline using Splunk.

## 📂 Repository Structure

```
Conti-Ransomware-Threat-Hunting-Using-Splunk/
│
├── README.md
├── Investigation-Notes.md
├── Splunk-Queries.md
├── IOC.md
├── MITRE-ATTACK.md
├── Attack-Timeline.md
└── Screenshots/
```

### 📁 Project Files

- 📄 [README.md](./README.md)
- 📄 [Investigation-Notes.md](./Investigation-Notes.md)
- 📄 [Splunk-Queries.md](./Splunk-Queries.md)
- 📄 [IOC.md](./IOC.md)
- 📄 [MITRE-ATTACK.md](./MITRE-ATTACK.md)
- 📄 [Attack-Timeline.md](./Attack-Timeline.md)
- 🖼️ [Screenshots](./Screenshots/)

### 📸 Investigation Screenshots

- [01 - Processes Creating Files](./Screenshots/01_Processes_Creating_Files.jpeg)
- [02 - Malicious File Hash](./Screenshots/02_Malicious_File_Hash.jpeg)
- [03 - Ransom Note Detection](./Screenshots/03_Ransom_Note_Detection.jpeg)
- [04 - Suspicious User Creation](./Screenshots/04_Suspicious_User_Creation.jpeg)
- [05 - Process Injection](./Screenshots/05_Process_Injection.jpeg)
- [06 - Web Shell Detection](./Screenshots/06_Web_Shell_Detection.jpeg)
- [07 - Web Shell Verification](./Screenshots/07_Web_Shell_Verification.jpeg)

## Skills Demonstrated

- Threat Hunting
- Splunk SIEM
- Sysmon Log Analysis
- IIS Log Analysis
- IOC Identification
- Process Analysis
- Windows Event Log Analysis
- MITRE ATT&CK Mapping
- Attack Timeline Reconstruction

## Disclaimer

This project is based on a controlled cybersecurity lab environment created for educational purposes. The investigation was performed using simulated log data to practice threat hunting and incident analysis techniques.



