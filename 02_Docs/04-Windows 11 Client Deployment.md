# Day 04 - Windows 11 Client's Deployment

## Overview

This phase focused on deploying a Windows 11 Enterprise workstation and integrating it into the Active Directory domain. The client was configured to communicate with the Domain Controller and validated as a domain-joined endpoint for the SOC lab environment.

---

## Objective

- Deploy a Windows 11 virtual machine.
- Configure network settings for domain communication.
- Join the client to the Active Directory domain.
- Validate successful domain authentication.

---

## Environment

| Component | Value |
|-----------|-------|
| Operating System | Windows 11 |
| Hostname | CLIENT1 |
| Domain | corp.local |
| Network | Internal Network |
| IP Address | 172.16.0.100 |

---

## Tasks Performed

- Created a Windows 11 virtual machine in VirtualBox.
- Installed the Windows 11 operating system.
- Configured the client to use the Internal Network.
- Verified IP configuration and DNS settings.
- Joined the client to the **corp.local** Active Directory domain.
- Restarted the system to apply domain membership.
- Successfully authenticated using a domain user account.

---

## Validation

The following checks confirmed a successful deployment:

- Windows 11 client received the expected IP configuration.
- Domain join completed successfully.
- Domain user authentication was successful.
- Communication with the Domain Controller was verified.

---

## Result

The Windows 11 workstation was successfully integrated into the Active Directory environment and is now functioning as a managed domain endpoint within the Enterprise SOC Lab.

---

## Skills Demonstrated

- Windows 11 Deployment
- Active Directory Domain Join
- Windows Network Configuration
- Domain Authentication
- Enterprise Endpoint Configuration
