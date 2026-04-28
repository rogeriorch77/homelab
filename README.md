# 🖥️ HomeLab — HPE ProLiant ML350 Gen9

Personal infrastructure laboratory built on an 
enterprise-grade server for learning and practicing 
real-world SysAdmin & DevOps skills.

## 🔧 Hardware
- **Server:** HPE ProLiant ML350 Gen9
- **Hypervisor:** Proxmox VE 8.4
- **NAS:** WD Cloud Mirror Gen2
- **Network:** Orange Livebox

## 🚀 Projects

### ✅ Plex Media Server (LXC Container)
- Debian 12 LXC container on Proxmox VE
- Plex Media Server serving media from NAS via SMB
- Static IP configuration
- [Documentation](proxmox/plex-nas/README.md)

### ✅ Proxmox VE — Hypervisor Setup
- HPE ProLiant ML350 Gen9 running Proxmox VE 8.4
- LXC containers (Debian 12), VM management
- NAS integration via SMB/CIFS (persistent mount via fstab)
- Backup strategy with VZDump to NAS storage
- Kernel & system updates (no-subscription repository)

---

### 🔜 Next Projects

## 📱 Group 1: IT Support N1/N2/N3

| Priority | Category | Technology | Goal |
|---|---|---|---|
| 1 | 🛠️ IT Support | GLPI | Ticketing & incident management - N1/N2 |
| 2 | 🏢 Enterprise | Windows Server (AD - basics) | User/computer management, password resets - N1/N2 |
| 3 | 🏢 Enterprise | GPO | User & device policy control, drive mapping - N2 |
| 4 | 🏢 Enterprise | DNS & DHCP (troubleshooting) | Diagnose network connectivity issues - N2 |
| 5 | 🏢 Enterprise | Microsoft 365 | Mailbox, Teams, license management - N1/N2 |
| 6 | 🔐 Network & Security | VPN Client Support | Configure remote access for users - N2 |
| 7 | 🛠️ IT Support | Remote Support Tools | RDP, TeamViewer troubleshooting - N1 |
| 8 | 🛠️ IT Support | Windows 10/11 Support | OS troubleshooting, updates, drivers - N1/N2 |
| 9 | 🛠️ IT Support | Printer Management | Network printer setup & troubleshooting - N1/N2 |
| 10 | 🛠️ IT Support | Hardware Support | Desktop/laptop component diagnostics - N1/N2 |

---

## 🏗️ Group 2: SysAdmin Jr (Infrastructure)

| Priority | Category | Technology | Goal |
|---|---|---|---|
| 1 | 🐧 Linux | RHEL / AlmaLinux | Enterprise Linux server administration - Jr |
| 2 | 🐧 Linux | Docker | Containerized services deployment - Jr |
| 3 | 🏢 Enterprise | Windows Server (AD - advanced) | Domain design, FSMO roles, replication - Jr/Intermediate |
| 4 | 🏢 Enterprise | DNS & DHCP (server setup) | Zone management, high availability - Jr |
| 5 | 📊 Monitoring | Zabbix | Infrastructure monitoring & alerting - Jr |
| 6 | 🔐 Network & Security | VLAN | Network segmentation (users, servers, IoT) - Jr |
| 7 | 🔐 Network & Security | pfSense/OPNsense | Firewall, NAT, VPN, traffic filtering - Jr/Intermediate |
| 8 | 🔐 Network & Security | WireGuard | Secure site-to-site VPN (VPS ↔ Homelab) - Jr |
| 9 | 🔐 Network & Security | Pi-Hole | Network-wide ad & tracker blocking - Jr |
| 10 | 🛠️ Automation | Bash / Ansible | Script automation & configuration management - Jr/Intermediate |
| 11 | 💾 Backup & DR | Veeam / Proxmox Backup Server | VM backup & disaster recovery - Jr |
| 12 | 🌐 Web Services | Nginx / Apache | Reverse proxy, SSL/TLS, web hosting - Jr |
| 13 | 💾 Storage | NFS / iSCSI | Shared storage for VMs and users - Intermediate |

---

## 🛠️ Stack
| Technology | Usage |
|---|---|
| Proxmox VE 8.4 | Hypervisor |
| Debian 12 | LXC Container OS |
| Plex Media Server | Media streaming |
| SMB/CIFS | NAS mount (persistent) |
| Docker | Container management (soon) |
| WireGuard | VPN (soon) |

## 📌 Goals
- Build real-world infrastructure skills
- Document everything as a SysAdmin would
- Prepare for IT Support N1/N2/N3 roles in France
- Transition to Junior SysAdmin# 🖥️ HomeLab — HPE ProLiant ML350 Gen9
