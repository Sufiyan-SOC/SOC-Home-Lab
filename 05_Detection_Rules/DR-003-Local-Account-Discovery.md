# Detection Rule

## Detection Information

| Field | Value |
|-------|-------|
| Rule ID | DR-002 |
| Rule Name | Windows Local Account Discovery Detection |
| Status | Active |
| Severity | Medium |
| Platform | Splunk Enterprise |
| Log Source | Microsoft Sysmon |
| Event ID | 1 (Process Creation) |

---

# Objective

Detect execution of Windows native account and privileged group discovery commands that may indicate post-compromise reconnaissance performed by an attacker.

---

# Detection Logic

The rule monitors execution of common Windows discovery utilities used to enumerate:

- Current logged-on user
- Local user accounts
- Group memberships
- Local administrator group

Monitored binaries:

- whoami.exe
- net.exe

---

# SPL Query

```spl
index=* source="XmlWinEventLog:Microsoft-Windows-Sysmon/Operational" EventCode=1
(Image="*\\whoami.exe" OR Image="*\\net.exe")
| table _time Computer User Image CommandLine
| sort - _time
```

---

# Expected Output

- Time
- Hostname
- Username
- Executed Process
- Command Line

---

# Investigation Steps

1. Identify the endpoint executing the discovery commands.
2. Identify the user account responsible for execution.
3. Review the complete command line.
4. Verify the parent process that launched the command.
5. Determine whether the activity is administrative or suspicious.
6. Correlate with additional process execution or authentication events.

---

# False Positives

- System administrators performing legitimate administration
- Helpdesk personnel
- IT support scripts
- Automated inventory or management tools

---

# MITRE ATT&CK

| Tactic | Technique | ID |
|---------|-----------|----|
| Discovery | Local Account Discovery | T1087.001 |
| Discovery | Local Group Discovery | T1069.001 |

---

# Detection Validation

Validated by executing the following Windows discovery commands from a domain-joined Windows 11 Enterprise endpoint:

```cmd
whoami
hostname
whoami /groups
net user
net localgroup administrators
```

The commands generated Microsoft Sysmon Event ID 1 (Process Creation) events, which were successfully forwarded to Splunk Enterprise and detected by the rule.

---

# Analyst Notes

This detection identifies one of the most common reconnaissance activities performed immediately after initial access. While these commands are legitimate Windows administrative utilities, repeated or unexpected execution by standard users should be investigated, especially when followed by privilege escalation, credential access, or lateral movement activity.
