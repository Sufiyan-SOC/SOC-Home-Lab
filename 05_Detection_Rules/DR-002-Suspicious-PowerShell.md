# Detection Rule

## Detection Information

| Field | Value |
|-------|-------|
| Rule ID | DR-002 |
| Rule Name | Suspicious PowerShell Execution |
| Severity | High |
| Platform | Splunk Enterprise |
| Log Source | Sysmon Event ID 1 |

---

# Objective

Detect PowerShell executions containing command-line arguments commonly observed during malicious activity.

---

# Detection Logic

Monitor PowerShell process creation events and identify executions containing:

- EncodedCommand
- -enc
- -nop
- Hidden Window
- Invoke-WebRequest
- DownloadString

---

# SPL Query

```spl
index=* source="XmlWinEventLog:Microsoft-Windows-Sysmon/Operational" EventCode=1 Image="*powershell.exe"
(CommandLine="*-enc*" OR CommandLine="*-EncodedCommand*" OR CommandLine="*-nop*" OR CommandLine="*-w hidden*" OR CommandLine="*Invoke-WebRequest*" OR CommandLine="*DownloadString*")
| table _time Computer User ParentImage CommandLine
| sort - _time
```

---

# Alert Configuration

Alert Name

Suspicious PowerShell Execution

Schedule

Every 5 Minutes

Trigger

Results > 0

Severity

High

---

# Investigation Guide

SOC analysts should verify:

- Source Endpoint
- Executing User
- Parent Process
- Command Line
- Execution Time
- Related Events

---

# Common False Positives

- Administrative PowerShell usage
- Automation scripts
- Enterprise management tools

---

# MITRE ATT&CK

| Tactic | Technique | ID |
|---------|-----------|----|
| Execution | PowerShell | T1059.001 |

---

# Detection Outcome

The detection successfully identified suspicious PowerShell executions during security monitoring.

The generated telemetry provided sufficient evidence to perform endpoint investigation and incident analysis.
