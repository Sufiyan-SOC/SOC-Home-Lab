# Incident Report

## Incident Information

| Field | Value |
|-------|-------|
| Incident ID | IR-007 |
| Incident Name | Remote Command Execution via Impacket PsExec |
| Severity | High |
| Status | Closed |
| Detection Source | Splunk Enterprise |

---

# Executive Summary

Splunk detected remote command execution performed using Impacket PsExec.

Microsoft Sysmon Event ID 1 recorded SYSTEM-level command execution on CLIENT1, allowing analysts to identify the executed command, parent process, and affected endpoint.

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

## Endpoint

CLIENT1

---

## User

NT AUTHORITY\SYSTEM

---

## Parent Process

Random Impacket executable

---

## Executed Process

cmd.exe

---

# Investigation Summary

- Remote command execution confirmed.
- SYSTEM-level process identified.
- Parent process validated.
- Splunk successfully correlated endpoint and command execution.
- Activity originated from the Kali attack workstation as part of a controlled enterprise lab.

---

# Business Impact

If performed by an attacker, remote command execution enables lateral movement, remote administration, and post-exploitation across enterprise systems.

Current Impact:

Low (Lab Simulation)

---

# Recommendations

- Restrict administrative SMB access.
- Monitor remote SYSTEM process creation.
- Correlate authentication and process telemetry.
- Investigate unusual parent-child process relationships.

---

# Analyst Verdict

Classification: True Positive

Confidence: High

Business Impact: Low (Lab Simulation)
