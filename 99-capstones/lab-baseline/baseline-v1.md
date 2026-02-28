# Lab Baseline 

### Hypervisor
- **Platform:** Oracle VirtualBox 7.2.4
- **Host OS:** Windows 11

### Virtual Machines

| VM | Hostname | IP (host-only) | Role |
|---|---|---|---|
| Windows Server 2022 | LAB-DC01 | 192.168.56.30 | DC, DNS |
| Windows 11 | LAB-W1-WIN11 | 192.168.56.10 | Domain client |
| Ubuntu Server | LAB-W1-UBU-SRV | 192.168.56.20 | Linux server |

**LAB-DC01** (Windows Server 2022)
- OS: Windows Server 2022
- RAM: 6GB
- CPUs: 2
- Disk: 60GB
- Network: Intel PRO/1000 MT Desktop (NAT Network, Host-Only)
- Purpose: DC

**LAB-W1-WIN11** (Windows 11 Client)
- OS: Windows 11 (64-bit)
- RAM: 8GB
- CPUs: 2
- Disk: 80GB
- Network: Intel PRO/1000 MT Desktop (NAT Network, Host-Only)
- Purpose: Windows client operations, DNS client troubleshooting

**LAB-W1-UBU-SRV** (Ubuntu Server)
- OS: Ubuntu 22.04 Server (64-bit)
- RAM: 4GB
- CPUs: 2
- Disk: 30GB
- Network: Intel PRO/1000 MT Desktop (Host-Only)
- Purpose: Linux operations, systemd/journalctl, SSH troubleshooting

### Network Configuration (Simple)
- **Mode:** Host-only adapter (vboxnet0)
- **Subnet:** 192.168.56.0/24 (default VirtualBox host-only)
- **Gateway:** 192.168.56.1 (host)
- **DHCP:** Enabled via VirtualBox DHCP server

**Limitations of current setup:**
- No internal DHCP server (VirtualBox DHCP only)
- No routing between VLANs (not configured yet)
