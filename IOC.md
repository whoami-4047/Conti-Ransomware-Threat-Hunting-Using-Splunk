# Indicators of Compromise (IOCs)

This document summarizes the Indicators of Compromise (IOCs) identified during the investigation of the simulated Conti ransomware attack. These indicators can assist security analysts in identifying similar malicious activity in enterprise environments.

---

## File Hash

| IOC Type | Value | Description |
|----------|-------|-------------|
| SHA256 Hash | `53B1C1B2F41A7FC300E97D036E57539453FF82001DD3F6ABF07F4896B1F9CA22` | SHA256 hash of the suspicious executable identified during the investigation. |

---

## Suspicious Files

| File Name | Description |
|-----------|-------------|
| README.txt | Ransom note created after ransomware execution. |
| i3gfPctK1c2x.aspx | Suspicious ASPX web shell identified on the Exchange Server. |

---

## Suspicious Processes

| Process | Description |
|----------|-------------|
| powershell.exe | Used to execute malicious commands. |
| cmd.exe | Suspicious executable observed during the investigation. |
| unsecapp.exe | Observed during process injection activity. |
| lsass.exe | Targeted during credential access techniques. |

---

## Suspicious Command

```cmd
net user /add securityninja hardToHack123$
```

### Description

The attacker created a new local user account to establish persistence on the compromised system.

---

## Log Sources

- Microsoft Sysmon Operational Logs
- IIS Web Server Logs
- Windows Event Logs

---

## Summary

The collected Indicators of Compromise provide evidence of ransomware execution, persistence, process injection, credential access attempts, and web shell activity. These IOCs can be used to support future threat hunting and incident response activities.
