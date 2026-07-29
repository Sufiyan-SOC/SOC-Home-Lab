# Day 01 – SOC Home Lab Planning & Environment Design

## Objective

The objective of Day 01 was to design the overall architecture of an Enterprise Security Operations Center (SOC) Home Lab before deployment.

A structured plan was created to simulate a real-world enterprise environment capable of supporting centralized logging, endpoint monitoring, detection engineering, threat investigation, and incident response.

---

# Project Scope

This project aims to build an Enterprise SOC Home Lab that replicates a typical Blue Team environment used by SOC analysts.

The lab is designed to provide hands-on experience with enterprise infrastructure, Windows administration, SIEM deployment, security monitoring, and attack detection.

---

# Planned Infrastructure

The lab environment consists of the following systems:

| System | Role |
|----------|------------------------------|
| Windows Server 2022 | Active Directory, DNS, DHCP |
| Windows 11 Enterprise | Domain-Joined Endpoint |
| Ubuntu Server | Splunk Enterprise Server |
| Kali Linux | Attack Simulation Workstation |

---

# Initial Lab Architecture

```text
                     SOC Lab

                     Internet
                        │
                       NAT
                        │
         Windows Server 2022 (DC01)
           AD DS • DNS • DHCP
                        │
──────────────── Internal Network ────────────────
        │                    │                  │
        │                    │                  │
 Windows 11            Ubuntu Server        Kali Linux
  CLIENT1            Splunk Enterprise     Attack Machine
        │
 Splunk Universal Forwarder

Ubuntu Server
        │
 Host-Only Adapter
        │
 Host Browser
 Splunk Web Interface
```

---

# Environment Planning

The following components were planned before deployment:

- Enterprise network topology
- Virtual machine resource allocation
- Network segmentation
- IP addressing scheme
- Operating system selection
- Log collection architecture
- Centralized monitoring design

---

# Technologies Selected

| Technology | Purpose |
|------------|-------------------------------------------|
| Oracle VirtualBox | Virtualization Platform |
| Windows Server 2022 | Enterprise Infrastructure |
| Windows 11 Enterprise | Endpoint Monitoring |
| Ubuntu Server | Splunk Enterprise Deployment |
| Splunk Enterprise | Security Monitoring & Log Analysis |
| Splunk Universal Forwarder | Endpoint Log Collection |
| Microsoft Sysmon | Advanced Windows Telemetry |

---

# Expected SOC Workflow

Attack Simulation

↓

Windows Event Generation

↓

Sysmon Telemetry

↓

Splunk Universal Forwarder

↓

Splunk Enterprise

↓

Detection Engineering

↓

SIEM Alerts

↓

Investigation

↓

Incident Reporting

---

# Skills Demonstrated

- Enterprise SOC Architecture Design
- Virtualization Planning
- Windows Infrastructure Planning
- Network Segmentation
- Log Collection Design
- SIEM Architecture Planning

---

# Deliverables

- Enterprise SOC architecture designed
- Virtualization environment planned
- Infrastructure components identified
- Network topology finalized
- Deployment roadmap prepared

---

# Outcome

Day 01 established the architectural foundation for the Enterprise SOC Lab.

The completed design provides a scalable environment for implementing Active Directory, Windows endpoints, centralized log collection, SIEM monitoring, attack simulation, detection engineering, and incident investigation throughout the remaining phases of the project.
