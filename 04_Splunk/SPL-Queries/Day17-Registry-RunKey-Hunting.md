# Registry Run Key Queries

## 1. Detect Registry Value Set Events

```spl
index=* source="XmlWinEventLog:Microsoft-Windows-Sysmon/Operational" "<EventID>13</EventID>"
```

Purpose:
Identify Sysmon Registry Value Set events.

---

## 2. Investigate Registry Run Key

```spl
index=* source="XmlWinEventLog:Microsoft-Windows-Sysmon/Operational" SOCLabTest
| table _time Image TargetObject Details User
```

Purpose:
Investigate a specific Registry Run Key modification.

---

## 3. Detect Run / RunOnce Persistence

```spl
index=* source="XmlWinEventLog:Microsoft-Windows-Sysmon/Operational" "<EventID>13</EventID>"
(TargetObject="*\\CurrentVersion\\Run\\*" OR TargetObject="*\\CurrentVersion\\RunOnce\\*")
| table _time Computer User Image TargetObject Details
```

Purpose:
Detect Registry-based persistence.

---

## 4. Registry Timeline

```spl
index=* source="XmlWinEventLog:Microsoft-Windows-Sysmon/Operational" SOCLabTest
| sort _time
| table _time Computer User Image TargetObject Details
```

Purpose:
Create an investigation timeline for Registry persistence events.
