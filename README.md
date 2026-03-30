# 🖥️ HomeLab — HPE ProLiant ML350 Gen9

Personal infrastructure laboratory built on an 
enterprise-grade server for learning and practicing 
real-world SysAdmin & DevOps skills.

## 🔧 Hardware
- **Server:** HPE ProLiant ML350 Gen9
- **Hypervisor:** Proxmox VE 8.4
- **NAS:** WD Cloud Mirror Gen2
- **Network:** Orange Livebox (France)

## 🚀 Projects

### ✅ Plex Media Server (LXC Container)
- Debian 12 LXC container on Proxmox VE
- Plex Media Server serving media from NAS via SMB
- Static IP configuration
- [Documentation](proxmox/plex-nas/README.md)

### 🔜 Next Projects

| Priority | Category | Technology | Goal |
|---|---|---|---|
| 1 | 🐧 Linux | Docker | Containerized services deployment |
| 2 | 🏢 Enterprise | Windows Server (AD, DNS, DHCP) | Centralized identity & management |
| 3 | 🏢 Enterprise | GPO | User & device policy control |
| 4 | 🛠️ IT Support | GLPI | Ticketing & incident management |
| 5 | 📊 Monitoring | Zabbix | Infrastructure monitoring |
| 6 | 🔐 Network & Security | Pi-Hole | Network-wide ad & tracker blocking |
| 7 | 🔐 Network & Security | WireGuard | Secure remote access (VPS ↔ Homelab) |
| 8 | 🔐 Network & Security | VLAN | Network segmentation basics |
| 9 | 🐧 Linux | RHEL / AlmaLinux | Enterprise Linux environment |

## 🛠️ Stack
| Technology | Usage |
|---|---|
| Proxmox VE 8.4 | Hypervisor |
| Debian 12 | LXC Container OS |
| Plex Media Server | Media streaming |
| SMB/CIFS | NAS mount |
| Docker | Container management (soon) |
| WireGuard | VPN (soon) |

## 📌 Goals
- Build real-world infrastructure skills
- Document everything as a SysAdmin would
- Prepare for infrastructure & cloud roles
```
