# Attack Timeline

This document reconstructs the attack timeline based on evidence collected from Sysmon and IIS logs during the simulated Conti ransomware investigation.

---

## Attack Timeline

| Phase | MITRE Tactic | Evidence | Description |
|--------|--------------|----------|-------------|
| 1. Initial Access | Initial Access | Suspicious ASPX web shell | The attacker gained initial access by uploading a malicious ASPX web shell to the Microsoft Exchange Server. |
| 2. Web Shell Activity | Execution | IIS HTTP POST requests | IIS logs revealed HTTP POST requests indicating interaction with the uploaded web shell. |
| 3. Command Execution | Execution | `powershell.exe` and `cmd.exe` | The attacker executed malicious PowerShell and Command Prompt commands on the compromised host. |
| 4. Suspicious File Creation | Discovery | Sysmon Event ID 11 | File creation events were analyzed to identify suspicious executables and attacker activity. |
| 5. Local User Creation | Persistence | `net user /add securityninja hardToHack123$` | A new local administrator account was created to maintain persistence. |
| 6. Process Injection | Defense Evasion | Sysmon Event ID 8 | Process injection activity involving `powershell.exe`, `unsecapp.exe`, and `lsass.exe` was observed. |
| 7. Credential Access | Credential Access | `lsass.exe` | Activity involving LSASS suggested an attempt to access user credentials. |
| 8. Ransomware Execution | Impact | Multiple `README.txt` files | The creation of ransom notes confirmed successful ransomware execution. |

---

## Attack Flow

```text
Initial Access
      │
      ▼
Web Shell Upload
      │
      ▼
HTTP POST Requests
      │
      ▼
PowerShell Execution
      │
      ▼
Command Prompt Execution
      │
      ▼
Suspicious File Creation
      │
      ▼
Local User Creation
      │
      ▼
Process Injection
      │
      ▼
Credential Access (LSASS)
      │
      ▼
Ransomware Execution
      │
      ▼
README.txt Ransom Notes
```

---

## Investigation Summary

The attack timeline was reconstructed by correlating evidence from Microsoft Sysmon Operational logs and IIS web server logs. The investigation identified the attacker's progression from initial access through web shell deployment, command execution, persistence, process injection, credential access, and finally ransomware execution. This timeline provides a structured view of the attack lifecycle and supports incident response and future threat hunting activities.

---

## Key Evidence

- Suspicious ASPX web shell detected.
- HTTP POST requests observed in IIS logs.
- Malicious PowerShell and CMD execution.
- Suspicious file creation identified using Sysmon Event ID 11.
- Unauthorized local user account creation.
- Process injection involving `unsecapp.exe` and `lsass.exe`.
- Multiple `README.txt` ransom notes confirming ransomware execution.
