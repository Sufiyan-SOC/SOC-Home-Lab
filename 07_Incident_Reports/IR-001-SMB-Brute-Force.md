# Incident Report

## Incident Information

| Field | Value |
|-------|-------|
| Incident ID | IR-001 |
| Incident Name | SMB Brute Force Detection |
| Severity | High |
| Status | Closed (Lab Validation) |
| Detection Source | Splunk Enterprise |

---

# Executive Summary

Splunk Enterprise detected multiple failed SMB authentication attempts against a Windows 11 Enterprise endpoint.

The activity originated from the authorized Kali Linux attack workstation used during the Enterprise SOC Lab.

The incident was investigated and validated as an expected lab simulation.

---

# Timeline

| Phase | Description |
|---------|------------|
| Attack | SMB password spraying executed |
| Detection | Windows Event ID 4625 generated |
| Collection | Splunk indexed authentication logs |
| Alert | Detection rule triggered |
| Investigation | Source IP and target account identified |
| Closure | Activity confirmed as authorized lab exercise |

---

# Indicators of Compromise

## Source IP

172.16.0.101

## Destination Host

CLIENT1

## Target Account

aabrev

## Event IDs

4625

4624

---

# Investigation Summary

The investigation confirmed:

- Multiple failed authentication attempts
- Successful identification of attacking source
- Target account validation
- Authentication timeline reconstruction

---

# Root Cause

Controlled password spraying simulation performed during the Enterprise SOC Lab.

---

# Impact Assessment

No unauthorized access.

No malware execution.

No persistence established.

---

# Analyst Actions

- Reviewed authentication events
- Validated source IP
- Confirmed affected account
- Verified successful authentication
- Closed incident

---

# Lessons Learned

- Authentication monitoring successfully detected repeated failures.
- Splunk dashboards provided rapid visibility.
- Detection rule functioned as expected.

---

# Recommendations

- Implement account lockout policies.
- Enable scheduled correlation searches.
- Continue monitoring repeated authentication failures.
