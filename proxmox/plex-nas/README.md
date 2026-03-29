# 🎬 Plex Media Server — LXC Container on Proxmox VE

## 📋 Overview
Deployment of Plex Media Server inside a Debian 12 
LXC container on Proxmox VE 8.4, serving media 
from a WD Cloud Mirror NAS via SMB/CIFS.

## 🔧 Infrastructure
| Component | Details |
|---|---|
| **Host** | HPE ProLiant ML350 Gen9 |
| **Hypervisor** | Proxmox VE 8.4 |
| **Container** | LXC CT 100 — plex-ct |
| **OS** | Debian 12 (standard) |
| **NAS** | WD Cloud Mirror Gen2 |
| **IP** | 192.168.1.X/24 |

## ⚙️ Container Resources
| Resource | Value |
|---|---|
| **CPU** | 2 cores |
| **RAM** | 2048 MB |
| **Swap** | 512 MB |
| **Disk** | 8 GB (local-lvm) |

## 📦 Installation Steps

### 1. Download Debian 12 Template
```bash
pveam update
pveam download local debian-12-standard_12.12-1_amd64.tar.zst
```

### 2. Create LXC Container
- CT ID: 100
- Hostname: plex-ct
- Template: Debian 12
- Unprivileged: Yes
- Nesting: Enabled

### 3. Install Plex Media Server
```bash
apt-get update && apt-get upgrade -y
curl https://downloads.plex.tv/plex-keys/PlexSign.key | gpg --dearmor -o /usr/share/keyrings/plex.gpg
echo "deb [signed-by=/usr/share/keyrings/plex.gpg] https://downloads.plex.tv/repo/deb public main" > /etc/apt/sources.list.d/plexmediaserver.list
apt-get update
apt-get install plexmediaserver -y
```

### 4. Mount NAS via SMB
```bash
# On Proxmox host (srv01)
nano /root/.smb_credentials
# Add: username=admin / password=yourpassword
chmod 600 /root/.smb_credentials
mkdir -p /mnt/nas/movies
mount -t cifs //NAS_IP/Movies /mnt/nas/movies -o credentials=/root/.smb_credentials,vers=2.0
```

### 5. Pass NAS mount to CT
```bash
# Add to /etc/pve/lxc/100.conf
mp0: /mnt/nas/movies,mp=/mnt/nas/movies
```

### 6. Verify Plex Service
```bash
systemctl status plexmediaserver
```

## ✅ Result
- Plex Media Server accessible at `http://192.168.1.X:32400/web`
- Media served from NAS to TV via Plex app
- Laptop no longer needed as media server!

## 🔗 References
- [Proxmox VE Documentation](https://pve.proxmox.com/wiki/Main_Page)
- [Plex Media Server](https://www.plex.tv)
```