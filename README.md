# IT Operations Lab & Portfolio

**Hands-on IT Operations documentation** — break/fix scenarios, troubleshooting cases, runbooks, and operational procedures built through structured lab work.

**Goal:** Demonstrate production-ready IT Ops skills for NOC / Infrastructure Support / Junior SysAdmin roles.

---

## 📋 What's Inside

This repository contains documented evidence of operational competence across:

- **Windows Operations** — Client & Server troubleshooting, services, networking, Event Viewer, permissions
- **Linux Operations** — systemd, journalctl, permissions, SSH, disk management, service troubleshooting
- **Networking** — TCP/IP, DNS, DHCP, VLANs, routing, ACLs, packet analysis
- **Identity & Access Management** — Active Directory, group-based access, JML workflows, SSO concepts
- **Automation** — PowerShell & Bash scripts for operational tasks
- **MDM & Compliance** — Device policies, access control evidence, change management

**Evidence standard:** Every case includes command outputs, logs, screenshots, verification steps, and prevention measures.

---

## 🎯 Best Work (Start Here)

**Top Cases:**
- *[Will be added as cases are completed]*

**Capstone Incidents:**
- *[Capstone 1: VPN users can't access internal app — Coming soon]*
- *[Capstone 2: New hire onboarded but no access — Coming soon]*

**Most Useful Runbooks:**
- *[Will be added as runbooks are created]*

**Automation Scripts:**
- *[Will be added as scripts are created]*

---

## 📂 Repository Structure

```
it-ops-labs/
│
├── 00-templates/              # Professional documentation templates
│   ├── TICKET_TEMPLATE.md
│   ├── RUNBOOK_TEMPLATE.md
│   ├── POSTMORTEM_TEMPLATE.md
│   └── LAB_WRITEUP_TEMPLATE.md
│
├── 01-windows/                # Windows Operations
│   ├── cases/                 # Break/fix scenarios
│   ├── labs/                  # Learning labs
│   ├── runbooks/              # Standard procedures
│   ├── artifacts/             # Screenshots, logs, configs
│   └── README.md
│
├── 02-linux/                  # Linux Operations
│   ├── cases/
│   ├── labs/
│   ├── runbooks/
│   ├── artifacts/
│   └── README.md
│
├── 03-networking/             # Networking & Infrastructure
│   ├── cases/
│   ├── labs/
│   ├── runbooks/
│   ├── artifacts/
│   └── README.md
│
├── 04-identity-access/        # IAM & Directory Services
│   ├── cases/
│   ├── labs/
│   ├── runbooks/
│   ├── artifacts/
│   └── README.md
│
├── 05-automation/             # Scripts & Automation
│   ├── scripts/               # PowerShell, Bash, Python
│   ├── runbooks/
│   └── README.md
│
├── 06-mdm-compliance/         # Device Management & Compliance
│   ├── policies/
│   ├── compliance/
│   ├── change-management/
│   └── README.md
│
└── 99-capstones/              # Complex Multi-Failure Scenarios
    ├── lab-baseline/          # Lab environment documentation
    ├── operator-method.md     # Troubleshooting methodology
    ├── capstone-001-vpn/
    └── capstone-002-jml/
```

---

## 🛠️ Lab Environment

**Current setup:**
- **Hypervisor:** [VirtualBox / VMware / Hyper-V]
- **Systems:**
  - Windows 11 VM (client operations)
  - Windows Server 2022 VM (AD DS, DNS, DHCP, file services)
  - Ubuntu 22.04 Server VM (Linux operations)
  - [Router/Firewall VM if applicable]

**Network:**
- Internal network for isolated testing
- Multi-VLAN setup for networking labs

*Detailed topology: See `/99-capstones/lab-baseline/`*

---

## 📖 Documentation Standards

Every case follows professional IT Operations documentation practices:

### Case Documentation (Tickets)
- **Symptom description** with exact error messages
- **Hypothesis-driven troubleshooting** (what I tested and why)
- **Root cause** with evidence (logs, configs, command outputs)
- **Resolution steps** with verification
- **Prevention measures** (monitoring, runbooks, config changes)

### Runbooks
- **Repeatable procedures** for common operations
- **Prerequisites** and risk assessment
- **Step-by-step instructions** with expected outputs
- **Verification tests** and rollback procedures
- **Escalation criteria** when stuck

### Postmortems
- **Timeline** of incident detection → investigation → resolution
- **Impact analysis** (users, systems, business)
- **Root cause analysis** with contributing factors
- **Action items** with owners and deadlines (prevent, detect, improve)
- **Lessons learned** (technical and process)

---

## 🎓 Skills Demonstrated

### Windows
- Event Viewer log analysis and filtering
- Service management, dependencies, recovery actions
- DNS client troubleshooting (cache, resolution, server config)
- DHCP client issues (APIPA, lease problems, wrong options)
- Windows Firewall rule creation and testing
- Performance troubleshooting (Task Manager, Resource Monitor)
- VPN client connectivity (routes, DNS, split tunnel)

### Linux
- systemd service management (status, logs, enable/disable)
- journalctl log analysis and filtering
- User/group management and permissions (chmod, chown, sudo)
- SSH troubleshooting (keys, permissions, auth logs)
- Network configuration (ip, ss, route tables)
- Disk usage triage (df, du, log rotation)
- DNS resolution troubleshooting (systemd-resolved, /etc/resolv.conf)

### Networking
- TCP/IP fundamentals and subnetting
- DNS/DHCP failure pattern recognition
- VLAN configuration and trunk troubleshooting
- Routing table analysis and gateway issues
- ACL testing and verification
- Packet capture analysis (Wireshark)
- Network address translation (NAT) concepts

### Identity & Access
- Active Directory basics (users, groups, OUs)
- Group-based access control (least privilege)
- NTFS and share permissions
- JML workflows (Joiner/Mover/Leaver)
- Password reset and account lockout handling
- SSO/SAML/OIDC concepts
- Entra ID (Azure AD) fundamentals

### Automation
- PowerShell scripting (system info, log parsing, service checks)
- Bash scripting (health checks, monitoring helpers)
- Task scheduling (Windows Task Scheduler, Linux cron)
- Git version control basics
- Script documentation and error handling

---

## 🔍 Troubleshooting Methodology

**My approach to operational issues:**

1. **Gather symptoms** — What broke? When? Who's affected? Error messages?
2. **Form hypotheses** — What could cause this? Layer by layer (network → OS → service → app)
3. **Test systematically** — Isolate variables, rule out causes, document results
4. **Identify root cause** — What actually failed? Why did it fail? Evidence?
5. **Apply fix** — Minimal change, test in isolation if possible
6. **Verify resolution** — Does it work? Can users confirm? Monitoring healthy?
7. **Prevent recurrence** — Monitoring alert? Runbook? Config standard? Documentation?
8. **Document thoroughly** — Timeline, evidence, lessons learned

*Full methodology: See `/99-capstones/operator-method.md`*

---

## 📊 Progress Tracking

**Skill Matrix** (0 = unknown, 1 = can follow guide, 2 = can solve alone, 3 = can teach/write runbook)

### Windows Operations
| Skill | Level | Evidence |
|-------|-------|----------|
| DNS troubleshooting | 0→? | *In progress* |
| DHCP client issues | 0→? | *Planned* |
| Service dependencies | 0→? | *Planned* |
| Event Viewer analysis | 0→? | *Planned* |
| Firewall rule management | 0→? | *Planned* |
| VPN troubleshooting | 0→? | *Planned* |

### Linux Operations
| Skill | Level | Evidence |
|-------|-------|----------|
| systemd service mgmt | 0→? | *In progress* |
| journalctl log analysis | 0→? | *Planned* |
| SSH troubleshooting | 0→? | *Planned* |
| Permissions management | 0→? | *Planned* |
| Network configuration | 0→? | *Planned* |

### Networking
| Skill | Level | Evidence |
|-------|-------|----------|
| DNS/DHCP troubleshooting | 0→? | *Planned* |
| VLAN configuration | 0→? | *Planned* |
| Routing troubleshooting | 0→? | *Planned* |
| Packet capture analysis | 0→? | *Planned* |

*Full skill matrix updated as cases are completed*

---

## 📈 Case Statistics

- **Total cases documented:** 0
- **Windows cases:** 0
- **Linux cases:** 0
- **Network cases:** 0
- **IAM cases:** 0
- **Runbooks created:** 0
- **Postmortems written:** 0
- **Scripts developed:** 0

*Updated: [Current Date]*

---

## 🚀 How to Navigate This Repo

**If you're a hiring manager:**
1. Start with **Best Work** section above (top cases and capstones)
2. Review a **postmortem** to see root cause analysis skills
3. Check a **runbook** to see documentation quality
4. Look at **automation scripts** to see scripting ability

**If you're learning IT Ops:**
1. Review the **templates** in `/00-templates/` for documentation standards
2. Read the **troubleshooting methodology** in `/99-capstones/operator-method.md`
3. Follow cases chronologically within each module (case-001, case-002, etc.)
4. See how tickets → runbooks (when patterns emerge)

---

## 🔗 Related Links

- **Lab Documentation:** See `/99-capstones/lab-baseline/` for environment details
- **Templates:** All cases use professional templates from `/00-templates/`
- **Methodology:** Troubleshooting approach documented in `/99-capstones/operator-method.md`

---

## 📝 Documentation Philosophy

**Why I document this way:**

In real IT Operations work, documentation isn't optional—it's how you:
- Hand off incidents during shift changes
- Train new team members
- Prevent repeated failures
- Prove compliance during audits
- Build institutional knowledge

This portfolio demonstrates **operational maturity**: not just "I can fix things" but "I can fix things in a way that prevents recurrence, helps others, and leaves the organization better than I found it."

Every case includes:
- ✅ Evidence (screenshots, logs, command outputs)
- ✅ Verification (proof the fix worked)
- ✅ Prevention (runbook, monitoring, or process improvement)

---

## 📬 Contact

*[Your contact information or LinkedIn if you want to include it]*

---

## 📄 License

This repository is for educational and portfolio purposes.

---

**Last Updated:** [Date]  
**Status:** 🚧 Active development — cases being added weekly
