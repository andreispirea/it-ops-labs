# Lab Baseline v1.0

## Current Setup (Week 1)

### Hypervisor
- **Platform:** Oracle VirtualBox 7.2.4
- **Host OS:** Windows 11

### Virtual Machines

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
- No internal DNS server (relies on host DNS)
- No internal DHCP server (VirtualBox DHCP only)
- No routing between VLANs (not configured yet)
- No AD domain

**What this supports:**
- Windows client troubleshooting (DNS cache, network config)
- Linux service/log troubleshooting
- Basic networking (connectivity, gateway, DNS client issues)
