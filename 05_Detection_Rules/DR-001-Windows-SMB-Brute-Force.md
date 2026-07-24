# Detection Rule

## Detection Information

| Field | Value |
|-------|-------|
| Rule ID | DR-001 |
| Rule Name | Windows SMB Brute Force Detection |
| Status | Active |
| Severity | High |
| Platform | Splunk Enterprise |
| Log Source | Windows Security Logs |
| Event ID | 4625 |

---

# Objective

Detect repeated failed SMB authentication attempts against Windows endpoints that may indicate brute-force or password spraying activity.

---

# Detection Logic

The rule identifies accounts receiving multiple failed authentication attempts from the same source IP.

Threshold:

- Failed Attempts ≥ 3

---

# SPL Query

```spl
index=* source="WinEventLog:Security" EventCode=4625
| stats count as FailedAttempts values(Source_Network_Address) as SourceIP by Account_Name
| where FailedAttempts>=3
| sort - FailedAttempts
```

---

# Expected Output

- Source IP
- Target Account
- Failed Attempts

---

# Investigation Steps

1. Identify Source IP
2. Identify Target User
3. Verify Authentication Timeline
4. Check for Successful Logon (4624)
5. Determine if activity is authorized

---

# False Positives

- User entering incorrect passwords
- Password expiration
- Automated management tools

---

# MITRE ATT&CK

| Tactic | Technique | ID |
|---------|-----------|----|
| Credential Access | Brute Force | T1110 |

---

# Detection Validation

Validated using controlled SMB password spraying from the Kali attack workstation against CLIENT1.
