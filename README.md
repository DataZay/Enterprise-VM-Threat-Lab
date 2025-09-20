# Enterprise-VM-Threat-Lab
Virtual enterprise network lab featuring Windows Server, Ubuntu endpoints, Active Directory, and a centralized Wazuh SIEM for real-time threat detection and monitoring.
---
## 🖥️ Project Overview

This lab replicates an enterprise network infrastructure featuring:

- **Active Directory Domain Controller** on Windows Server 2025  
- Multiple endpoints including Windows 11 and Ubuntu Linux  
- A centralized **Wazuh SIEM Server** on Ubuntu with Elastic Stack  
- An attacker machine using Kali Linux to simulate real-world attack techniques  
- Services such as DNS, DHCP, MailHog, and file shares to emulate typical corporate resources  

The goal is to provide hands-on experience in deploying, configuring, attacking, and defending an enterprise environment.

---

## 📁 Repository Structure

| File / Folder           | Description                                      |
|------------------------|-------------------------------------------------|
| `README.md`            | This main introduction and guide                 |
| `lab-overview.md`      | Detailed overview of the virtual lab setup       |
| `windows-server.md`    | Windows Server 2025 Domain Controller setup      |
| `windows11-victim.md`  | Windows 11 workstation configuration and logs   |
| `ubuntu-jane.md`       | Ubuntu Linux user workstation details             |
| `ubuntu-wazuh.md`      | Wazuh SIEM Server installation and configuration |
| `ubuntu-admin.md`      | Internal Ubuntu admin server setup and cron jobs |
| `kali-attacker.md`     | Kali Linux attacker machine tools and attack flow|
| `final-tests.md`       | Testing and validation steps for lab completeness|
| `optional-hardening.md`| Additional security hardening recommendations    |
| `network-diagram.drawio` | Network topology diagram (editable with draw.io) |

---

## 🚀 Getting Started

### Prerequisites

- Virtualization software (e.g., VMware, VirtualBox) to deploy VMs  
- Windows Server 2025 ISO (Preview or Final)  
- Windows 11 Enterprise ISO  
- Ubuntu 22.04 Desktop and Server ISOs  
- Kali Linux 2024.2 ISO  
- Basic familiarity with Linux and Windows administration  
- Git installed (optional, for cloning this repo)
