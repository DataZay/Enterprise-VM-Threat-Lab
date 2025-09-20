# 📂 windows11-victim.md  

### 🧍‍♂️ Windows 11 (John Doe) Workstation

```markdown
# 🧍‍♂️ Windows 11 – John Doe (Domain Workstation)

## 🔧 VM Specs
- **OS**: Windows 11 Enterprise
- **Hostname**: `WIN11-JOHN`
- **IP Address**: `10.0.0.100`
- **vCPU**: 2
- **RAM**: 4096 MB
- **Storage**: 80 GB

## 🔗 Domain Join
- DNS set to `10.0.0.5`
- Joined to `corp-local.com`
- Domain User: `corp\johnd`

## 🧰 Tools Installed
- **Winlogbeat**
- **Event Viewer**
- Remote Server Admin Tools (RSAT, optional)

## 🔍 Wazuh Agent Configuration
- Installed Wazuh Agent for Windows
- Configured to connect to `10.0.0.10`
- Monitored:
  - Security logs
  - System logs
  - Application logs

## 📈 Example Events Captured
- Login Success/Failure (4624, 4625)
- UAC events
- Software installations
- Reverse shell via PowerShell detected by Wazuh
