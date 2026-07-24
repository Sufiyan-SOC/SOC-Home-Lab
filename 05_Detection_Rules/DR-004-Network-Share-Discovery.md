# Detection Rule

## Detection Information

| Field | Value |
|-------|-------|
| Rule ID | DR-003 |
| Rule Name | Windows Network Share Discovery Detection |
| Status | Active |
| Severity | Medium |
| Platform | Splunk Enterprise |
| Log Source | Microsoft Sysmon |
| Event ID | 1 |

---

# Objective

Detect execution of Windows native commands used to enumerate network shares and shared resources.

---

# Detection Logic

The rule monitors execution of:

- net share
- net use
- net view
- SYSVOL
- NETLOGON

---

# SPL Query

(Use Detection Query from Day32-Network-Share-Discovery.spl)

---

# Expected Output

- Time
- Computer
- User
- Process
- Command Line

---

# Investigation Steps

1. Identify endpoint
2. Identify user
3. Review command line
4. Review parent process
5. Determine legitimacy

---

# False Positives

- Windows administrators
- Helpdesk staff
- IT automation

---

# MITRE ATT&CK

| Tactic | Technique | ID |
|---------|-----------|----|
| Discovery | Network Share Discovery | T1135 |

---

# Detection Validation

Validated through controlled execution of Windows network share enumeration commands from CLIENT1.

---

# Analyst Notes

Network share discovery is commonly performed before lateral movement and data access. Unexpected execution by standard users should be investigated.
