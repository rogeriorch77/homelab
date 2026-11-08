# HomeLab — Infrastructure & Virtualization

**Proxmox VE · Linux · Networking · Security · Storage · Self-Hosting**

A personal infrastructure laboratory built around an **HPE ProLiant ML350 Gen9**, designed to deploy, manage, troubleshoot and improve real-world IT infrastructure.

The environment combines virtualization, network security, Linux and Windows administration, storage, backup and self-hosted services.

This repository documents the existing infrastructure, technical implementations and future architectural improvements.

---

## 1. Infrastructure Overview

| Component | Technology | Status |
|---|---|---|
| Physical server | HPE ProLiant ML350 Gen9 | Deployed |
| Hypervisor | Proxmox VE 8.4 | Deployed |
| Firewall | OPNsense virtual machine | Deployed |
| Secure remote access | WireGuard | Deployed |
| Network storage | WD My Cloud Mirror Gen2 | Deployed |
| Virtualized storage | TrueNAS | Deployed — under review |
| Hardware management | HPE iLO 4 | Available |
| Physical firewall appliance | Dedicated x86 hardware | Planned |
| Independent OOB management | Raspberry Pi / mini-PC | Planned |
| Backup infrastructure | Independent backup system | Planned improvement |

**Status definitions**

- **Deployed:** installed and previously verified.
- **Under review:** existing component requiring additional validation.
- **Planned:** not yet implemented.

Current service availability is not implied by historical deployment status.

## 2. Physical Hardware & Storage

### HPE ProLiant ML350 Gen9

| Resource | Configuration |
|---|---|
| Processor | Intel Xeon E5-2620 v4 |
| CPU | 8 cores / 16 threads |
| Memory | 96 GB RAM installed |
| Hypervisor | Proxmox VE |
| Protected storage | Approximately 300 GB mirrored |
| Experimental storage | Approximately 900 GB non-mirrored |
| Hardware management | HPE iLO 4 |

### Storage Strategy

**Mirrored storage — priority workloads**

Intended for Proxmox and virtual machines with persistent configurations and important operational data.

**Non-mirrored storage — development and testing**

Intended for experimental VMs, operating system testing, temporary environments and disposable workloads.

The final allocation of virtual disks is pending verification.

RAID is not a replacement for backups.

## 3. Networking & Security

The current infrastructure uses **OPNsense** and **WireGuard** for network security and remote access.

Technical areas include:

- Firewall and traffic filtering
- Secure VPN connectivity
- VLAN-based network segmentation
- Network troubleshooting
- Linux and Windows connectivity
- Hardware-level management through iLO

### Planned Improvements

The current firewall is virtualized on the Proxmox host.

A future dedicated x86 appliance will host OPNsense independently, reducing the infrastructure's dependency on a single physical server.

An additional out-of-band (OOB) management path is planned to provide emergency access to the HPE iLO interface.

Sensitive network configurations are intentionally excluded from public documentation.

## 4. Virtualization & Services

The laboratory includes different categories of virtual machines and Linux containers.

| Category | Technologies |
|---|---|
| Network security | OPNsense, WireGuard |
| Linux administration | Debian and other Linux environments |
| Windows administration | Windows Server, Active Directory |
| IT service management | GLPI |
| Credential management | Vaultwarden |
| Storage | TrueNAS, SMB/CIFS, NAS |
| Media streaming | Jellyfin, Plex |
| Development | Isolated application and database environments |

Not every deployed service is considered production-critical. Service dependencies and recovery procedures are being reviewed.

## 5. Media Services — Jellyfin & Plex

Two self-hosted media solutions have been deployed as Linux containers.

### Jellyfin — Preferred Platform

**Status:** Deployed; migration validation pending.

Jellyfin is the preferred platform for the future media environment.

The implementation includes:

- Linux container deployment
- Web-based media management
- NAS integration
- Media library organization
- Playback and client compatibility testing

Final validation of playback, storage access, backups and automatic startup is pending.

### Plex — Legacy / Fallback

**Status:** Previously operational; retained during transition.

Plex was initially deployed using a Debian LXC container integrated with network storage.

It remains documented as an earlier implementation and a fallback while Jellyfin is being validated.

[Read Plex deployment documentation](proxmox/plex-nas/README.md)

**Migration objective:** complete Jellyfin validation before considering Plex retirement.

## 6. Backup & Recovery

The infrastructure uses network storage and Proxmox backup mechanisms.

The recovery strategy is being reviewed to improve protection against:

- Virtual machine failure
- Disk failure
- Hypervisor failure
- Accidental deletion
- Complete physical server loss

### Planned Improvements

- Independent Proxmox backup infrastructure
- Backup integrity verification
- Documented restoration testing
- Encrypted off-site backup copies
- Emergency recovery procedures

The objective is to make important services recoverable without depending entirely on the HPE server.

## 7. Infrastructure Roadmap

| Phase | Improvement | Status |
|---|---|---|
| 01 | Current infrastructure audit | In progress |
| 02 | Jellyfin migration validation | In progress |
| 03 | Independent OOB management | Planned |
| 04 | Dedicated physical OPNsense firewall | Planned |
| 05 | Independent backup and recovery | Planned |
| 06 | Critical service separation | Planned |
| 07 | Rackmount server migration | Long-term |
| 08 | Dedicated 42U HomeLab rack | Long-term |

### Future Architecture

**EDGE** — Physical firewall, network gateway and VPN.

**OOB** — Independent emergency hardware management.

**PVE** — Virtualization, applications and experimental workloads.

**BACKUP** — Independent storage and disaster recovery.

The future design may include multiple racks for production, networking and backup infrastructure.

These are architectural objectives, not completed deployments.

## 8. Repository Documentation

- [Plex LXC + NAS Integration](proxmox/plex-nas/README.md)
- Jellyfin deployment — documentation planned
- Hardware and storage — documentation planned
- Network architecture — documentation planned
- Backup and disaster recovery — documentation planned
- Infrastructure roadmap — documentation planned

Documentation is added as implementations are validated.

## 9. Security & Documentation Policy

This public repository focuses on infrastructure engineering, implementation and technical learning.

The following information is intentionally excluded:

- Credentials, tokens and private keys
- Internal IP addressing and sensitive topology details
- Production firewall rules and VPN configuration
- Private application source code
- Sensitive recovery procedures
- Private business and product documentation

---

**Build · Deploy · Test · Troubleshoot · Document · Improve**
