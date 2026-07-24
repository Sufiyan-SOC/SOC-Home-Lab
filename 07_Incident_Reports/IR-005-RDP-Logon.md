# Incident Report

## Incident Information

| Field | Value |
|-------|-------|
| Incident ID | IR-005 |
| Incident Name | Successful Remote Desktop Logon |
| Severity | Medium |
| Status | Closed |
| Detection Source | Splunk Enterprise |

---

# Executive Summary

Splunk Enterprise detected a successful Remote Desktop authentication on CLIENT1. Windows Security Event ID 4624 with Logon Type 10 confirmed an interactive RDP session.

The event was investigated to verify user identity, source IP, and endpoint activity.

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

## Source

Kali Linux

---

## Source IP

172.16.0.101

---

## Windows Event

4624

---

## Logon Type

10 (Remote Interactive)

---

# Investigation Summary

- Successful RDP authentication confirmed.
- Authentication originated from the Kali workstation.
- Windows Security Event ID 4624 validated the session.
- Splunk successfully correlated endpoint, user, and source IP information.
- Activity was generated as part of a controlled lab simulation.

---

# Recommendations

- Monitor successful RDP logons from unusual IP addresses.
- Restrict RDP access through firewall rules.
- Require MFA for remote administrative access.
- Review RDP activity outside business hours.

---

# Analyst Verdict

Classification: True Positive

Confidence: High

Business Impact: Low (Lab Simulation)
