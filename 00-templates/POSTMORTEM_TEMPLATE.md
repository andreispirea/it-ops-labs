# Postmortem: [INCIDENT_TITLE]

## Document Information
| Field | Value |
|-------|-------|
| **Incident ID** | INC-YYYY-MM-DD-XXX |
| **Date of Incident** | YYYY-MM-DD |
| **Date of Postmortem** | YYYY-MM-DD |
| **Author(s)** | [Your Name] |
| **Reviewers** | [Name or "Self-review"] |
| **Severity** | SEV-1 (Critical) / SEV-2 (High) / SEV-3 (Medium) |
| **Status** | Draft / Under Review / Final |

---

## Executive Summary

**What happened (one paragraph):**
[Brief description: what broke, when, impact, how long, resolution]

Example: "On 2024-01-15 between 14:30-16:45 UTC, VPN users were unable to access internal applications. Approximately 45 remote workers lost access to email, file shares, and internal web apps. The root cause was a misconfigured DNS push policy on the VPN server combined with a missing firewall rule. The incident was resolved by correcting the DNS configuration and adding the required firewall rule. Total downtime: 2 hours 15 minutes."

**Impact:**
- **Users affected:** [number] users / [specific team or all users]
- **Systems affected:** [list key systems]
- **Business impact:** [lost productivity / blocked critical function / customer-facing]
- **Duration:** [X hours Y minutes total downtime]

**Root cause (one sentence):**
[Technical root cause]

**Resolution (one sentence):**
[What fixed it]

---

## Timeline

**All times in [specify timezone: UTC / local]**

| Time | Event | Type |
|------|-------|------|
| HH:MM | [What happened] | Detection / Investigation / Action / Resolution |
| HH:MM | [Next event] | Detection |
| HH:MM | [Next event] | Investigation |
| HH:MM | [Action taken] | Action |
| HH:MM | [Result observed] | Observation |
| HH:MM | [Incident resolved] | Resolution |
| HH:MM | [Verification complete] | Verification |

**Example timeline entries:**
- `14:30` - First user report: "Can't access internal wiki" (Detection)
- `14:35` - Additional reports from 5 users, same symptom (Detection)
- `14:38` - Engineer begins investigation: VPN status checks (Investigation)
- `14:42` - Confirmed: VPN connected but DNS resolution failing for internal domains (Investigation)
- `14:50` - Root cause identified: DNS servers not pushed to VPN clients (Investigation)
- `15:00` - Applied fix: Updated VPN server DNS push policy (Action)
- `15:05` - Verified: New VPN connections receive correct DNS (Verification)
- `15:10` - Users asked to disconnect/reconnect VPN (Action)
- `15:30` - 80% of users report resolution (Verification)
- `16:45` - Last affected user reconnected, full resolution confirmed (Resolution)

---

## Impact Analysis

### User Impact
**Who was affected:**
- [Department / role / location]
- [Number of users]
- [Type of impact: no access / degraded performance / etc.]

**What they couldn't do:**
- [Critical function 1]
- [Critical function 2]
- [Workaround available: Yes/No - describe if yes]

### System Impact
**Systems affected:**
- [System 1: status during incident]
- [System 2: status during incident]

**Data impact:**
- Data loss: Yes / No
- Data integrity: Affected / Not affected
- Backups: Required / Not required

### Business Impact
**Quantifiable impact:**
- Lost productivity: [estimate hours]
- Revenue impact: [if applicable]
- SLA breach: Yes / No
- Customer-facing: Yes / No

**Qualitative impact:**
- [Team morale / trust impact]
- [Reputational considerations]

---

## Root Cause Analysis

### What Happened (Technical Details)

**The failure chain:**
1. [Initial condition or misconfiguration]
2. [What triggered the failure]
3. [How it propagated]
4. [Why monitoring didn't catch it / why it wasn't prevented]

