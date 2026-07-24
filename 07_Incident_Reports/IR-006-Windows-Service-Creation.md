# Incident Report

## Incident Information

| Field | Value |
|-------|-------|
| Incident ID | IR-006 |
| Incident Name | Windows Service Creation |
| Severity | High |
| Status | Closed |
| Detection Source | Splunk Enterprise |

---

# Executive Summary

Splunk detected execution of a Windows service creation command using **sc.exe**. Sysmon Event ID 1 recorded the process execution, allowing investigation of the user, endpoint, and command-line activity.

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

CORP\aabrev

---

## Process

sc.exe

---

## Command

sc create TestService

---

# Investigation Summary

- Service creation command executed.
- Activity originated from CLIENT1.
- Sysmon Event ID 1 confirmed execution.
- Splunk correlated endpoint, user, and command-line information.
- Activity was generated as part of a controlled enterprise lab.

---

# Recommendations

- Monitor Windows service creation.
- Investigate unauthorized services.
- Review parent-child process relationships.
- Restrict service creation privileges.

---

# Analyst Verdict

Classification: True Positive

Confidence: High

Business Impact: Low (Lab Simulation)
