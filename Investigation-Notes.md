# Investigation Notes

## Incident Summary

A Microsoft Exchange Server was suspected to be compromised after users reported issues accessing email services. Initial analysis suggested possible ransomware activity affecting the server.

The objective of this investigation was to analyze available logs using Splunk Enterprise, identify Indicators of Compromise (IOCs), reconstruct the attack timeline, and understand the attacker's behavior throughout the incident.

---

## Investigation Methodology

The investigation followed a structured SOC analysis process:

1. Identify suspicious events.
2. Analyze Sysmon and IIS logs.
3. Collect evidence.
4. Identify Indicators of Compromise (IOCs).
5. Correlate related events.
6. Map attacker techniques using MITRE ATT&CK.
7. Build the attack timeline.
8. Document findings.

---

## Evidence Sources

The following log sources were analyzed during the investigation:

- Microsoft Sysmon Operational Logs
- IIS Web Server Logs
- Windows Event Logs
- Splunk Enterprise

---

## Investigation Steps

The investigation was divided into multiple phases:

### Phase 1 — File Creation Analysis

Objective:

Identify newly created files and the processes responsible for creating them.

Evidence Collected:

- Sysmon Event ID 11
- Image
- TargetFilename

---

### Phase 2 — Suspicious Executable Analysis

Objective:

Analyze suspicious executables and collect their cryptographic hashes.

Evidence Collected:

- SHA256 Hash
- Executable Path

---

### Phase 3 — Ransom Note Detection

Objective:

Identify ransomware notes created during the attack.

Evidence Collected:

- README.txt
- TargetFilename

---

### Phase 4 — Unauthorized User Creation

Objective:

Detect attacker-created local user accounts.

Evidence Collected:

- CommandLine
- net user /add

---

### Phase 5 — Process Injection Investigation

Objective:

Identify process injection and possible credential access.

Evidence Collected:

- Sysmon Event ID 8
- SourceImage
- TargetImage

---

### Phase 6 — Web Shell Investigation

Objective:

Detect suspicious web shell activity using IIS logs.

Evidence Collected:

- HTTP POST Requests
- Suspicious ASPX File

---

## Investigation Outcome

The investigation successfully identified multiple indicators associated with a simulated Conti ransomware attack.

The collected evidence revealed malicious process execution, ransomware note creation, unauthorized user creation, process injection, and web shell activity.

These findings were further correlated to reconstruct the attack timeline and understand the attacker's behavior.