**Example:**
1. VPN server was configured to push DNS servers 10.0.0.10 and 10.0.0.11 to clients
2. DNS server 10.0.0.10 was decommissioned 2 weeks ago without updating VPN config
3. DNS server 10.0.0.11 was rebooted for patching and took 30 minutes to come back
4. During this window, VPN clients had no working DNS servers
5. Firewall rule allowing VPN clients to reach new DNS server 10.0.0.20 was never created
6. Monitoring only checked VPN tunnel establishment, not DNS functionality

### Root Cause (Specific Technical Reason)

**Primary root cause:**
[Exact technical reason - config error, failed component, human error, design flaw]

Example: "VPN server DNS push policy referenced a decommissioned DNS server (10.0.0.10) and a single point of failure DNS server (10.0.0.11). When 10.0.0.11 was rebooted, VPN clients had no functional DNS resolution."

**Evidence:**
- Config file showing: `[relevant config snippet]`
- Log showing: `[relevant log entry]`
- Command output proving: `[verification command]`

**Artifacts:**
- `artifacts/vpn-config-before.txt`
- `artifacts/dns-failure-logs.txt`
- `artifacts/firewall-rules-missing.png`

### Contributing Factors

**Why this root cause became an incident:**

1. **[Contributing factor 1]**
   - Description: [What made this worse]
   - Why it mattered: [Impact on incident]

2. **[Contributing factor 2]**
   - Description: [What else contributed]
   - Why it mattered: [Impact on incident]

**Example:**
1. **Lack of DNS health monitoring for VPN clients**
   - Monitoring checked VPN tunnel up/down but not DNS functionality
   - This delayed detection until user reports

2. **No change management for DNS server decommission**
   - When 10.0.0.10 was decommissioned, dependent systems weren't identified
   - VPN config wasn't updated as part of decommission process

3. **Single point of failure in DNS architecture**
   - Only one remaining DNS server available to VPN clients
   - No redundancy when it was rebooted

---

## Detection and Response

### How We Found Out
- **Detection method:** User report / Monitoring alert / Scheduled check
- **Time to detect:** [X minutes from start of impact]
- **Initial symptoms reported:** [What users/monitoring said]

### Response Effectiveness

**What went well:**
- ✅ [Quick triage / good collaboration / effective communication]
- ✅ [Successful troubleshooting method]
- ✅ [Rollback plan worked / verification was thorough]

**What could have gone better:**
- ⚠️ [Delayed detection / slow initial response]
- ⚠️ [Miscommunication or unclear escalation]
- ⚠️ [Failed first attempt / took too long to find root cause]

### Communication Timeline

| Time | Communication | Audience |
|------|--------------|----------|
| HH:MM | [What was communicated] | [Who was notified] |
| HH:MM | [Update provided] | [Audience] |
| HH:MM | [Resolution announced] | [Audience] |

---

## Resolution

### What Fixed It

**Immediate fix (restored service):**
1. [Action taken]
   ```
   [command or config change]
   ```
2. [Verification performed]
   ```
   [verification command]
   ```

**Temporary vs permanent:**
- Temporary fix: [if applicable - what was the quick workaround]
- Permanent fix: [the actual long-term solution]

### Verification

**How we confirmed resolution:**
1. [Technical verification test]
   - Command: `[command]`
   - Result: [success indicator]

2. [User verification]
   - [How users confirmed it worked]
   - [Number of users who validated]

3. [Monitoring confirmation]
   - [What monitoring showed after fix]

---

## Action Items

### Prevent Recurrence (Required)

| Action | Owner | Deadline | Status |
|--------|-------|----------|--------|
| [Specific action to prevent this exact issue] | [Name] | YYYY-MM-DD | Open / In Progress / Complete |
| [Another prevention action] | [Name] | YYYY-MM-DD | Open |
| [Config/code/process change] | [Name] | YYYY-MM-DD | Open |

**Example:**
| Action | Owner | Deadline | Status |
|--------|-------|----------|--------|
| Update VPN server to reference only active DNS servers (10.0.0.20, 10.0.0.21) | Network Team | 2024-01-20 | Complete |
| Create firewall rules allowing VPN clients to reach all DNS servers | Firewall Team | 2024-01-20 | Complete |
| Document VPN DNS config in runbook | Ops Team | 2024-01-22 | Complete |

