├── lab-overview.md

# 🖥️ Virtual Machine Setup Overview

This lab simulates a realistic enterprise network environment using multiple virtual machines across both Windows and Ubuntu platforms. The goal is to replicate common IT infrastructure services (like AD, DNS, DHCP) while integrating **Wazuh SIEM** to monitor, detect, and respond to attack simulations. The lab supports log ingestion, alerting, and Blue Team skill development through practical Red Team attack tests.

---

## 💻 Virtual Machines

| VM Name               | Operating System       | Role                     | Tools & Services                           | IP Address     |
|----------------------|------------------------|--------------------------|---------------------------------------------|----------------|
| **Windows Server**    | Windows Server 2025    | Domain Controller         | Active Directory, DNS, DHCP                 | `10.0.0.5`     |
| **Windows 11 (John)** | Windows 11 Enterprise  | Domain User Workstation   | Winlog, Event Viewer                        | `10.0.0.100`   |
| **Ubuntu (Jane)**     | Ubuntu 22.04 Desktop   | Domain-Joined Linux Host  | Wazuh Agent, Auditd                         | `10.0.0.101`   |
| **Kali Linux**        | Kali Linux 2024.2      | Attacker Machine          | Nmap, Hydra, Netcat                         | `10.0.0.103`   |
| **Ubuntu (Wazuh)**    | Ubuntu 22.04 Server    | Wazuh SIEM Server         | Wazuh Manager, Wazuh Dashboard, Elastic     | `10.0.0.10`    |
| **Ubuntu (Admin)**    | Ubuntu 22.04 Server    | Internal Corp Server      | MailHog, Cron Jobs, File Share              | `10.0.0.8`     |

---


## 🧰 VM Resource Specs

| VM Name               | vCPUs | RAM (MB) | Storage |
|-----------------------|-------|----------|---------|
| Windows Server 2025   | 2     | 4096     | 50 GB   |
| Windows 11 (John)     | 2     | 4096     | 80 GB   |
| Ubuntu (Jane)         | 1     | 2048     | 80 GB   |
| Ubuntu (Admin Server) | 2     | 4096     | 80 GB   |
| Ubuntu (Wazuh Server) | 2     | 4096     | 80 GB   |
| Kali Linux            | 1     | 2048     | 55 GB   |

---

## 🔧 Roles & Responsibilities

- **Windows Server 2025**
  - Hosts `corp.local` domain with integrated **AD, DNS, and DHCP**
  - Issues IP leases and manages name resolution internally

- **Windows 11 (John Doe)**
  - Joined to domain
  - Simulates a typical employee workstation for log analysis

- **Ubuntu Desktop (Jane Doe)**
  - Domain-joined Linux user endpoint
  - Monitored via **Wazuh Agent + Auditd**
  - Target for lateral movement simulation

- **Ubuntu (Admin Server)**
  - Internal tools, cron jobs, and mock corporate services
  - Can be used to simulate internal escalation and service abuse

- **Kali Linux**
  - Used to simulate real-world attacker behavior:
    - Reconnaissance (Nmap)
    - Brute-force (Hydra)
    - Reverse shell creation (Netcat)

- **Ubuntu (Wazuh Server)**
  - Hosts Wazuh SIEM, Elastic Stack, and Dashboard
  - Centralized log collector and alerting platform

---

## 📦 Security Monitoring Stack

- **SIEM**: [Wazuh](https://wazuh.com/)
- **Log Sources**:
  - Wazuh Agents (Ubuntu + Windows + Windows Server)
  - Auditd (Linux syscall monitoring)
  - Winlog (Windows event logs)
- **Detection Capabilities**:
  - Network scanning (e.g. Nmap)
  - Brute-force detection (e.g. Hydra)
  - Unauthorized logins (e.g. ssh)
  - Reverse shell execution (e.g. nc)
  - Suspicious process activity (e.g. wazuh monitoring

---

## 🔄 Log & Alert Flow

Endpoints (Windows, Ubuntu)
↓
Wazuh Agent
↓
Wazuh Manager @ 10.0.0.10
↓
Elasticsearch Stack
↓
Wazuh Dashboard (Kibana-based)
↓
Real-time Alerting & Visualization

---

## 🎯 Goals of the Lab

1. Build realistic enterprise environment with Windows + Linux endpoints
2. Deploy Active Directory, DNS, and DHCP from a central controller
3. Configure SIEM using Wazuh for cross-platform detection
4. Simulate attacks from Kali and verify alert generation
5. Practice Blue Team workflows: detection, triage, alert tuning
6. Showcase project publicly via GitHub for portfolio/recruiters
