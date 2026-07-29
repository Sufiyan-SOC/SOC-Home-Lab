#SOC Home Lab Architecture

## Purpose

The SOC Home Lab is designed to simulate a real-world enterprise environment for Security Operations Center (SOC) operations. The lab provides hands-on experience in Windows infrastructure administration, centralized log management, attack simulation, security monitoring, threat hunting, detection engineering, and incident investigation using enterprise security tools.

The objective is to understand how security events are generated, collected, analyzed, detected, and investigated across an Active Directory environment.

---

# Environment

The lab consists of four interconnected systems that simulate a small enterprise network.

| System | Role |
|---------|------|
| Windows Server 2022 | Active Directory Domain Controller, DNS, DHCP |
| Windows 11 Enterprise | Domain Joined Workstation |
| Ubuntu Server | Splunk Enterprise SIEM |
| Kali Linux | Attack Simulation Machine |

---

# Core Components

## Windows Server 2022 (DC01)

### Services

- Active Directory Domain Services (AD DS)
- DNS Server
- DHCP Server

### Network

- NAT Network
- Internal Network

### Responsibilities

- Domain authentication
- User and Group Management
- DNS Resolution
- IP Address Distribution
- Group Policy Management

---

## Windows 11  (CLIENT1)

### Role

- Domain Joined Endpoint
- Enterprise Workstation
- Security Event Source

### Network

- Internal Network

### Responsibilities

- Generates Windows Security Events
- Generates Sysmon Events
- Sends logs to Splunk through Universal Forwarder

---

## Ubuntu Server

### Role

Splunk Enterprise SIEM

### Network

- NAT Network
- Internal Network
- Host-Only Adapter

### Responsibilities

- Centralized Log Collection
- Log Indexing
- SPL Searching
- Dashboard Visualization
- Security Monitoring
- Alert Development

---

## Kali Linux

### Role

Attack Simulation Machine

### Network

- NAT Network
- Internal Network

### Responsibilities

- Enumeration
- Authentication Testing
- SMB Testing
- Network Scanning
- Attack Simulation
- Security Validation

---

# Enterprise Network Flow

Internet

↓

VirtualBox NAT

↓

Windows Server (DC01)

↓

 Internal Network

↓

Windows Client • Ubuntu Server • Kali Linux

---

# Security Monitoring Workflow

Windows Endpoint

↓

Windows Event Logs

+

Sysmon Logs

↓

Splunk Universal Forwarder

↓

Splunk Enterprise

↓

Log Indexing

↓

SPL Queries

↓

Dashboards

↓

Alerts

↓

Threat Hunting

↓

Incident Investigation

↓

MITRE ATT&CK Mapping

↓

Incident Report

---

# Security Use Cases

The lab is designed to simulate enterprise SOC use cases, including:

- User Authentication Monitoring
- Failed Logon Detection
- SMB Authentication Monitoring
- Brute Force Detection
- Network Enumeration Detection
- Process Creation Monitoring
- Network Connection Monitoring
- Windows Security Event Analysis
- Threat Hunting using SPL
- Incident Documentation

---

# Data Sources

The current lab collects logs from:

- Windows Security Logs
- Microsoft Sysmon
- Windows System Logs
- Windows Application Logs

---

# Architecture Highlights

- Active Directory Infrastructure
- Centralized Log Collection using Splunk Enterprise
- Domain Joined Windows Endpoint
- DNS & DHCP Services
- Sysmon Enhanced Logging
- Splunk Universal Forwarder
- Enterprise Attack Simulation
- Detection Engineering
- Threat Hunting
- Incident Investigation
- MITRE ATT&CK Mapping
- Security Documentation

---

# Skills Demonstrated

- Active Directory Administration
- Windows Server Administration
- Windows Endpoint Monitoring
- Network Architecture
- Log Management
- SIEM Operations
- SPL Query Development
- Detection Engineering
- Threat Hunting
- Incident Investigation
- MITRE ATT&CK Mapping
- Security Documentation