### Improve Detection (Required)

| Action | Owner | Deadline | Status |
|--------|-------|----------|--------|
| [Monitoring improvement to catch this earlier] | [Name] | YYYY-MM-DD | Open |
| [Alert configuration] | [Name] | YYYY-MM-DD | Open |

**Example:**
| Action | Owner | Deadline | Status |
|--------|-------|----------|--------|
| Add synthetic monitoring: VPN client DNS resolution check | Monitoring Team | 2024-01-25 | In Progress |
| Alert if VPN clients can't resolve internal domains | Monitoring Team | 2024-01-25 | In Progress |

### Improve Response (Optional)

| Action | Owner | Deadline | Status |
|--------|-------|----------|--------|
| [Process improvement] | [Name] | YYYY-MM-DD | Open |
| [Documentation update] | [Name] | YYYY-MM-DD | Open |
| [Training need] | [Name] | YYYY-MM-DD | Open |

**Example:**
| Action | Owner | Deadline | Status |
|--------|-------|----------|--------|
| Create runbook: "VPN DNS troubleshooting" | Ops Lead | 2024-01-30 | Open |
| Update change management: require dependency check for DNS changes | Change Manager | 2024-02-15 | Open |

---

## Lessons Learned

### Technical Lessons

**What we learned about the system:**
- [Technical insight about how things work or fail]
- [Design weakness discovered]
- [Dependency we didn't know about]

**Example:**
- VPN DNS configuration is a single point of failure for remote workers
- Current monitoring only checks tunnel status, not application-layer functionality
- DNS server decommissions need a dependency discovery process

### Process Lessons

**What we learned about our processes:**
- [Gap in change management / monitoring / documentation]
- [Escalation path issue]
- [Communication breakdown]

**Example:**
- Change management doesn't currently require identifying dependent systems
- No standard process for decommissioning infrastructure components
- Runbooks for VPN troubleshooting were outdated

### What Went Well

**Positive outcomes to maintain:**
- [Something that worked well during response]
- [Good practice to continue]

**Example:**
- Quick escalation to senior engineer when initial attempts failed
- Clear communication updates to affected users every 30 minutes
- Thorough verification before declaring incident resolved

---

## Supporting Evidence

### Configuration Files

**Before:**
```
[relevant config section showing the problem]
```

**After:**
```
[relevant config section showing the fix]
```

### Log Excerpts

**Error logs:**
```
[timestamp] [relevant error message showing failure]
```

**Resolution logs:**
```
[timestamp] [log entry showing successful resolution]
```

### Commands Used

**Investigation:**
```bash
# [Description of what this showed]
[command]
```

**Resolution:**
```bash
# [Description of fix applied]
[command]
```

**Verification:**
```bash
# [Description of how this proved success]
[command]
```

---

## Related Documentation

**Related tickets:**
- [CASE-XXX - initial detection ticket]
- [CASE-XXX - related issues discovered]

**Runbooks created/updated:**
- [RB-XXX - new or updated runbook]

**Change records:**
- [CHG-XXX - config changes made]

**External references:**
- [Vendor documentation used]
- [Internal wiki pages]

---

## Appendix

### Appendix A: Full Timeline (Detailed)

[If the main timeline was summarized, include the complete detailed timeline here with all events]

### Appendix B: User Reports

[Relevant user reports or support tickets that triggered detection]

### Appendix C: Monitoring Data

[Screenshots or data from monitoring systems showing the incident]

### Appendix D: Architecture Diagram

[If helpful: diagram showing the systems involved and where the failure occurred]

`artifacts/architecture-diagram.png`

---

## Sign-off

**Postmortem reviewed by:**
- [ ] Incident responder: [Name] - [Date]
- [ ] Technical lead: [Name] - [Date]
- [ ] [Stakeholder]: [Name] - [Date]

**Action items tracked in:** [Ticket system / project board link]

**Follow-up review scheduled for:** YYYY-MM-DD
