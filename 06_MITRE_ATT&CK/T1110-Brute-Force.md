# T1110 - Brute Force

## Technique
Brute Force

## Tactic
Credential Access

## Lab Scenario
Simulated SMB password spraying attack against Windows domain endpoint.

## Detection

- Windows Security Event ID: 4625 (Failed Logon)
- Windows Security Event ID: 4624 (Successful Logon)

## SIEM Detection

Splunk used to identify multiple failed authentication attempts from a single source IP.

## Investigation Data

- Source IP
- Target Username
- Failed Login Attempts
- Authentication Timeline

## Mitigation

- Strong password policy
- Account lockout policy
- MFA implementation
- Monitor abnormal authentication activity
