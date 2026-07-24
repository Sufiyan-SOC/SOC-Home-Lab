# Detection Rule

## Detection Information

| Field | Value |
|-------|-------|
| Rule ID | DR-005 |
| Rule Name | Windows Service Creation Detection |
| Status | Active |
| Severity | High |
| Platform | Splunk Enterprise |
| Log Source | Microsoft Sysmon |
| Event ID | 1 |

---

# Objective

Detect execution of Windows service creation commands that may indicate persistence or privilege escalation.

---

# Detection Logic

Monitor **sc.exe** executing with the **create** parameter.

---

# SPL Query

```spl
index=* source="XmlWinEventLog:Microsoft-Windows-Sysmon/Operational"
EventCode=1
Image="*\\sc.exe"
| search CommandLine="*create*"
```

---

# Expected Output

- Time
- Endpoint
- User
- Parent Process
- Command Line

---

# Investigation Steps

1. Verify endpoint.
2. Identify user.
3. Review service creation command.
4. Investigate parent process.
5. Confirm administrative authorization.

---

# False Positives

- System administrators
- Software installation
- Enterprise management tools

---

# MITRE ATT&CK

| Tactic | Technique | ID |
|---------|-----------|----|
| Persistence | Create or Modify System Process: Windows Service | T1543.003 |

---

# Detection Validation

Validated using controlled execution of **sc create** on CLIENT1.

---

# Analyst Notes

Unexpected service creation should be investigated immediately, especially when performed by standard users or outside maintenance windows.
