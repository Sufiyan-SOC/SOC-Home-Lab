# 🛡️ Security Operations Center (SOC) Home Lab

## Windows Security Monitoring Lab using Splunk, Active Directory, and Sysmon

This project demonstrates the design and implementation of a Security Operations Center (SOC) Home Lab built using Oracle VirtualBox.

The lab simulates a Windows Active Directory environment where security events are generated, collected, monitored, and investigated using Splunk Enterprise. The environment provides hands-on experience with Windows administration, Active Directory, centralized logging, security monitoring, attack simulation, alert development, and incident investigation.

The primary objective of this project is to develop practical Blue Team skills required for an entry-level SOC Analyst role by working with industry-standard security technologies and real-world SOC workflows.

---

# 🎯 Project Objectives

- Build an Active Directory environment
- Configure Windows Server as a Domain Controller
- Deploy DNS and DHCP services
- Join Windows endpoints to the domain
- Deploy Splunk Enterprise
- Configure Splunk Universal Forwarder
- Deploy Microsoft Sysmon
- Centralize Windows Security and Sysmon logs
- Simulate attacks from Kali Linux
- Develop SPL detection use cases
- Create SIEM alerts and dashboards
- Investigate security events
- Map detections to the MITRE ATT&CK Framework
- Document security incidents

---

# 🏗️ Lab Architecture

```text
                           Internet
                              │
                           NAT Network
                              │
                  ┌────────────────────────┐
                  │ Windows Server 2022    │
                  │ DC01                   │
                  │ Active Directory       │
                  │ DNS • DHCP             │
                  │ NAT + Internal         │
                  └────────────┬───────────┘
                               │
                     Internal Network
        ┌──────────────────────┼──────────────────────┐
        │                      │                      │
 ┌──────────────┐      ┌────────────────┐     ┌──────────────┐
 │ Windows 11   │      │ Ubuntu Server  │     │ Kali Linux   │
 │ CLIENT1      │      │ Splunk SIEM    │     │ Attack VM    │
 │ Domain Joined│      │ Log Collection │     │ Attack Sim   │
 └──────────────┘      └────────────────┘     └──────────────┘
```

---

# 🖥️ Lab Environment

| System | Role |
|---------|------|
| Windows Server 2022 | Active Directory Domain Controller |
| Windows 11 Enterprise | Domain Joined Client |
| Ubuntu Server | Splunk Enterprise SIEM |
| Kali Linux | Attack Simulation Machine |

---

# ⚙️ Technologies

- Windows Server 2022
- Windows 11 Enterprise
- Ubuntu Server
- Kali Linux
- Oracle VirtualBox
- Active Directory Domain Services
- DNS
- DHCP
- Splunk Enterprise
- Splunk Universal Forwarder
- Microsoft Sysmon
- Windows Event Logs
- PowerShell
- MITRE ATT&CK Framework

---

# 🔍 Infrastructure

- Active Directory Domain
- Organizational Units (OU)
- Domain Users
- Domain Groups
- DNS Server
- DHCP Server
- Domain-Joined Windows Client

---

# 📊 Security Monitoring

- Windows Security Event Collection
- Microsoft Sysmon Event Collection
- Windows Authentication Monitoring
- Process Creation Monitoring
- RDP Authentication Monitoring
- Windows Service Monitoring
- Remote Command Execution Monitoring
- Network Share Discovery Monitoring

---

# 🚨 Detection Use Cases

The lab includes practical detection scenarios implemented using Splunk Search Processing Language (SPL).

Current detection use cases include:

- Windows Authentication Monitoring
- Brute Force Detection
- Network Share Discovery Detection
- Remote Desktop (RDP) Logon Detection
- Windows Service Creation Detection
- Remote Command Execution Detection (Impacket PsExec)

Each detection includes:

- SPL Query
- SIEM Alert
- Dashboard
- Investigation
- MITRE ATT&CK Mapping
- Incident Report

---


# 📂 Repository Structure

```text
SOC-Home-Lab/

├── 01_Architecture
├── 02_Docs
├── 03_Screenshots
├── 04_Splunk
│   ├── Alerts
│   ├── Deshboard 
│   ├── Notes
│   ├── SPL-Queries
│   
├── 05_Detection-Rules
├── 06_MITRE-ATTACK
├── 07_Incident-Reports
└── README.md
```

---

# 💼 Skills Demonstrated

- Active Directory Administration
- Windows Server Administration
- Windows Endpoint Administration
- Splunk Enterprise Administration
- SPL Query Development
- SIEM Alert Development
- Dashboard Development
- Windows Event Log Analysis
- Microsoft Sysmon Monitoring
- Security Monitoring
- Threat Detection
- Alert Triage
- Incident Investigation
- IOC Analysis
- MITRE ATT&CK Mapping
- Blue Team Operations

---

# 🚧 Project Status

**Status:** Complete

This project demonstrates the deployment of a Windows Active Directory environment and a practical SOC workflow including centralized log collection, security monitoring, attack simulation, detection engineering, alert development, dashboard creation, incident investigation, MITRE ATT&CK mapping, and incident reporting using Splunk Enterprise.

---

# 👨‍💻 Author

**Shaikh Sufiyan**

SOC Analyst | Blue Team | Splunk | Active Directory | Windows Security

---

> This project was developed for hands-on learning, portfolio development, and demonstrating practical Security Operations Center (SOC) skills using industry-standard security technologies.
