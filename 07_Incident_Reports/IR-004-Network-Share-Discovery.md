
# Incident Report

## Incident Information

| Field | Value |
|-------|-------|
| Incident ID | IR-004 |
| Incident Name | Windows Network Share Discovery |
| Severity | Medium |
| Status | Closed |
| Detection Source | Splunk Enterprise |

---

# Executive Summary

Splunk detected execution of Windows network share discovery commands on CLIENT1. The activity generated Microsoft Sysmon Process Creation events and was investigated to determine whether it represented legitimate administration or attacker reconnaissance.

---

# Timeline

| Phase | Activity |
|---------|----------|
| Detection Rule | Created |
| SPL Query | Executed |
| Alert | Generated |
| Dashboard | Updated |
| Attack Simulation | Performed |
| Investigation | Completed |
| Incident Report | Documented |

---

# Indicators

**Endpoint**

CLIENT1

**User**

CORP\aabrev

**Processes**

- net.exe
- cmd.exe

**Executed Commands**

- net share
- net use
- dir \\DC01\SYSVOL
- dir \\DC01\NETLOGON

---

# Investigation Summary

- Windows share discovery commands were executed.
- Activity originated from CLIENT1.
- Sysmon Event ID 1 captured the execution.
- Splunk correlated and displayed the activity.
- No lateral movement was observed.

---

# Recommendations

- Monitor network share discovery.
- Correlate with SMB access events.
- Investigate repeated discovery activity by non-administrative users.

---

# Analyst Verdict

**Classification:** True Positive

**Confidence:** High

**Business Impact:** Low (Lab Simulation)
