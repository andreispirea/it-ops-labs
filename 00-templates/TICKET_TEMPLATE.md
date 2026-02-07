# Incident Ticket: [SHORT_DESCRIPTIVE_TITLE]

## Ticket Metadata
| Field | Value |
|-------|-------|
| **Ticket ID** | CASE-XXX-[description] |
| **Date Opened** | YYYY-MM-DD HH:MM |
| **Date Resolved** | YYYY-MM-DD HH:MM |
| **Severity** | Critical / High / Medium / Low |
| **Status** | Open / In Progress / Resolved / Closed |
| **Assigned To** | [Your Name / Team] |
| **Category** | Windows / Linux / Network / Identity / Application |

---

## Issue Summary
**One-line description of what broke and the impact**

Example: "Internal users unable to resolve company domain names - DNS server unreachable"

---

## Reported Symptoms
**What the user/system reported — be specific, use exact error messages**

- Error message: `[exact text or screenshot reference]`
- When it started: [timestamp or "approximately X hours ago"]
- Affected users/systems: [scope]
- What works: [things that still function]
- What doesn't work: [specific failures]

**Evidence artifacts:**
- Screenshot: `artifacts/screenshot-001-error-message.png`
- Log snippet: `artifacts/error-log-extract.txt`

---

## Impact Assessment
**Business/operational impact**

| Impact Area | Details |
|-------------|---------|
| **Users Affected** | [number] users / [specific team/department] |
| **Systems Affected** | [hostnames or service names] |
| **Business Impact** | [can't access email / can't reach internal apps / productivity stopped] |
| **Workaround Available?** | Yes / No — [describe if yes] |

---

## Initial Triage
**First observations and quick checks**

**Environment:**
- System: [hostname or IP]
- OS: [Windows 11 / Ubuntu 22.04 / etc.]
- Network segment: [VLAN / subnet if relevant]

**Quick checks performed:**
1. [Basic connectivity test - result]
2. [Service status check - result]
3. [Log review - result]

---

## Troubleshooting Steps

### Hypothesis 1: [What you thought might be wrong]
**Test performed:**
```
[command or test]
```

**Result:**
```
[output or observation]
```

**Conclusion:** ✅ Confirmed / ❌ Ruled out

---

### Hypothesis 2: [Next theory]
**Test performed:**
```
[command or test]
```

**Result:**
```
[output or observation]
```

**Conclusion:** ✅ Confirmed / ❌ Ruled out

---

### Hypothesis 3: [If needed]
**Test performed:**
```
[command or test]
```

**Result:**
```
[output or observation]
```

**Conclusion:** ✅ Confirmed / ❌ Ruled out

---

## Root Cause
**What actually caused the failure — be specific**

[Clear technical explanation]

**Evidence:**
- Log entry: `artifacts/root-cause-log.txt`
- Config file: `artifacts/misconfigured-setting.png`
- Command output proving root cause: `artifacts/proof.txt`

---

## Resolution
**What you did to fix it**

**Steps taken:**
1. [Command or action]
   ```
   [exact command if applicable]
   ```
2. [Next action]
3. [Final action]

**Configuration changes:**
- File: `[path]`
- Change: [before → after]

**Services restarted:**
- [service name]

---

## Verification
**How you confirmed the fix worked**

**Test 1:** [What you tested]
```
[command]
```
**Result:** ✅ Working as expected

**Test 2:** [Additional verification]
```
[command]
```
**Result:** ✅ Confirmed

**User confirmation:**
- [User tested and confirmed working: Yes/No]
- [Screenshot of successful operation: `artifacts/verification.png`]

---

## Prevention & Follow-up

**Immediate prevention:**
- [What you did to prevent recurrence - monitoring alert / config change / documentation]

**Long-term recommendations:**
- [ ] [Monitoring improvement]
- [ ] [Configuration standardization]
- [ ] [Documentation update - link to runbook if created]
- [ ] [Training need identified]

**Runbook created:** [Link to runbook if this is a recurring pattern]

---

## Lessons Learned

**What went well:**
- [Detection method worked / quick isolation / etc.]

**What could improve:**
- [Earlier detection needed / documentation gap / etc.]

**New knowledge:**
- [Technical insight gained from this incident]

---

## Escalation Notes
**If you had to escalate or collaborate**

- **Escalated to:** [Team / Person]
- **What you provided:** [Evidence / tests performed / what you ruled out]
- **What you needed:** [Specific help requested]
- **Outcome:** [How escalation helped resolve]

---

## Attachments / Artifacts
**All evidence referenced above**

- `artifacts/screenshot-001-error-message.png` — [description]
- `artifacts/config-before.txt` — [description]
- `artifacts/config-after.txt` — [description]
- `artifacts/verification-output.txt` — [description]
- `artifacts/[name].pcap` — [packet capture if network issue]

---

## Related Documentation
- Runbook: `[link if created]`
- Related tickets: `[CASE-XXX if applicable]`
- Vendor KB: `[link if used]`
- Internal wiki: `[link if updated]`

---

## Timeline
| Time | Event |
|------|-------|
| HH:MM | Issue reported |
| HH:MM | Triage started |
| HH:MM | Root cause identified |
| HH:MM | Fix applied |
| HH:MM | Verification completed |
| HH:MM | Ticket closed |

**Total resolution time:** [X hours / X minutes]
