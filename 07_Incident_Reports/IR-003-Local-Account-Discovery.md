# Incident Report

## Incident Information

| Field | Value |
|-------|-------|
| Incident ID | IR-003 |
| Incident Name | Windows Local Account Discovery |
| Severity | Medium |
| Status | Closed |
| Detection Source | Splunk Enterprise |

---

# Executive Summary

Splunk Enterprise detected execution of Windows account and privileged group discovery commands on a monitored Windows endpoint.

The alert was generated after Microsoft Sysmon Process Creation (Event ID 1) logs identified execution of Windows native utilities commonly used for post-compromise reconnaissance.

The incident was investigated using Splunk search queries, dashboards, and endpoint telemetry to determine whether the activity represented legitimate administration or attacker reconnaissance.

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

CORP\aabrev

---

## Executed Processes

- whoami.exe
- net.exe

---

## Parent Process

cmd.exe

---

## Executed Commands

- whoami
- hostname
- whoami /groups
- net user
- net localgroup administrators

---

# Investigation Summary

The investigation confirmed:

- Windows discovery commands were executed on CLIENT1.
- The activity originated from the user **CORP\aabrev**.
- Microsoft Sysmon Event ID 1 captured all executed processes.
- Parent process analysis identified **cmd.exe** as the originating process.
- Splunk successfully detected and visualized the activity through custom SPL queries and dashboards.
- No evidence of privilege escalation or lateral movement was observed during this simulation.

---

# MITRE ATT&CK Mapping

| Tactic | Technique | ID |
|---------|-----------|----|
| Discovery | Local Account Discovery | T1087.001 |
| Discovery | Local Group Discovery | T1069.001 |

---

# Recommendations

- Monitor execution of Windows discovery commands by standard users.
- Correlate discovery activity with authentication and privilege escalation events.
- Review parent-child process relationships for suspicious process execution.
- Investigate repeated discovery activity across multiple endpoints.
- Continue monitoring for follow-on techniques such as Credential Access or Lateral Movement.

---

# Conclusion

The simulated attack successfully demonstrated how post-compromise discovery activity can be detected using Microsoft Sysmon and Splunk Enterprise. The detection rule generated a valid alert, supporting investigation through endpoint telemetry, dashboard visualization, and MITRE ATT&CK mapping. The activity was classified as a **True Positive** within the controlled Enterprise SOC Lab environment.
