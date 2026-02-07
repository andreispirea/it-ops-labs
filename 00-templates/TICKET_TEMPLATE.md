# Ticket #[CASE-NUMBER] - [Brief Descriptive Title]

## Ticket Information
- **Ticket ID**: CASE-[XXX]-[descriptive-name]
- **Date**: YYYY-MM-DD
- **Severity**: [Critical | High | Medium | Low]
- **Status**: [Open | In Progress | Resolved | Closed]
- **Category**: [Windows | Linux | Network | Identity/Access | Other]
- **Assigned To**: [Your Name]
- **Time to Resolve**: [X hours/minutes]

---

## Issue Summary
<!-- 2-3 sentence executive summary of the problem -->
[Clear, concise description of what broke and the business impact]

---

## Reported Symptoms
<!-- What the user/system reported initially -->
- **User Report**: [What was reported by end user or monitoring]
- **Affected System(s)**: [Hostname, IP, or service name]
- **Impact Scope**: [Number of users affected / services down]
- **Business Impact**: [How this affects operations]

**Observable Behavior**:
- [Symptom 1]
- [Symptom 2]
- [Symptom 3]

---

## Environment Details
<!-- Critical context about the affected system -->
- **Operating System**: [Windows 11 / Ubuntu 22.04 / etc.]
- **Hostname/IP**: [computer-name / 192.168.1.100]
- **Domain/Network**: [CORP.LOCAL / VLAN 10 / etc.]
- **Related Services**: [Service names, dependencies]
- **Recent Changes**: [Any known changes in last 72h]

---

## Initial Triage
<!-- Your first investigation steps -->

**Expected Behavior**:
- [What should be happening normally]

**Observed Behavior**:
- [What is actually happening - be specific]

**Difference/Gap**:
- [Clear statement of the deviation]

---

## Investigation & Troubleshooting

### Hypothesis 1: [First Theory]
**Test Performed**:
```
[Command or test procedure]
```

**Output**:
```
[Actual command output or screenshot reference]
```

**Result**: ✓ Confirmed / ✗ Ruled Out  
**Evidence**: [artifacts/screenshot-01.png]

---

### Hypothesis 2: [Second Theory]
**Test Performed**:
```
[Command or test procedure]
```

**Output**:
```
[Actual command output or screenshot reference]
```

**Result**: ✓ Confirmed / ✗ Ruled Out  
**Evidence**: [artifacts/screenshot-02.png]

---

### Root Cause Identified
**Finding**: [Clear statement of what was broken]

**Evidence**:
- [Log entry, error message, or config showing the problem]
- [Reference to artifacts/evidence-file]

**Why This Occurred**: [Technical explanation of the failure mechanism]

---

## Resolution Steps

### Fix Applied
```bash
# Step 1: [Description]
[command-or-action]

# Step 2: [Description]
[command-or-action]

# Step 3: [Description]
[command-or-action]
```

**Configuration Changes**:
- File: `[/path/to/config]`
- Changed: `[old-value]` → `[new-value]`
- Reason: [Why this specific change]

---

## Verification
<!-- Prove the fix worked -->

**Test 1**: [Verification step]
```
[Command to verify]
```
**Result**: ✓ Pass  
**Evidence**: [artifacts/verification-01.png]

**Test 2**: [Additional verification]
```
[Command to verify]
```
**Result**: ✓ Pass  
**Evidence**: [artifacts/verification-02.png]

**User Confirmation**: [User tested and confirmed working - Date/Time]

---

## Prevention & Future Mitigation

### Immediate Prevention
- [Action taken to prevent immediate recurrence]

### Long-term Prevention
- **Monitoring**: [What to monitor to catch this early]
- **Automation**: [Script or check to prevent/detect]
- **Documentation**: [Runbook reference: /runbooks/runbook-XXX.md]
- **Configuration Standard**: [What should be the standard going forward]

### Recommended Actions
1. [Action 1 - who should do it]
2. [Action 2 - when it should happen]
3. [Action 3 - what needs approval]

---

## Knowledge Base
<!-- Make this findable for others -->

**Related Tickets**: [CASE-XXX, CASE-YYY]  
**Related Runbooks**: [/runbooks/runbook-XXX.md]  
**Keywords**: [DNS, firewall, service-failure, permissions, etc.]

---

## Artifacts & Evidence
<!-- All supporting files referenced above -->

```
/artifacts/
├── screenshot-01-initial-error.png
├── screenshot-02-event-viewer.png
├── screenshot-03-verification.png
├── eventlog-export.txt
├── command-output.txt
└── config-before-after.txt
```

---

## Timeline
<!-- Helpful for postmortems and learning -->

| Time | Event | Action Taken |
|------|-------|--------------|
| 09:15 | Issue reported | Ticket created |
| 09:20 | Triage started | Checked service status |
| 09:25 | Root cause found | Identified DNS misconfiguration |
| 09:30 | Fix applied | Updated DNS settings |
| 09:35 | Verified | User confirmed resolution |
| 09:40 | Documented | Created runbook |

**Total Resolution Time**: [XX minutes]

---

## Notes & Lessons Learned
<!-- Your reflection - this shows growth mindset -->

**What Worked Well**:
- [Systematic approach paid off]
- [Tool X helped identify the issue quickly]

**What Could Be Improved**:
- [Could have checked Y first to save time]
- [Need better monitoring for this scenario]

**Skills Applied**:
- [Event Viewer filtering]
- [DNS troubleshooting]
- [Service dependency analysis]

**New Knowledge Gained**:
- [Specific technical insight from this case]

---

## Escalation Notes
<!-- Only if you escalated - shows good judgment -->

**Would Escalate If**:
- [Scenario requiring senior engineer]
- [Scenario requiring vendor support]

**Information to Provide on Escalation**:
- This ticket (full investigation history)
- All artifacts in /artifacts/
- Tests already ruled out: [X, Y, Z]
- Current hypothesis: [Your best theory]

---

## Sign-off
- **Resolved By**: [Your Name]
- **Reviewed By**: [Reviewer name - or self if lab]
- **Date Closed**: YYYY-MM-DD
- **Disposition**: [Resolved - Root cause fixed and verified]
