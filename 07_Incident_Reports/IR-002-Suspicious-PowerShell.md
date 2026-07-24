# Incident Report

## Incident Information

| Field | Value |
|-------|-------|
| Incident ID | IR-002 |
| Incident Name | Suspicious PowerShell Execution |
| Severity | High |
| Status | Closed |
| Detection Source | Splunk Enterprise |

---

# Executive Summary

Splunk Enterprise detected suspicious PowerShell execution on a monitored Windows endpoint.

The alert was generated after Sysmon Process Creation logs identified PowerShell commands containing command-line arguments commonly associated with attacker activity.

The incident was investigated using Splunk dashboards, search queries, and endpoint telemetry.

---

# Timeline

| Phase | Activity |
|---------|----------|
| Detection Rule | Created |
| SPL Query | Executed |
| Alert | Generated |
| Dashboard | Updated |
| Attack Simulation | Performed |
| Alert Trigger | Observed |
| Dashboard Analysis | Completed |
| Investigation | Performed |
| Incident Report | Documented |

---

# Indicators

## Endpoint

CLIENT1

---

## User

corp\administrator

---

## Process

powershell.exe

---

## Parent Process

explorer.exe

---

## Suspicious Arguments

- EncodedCommand
- NoProfile
- Hidden Window

---

# Investigation Summary

The investigation confirmed:

- PowerShell execution occurred on CLIENT1.
- Suspicious command-line arguments were observed.
- Parent process information was collected.
- Execution timeline was reconstructed using Sysmon telemetry.
- Alert generation matched the observed endpoint activity.

---

# Recommendations

- Review encoded PowerShell commands.
- Investigate unusual parent-child process relationships.
- Expand detection coverage for PowerShell abuse techniques.
