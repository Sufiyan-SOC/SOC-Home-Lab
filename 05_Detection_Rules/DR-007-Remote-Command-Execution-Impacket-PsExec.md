# Detection Rule

## Detection Information

| Field | Value |
|-------|-------|
| Rule ID | DR-006 |
| Rule Name | Remote Command Execution via Impacket PsExec |
| Status | Active |
| Severity | High |
| Platform | Splunk Enterprise |
| Log Source | Microsoft Sysmon |
| Event ID | 1 |

---

# Objective

Detect remote command execution performed using Impacket PsExec, a widely used post-exploitation framework for lateral movement.

---

# Detection Logic

Monitor Sysmon Process Creation events where:

- User = NT AUTHORITY\SYSTEM
- Image = cmd.exe
- Parent process indicates remote execution artifact

---

# SPL Query

```spl
index=* source="XmlWinEventLog:Microsoft-Windows-Sysmon/Operational"
EventCode=1
User="NT AUTHORITY\\SYSTEM"
Image="*\\cmd.exe"
```

---

# Expected Output

- Endpoint
- Parent Process
- Executed Command
- User
- Timestamp

---

# Investigation Steps

1. Identify affected endpoint.
2. Review parent process.
3. Verify executed command.
4. Correlate authentication logs.
5. Determine business justification.

---

# False Positives

- Authorized administrators
- Remote support sessions
- Approved automation tools

---

# MITRE ATT&CK

| Tactic | Technique | ID |
|---------|-----------|----|
| Lateral Movement | SMB / Windows Admin Shares | T1021.002 |

---

# Detection Validation

Validated using Impacket PsExec from the Kali attack workstation against CLIENT1.

---

# Analyst Notes

Unexpected SYSTEM-level remote command execution should be treated as a high-priority investigation due to its association with post-exploitation and lateral movement.

---

# Recommendations

- Restrict remote administrative access.
- Monitor SYSTEM-level process creation.
- Review remote administration tools.
- Correlate authentication and process creation events.
