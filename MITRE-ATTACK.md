# MITRE ATT&CK Mapping

This document maps the observed attacker activities to the MITRE ATT&CK Enterprise Framework based on evidence collected during the investigation.

---

## MITRE ATT&CK Mapping

| Tactic | Technique ID | Technique | Evidence |
|---------|--------------|-----------|----------|
| Initial Access | T1505.003 | Web Shell | Suspicious ASPX web shell identified through IIS logs. |
| Execution | T1059.001 | PowerShell | Malicious PowerShell execution observed during the investigation. |
| Execution | T1059.003 | Windows Command Shell | Suspicious `cmd.exe` execution identified in Sysmon logs. |
| Persistence | T1136.001 | Create Local Account | `net user /add securityninja hardToHack123$` command created a new local account. |
| Defense Evasion | T1055 | Process Injection | Process injection observed involving `powershell.exe`, `unsecapp.exe`, and `lsass.exe`. |
| Credential Access | T1003.001 | LSASS Memory | Activity involving `lsass.exe` indicated potential credential access. |
| Impact | T1486 | Data Encrypted for Impact | Multiple `README.txt` ransom notes indicated ransomware execution. |

---

## MITRE ATT&CK Matrix Summary

| Tactic | Status |
|---------|--------|
| Initial Access | ✅ Identified |
| Execution | ✅ Identified |
| Persistence | ✅ Identified |
| Defense Evasion | ✅ Identified |
| Credential Access | ✅ Identified |
| Impact | ✅ Identified |

---

## Investigation Summary

The investigation identified multiple attacker techniques consistent with a Conti ransomware intrusion. Evidence collected from Sysmon and IIS logs showed web shell activity, malicious command execution, unauthorized account creation, process injection, credential access attempts, and ransomware execution. Mapping these activities to the MITRE ATT&CK framework helps security analysts understand the attack lifecycle and improve detection and response strategies.

---

