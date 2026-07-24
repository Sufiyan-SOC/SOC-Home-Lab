# T1135 - Network Share Discovery

## Technique

Network Share Discovery

## Tactic

Discovery

## Lab Scenario

A simulated attacker enumerated Windows shared resources using native commands before attempting potential lateral movement.

## Detection

- Microsoft Sysmon Event ID 1

## SIEM Detection

Splunk Enterprise detected execution of Windows network share discovery commands.

## Investigation Data

- Endpoint
- User
- Command Line
- Parent Process
- Timeline

## Mitigation

- Monitor share enumeration activity.
- Restrict unnecessary share access.
- Investigate repeated discovery activity.
- Correlate with SMB authentication and file access events.
