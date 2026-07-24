# Detection Rule

## Detection Information

| Field | Value |
|-------|-------|
| Rule ID | DR-004 |
| Rule Name | Successful Remote Desktop Logon Detection |
| Status | Active |
| Severity | Medium |
| Platform | Splunk Enterprise |
| Log Source | Windows Security Logs |
| Event ID | 4624 |

---

# Objective

Detect successful Remote Desktop Protocol (RDP) logons that may indicate legitimate remote administration or attacker lateral movement.

---

# Detection Logic

The rule identifies successful Windows authentication events where Logon Type equals 10.

---

# SPL Query

```spl
index=* source="WinEventLog:Security" EventCode=4624 LogonType=10
| table _time ComputerName Account_Name Source_Network_Address WorkstationName
```

---

# Expected Output

- Source IP
- Target Endpoint
- Username
- Workstation
- Logon Time

---

# Investigation Steps

1. Verify source IP.
2. Identify authenticated user.
3. Review authentication timeline.
4. Confirm expected administrative activity.
5. Investigate unusual login locations.

---

# False Positives

- System administrators
- Helpdesk personnel
- Authorized remote support

---

# MITRE ATT&CK

| Tactic | Technique | ID |
|---------|-----------|----|
| Lateral Movement | Remote Desktop Protocol | T1021.001 |

---

# Detection Validation

Validated through a successful Remote Desktop session initiated from the Kali attack workstation to CLIENT1.

---

# Analyst Notes

Unexpected RDP activity should always be correlated with user behavior, source IP reputation, and subsequent administrative actions.
