# Runbook: [CLEAR_PROCEDURE_NAME]

## Document Control
| Field | Value |
|-------|-------|
| **Runbook ID** | RB-XXX-[short-name] |
| **Version** | 1.0 |
| **Last Updated** | YYYY-MM-DD |
| **Owner** | [Your Name / Team] |
| **Reviewed By** | [Name or "Self-review"] |
| **Next Review Date** | YYYY-MM-DD |

---

## Purpose
**What this runbook solves — one clear sentence**

Example: "Restore DNS resolution on Windows clients when internal domain names fail to resolve"

---

## Scope

**When to use this runbook:**
- [Specific symptom or trigger condition]
- [Another condition that indicates this procedure applies]

**When NOT to use this runbook:**
- [Exclusion criteria - situations where this procedure doesn't apply]
- [Edge cases that need different handling]

**Success criteria:**
- [Measurable outcome that indicates procedure worked]

---

## Prerequisites

**Required access:**
- [ ] Administrative privileges on [system type]
- [ ] Access to [service/console]
- [ ] Permissions to [specific action]

**Required information:**
- [ ] [Hostname / IP address / identifier]
- [ ] [Username / account details]
- [ ] [Other context needed before starting]

**Required tools:**
- [ ] [Tool name and version if relevant]
- [ ] [Any scripts or utilities]

**Required knowledge:**
- [ ] Basic understanding of [technology/concept]
- [ ] Familiarity with [system/service]

---

## Risk Assessment

**Impact level:** Low / Medium / High

**What could go wrong:**
- [Potential negative outcome 1]
- [Potential negative outcome 2]

**Mitigation:**
- [How you reduce risk before/during procedure]
- [When to stop and escalate]

**Rollback available:** Yes / No  
**Rollback complexity:** [Simple / Moderate / Complex]

---

## Before You Start

### 1. Verify the symptoms
**Confirm this is actually the issue this runbook solves:**

Check 1: [Test command or observation]
```
[command]
```
**Expected output:** [What you should see]

Check 2: [Another verification]
```
[command]
```
**Expected output:** [What confirms this is the right procedure]

### 2. Document current state
**Capture evidence before making changes:**

```bash
# [Describe what this captures]
[command to capture current state]
```

**Save output to:** `baseline-state-[timestamp].txt`

### 3. Create backup/snapshot (if applicable)
- [ ] [Backup step if needed]
- [ ] [Snapshot VM if relevant]
- [ ] [Export current config]

---

## Procedure

### Step 1: [Action Name]
**What you're doing:** [Brief explanation of this step's purpose]

**Commands:**
```
[exact command with placeholders if needed]
```

**Expected result:**
```
[what success looks like]
```

**If this fails:**
- ⚠️ [What to check]
- ⚠️ [Common failure reason]
- ⚠️ [When to stop and escalate]

---

### Step 2: [Action Name]
**What you're doing:** [Explanation]

**Commands:**
```
[command]
```

**Expected result:**
```
[success indicator]
```

**Decision point:**
- If [condition A], proceed to Step 3
- If [condition B], skip to Step 5
- If [condition C], stop and see Troubleshooting section

---

### Step 3: [Action Name]
**What you're doing:** [Explanation]

**Commands:**
```
[command]
```

**Expected result:**
```
[success indicator]
```

**Important notes:**
- ⚠️ [Critical warning or timing consideration]
- 💡 [Helpful tip or context]

---

### Step 4: [Final Action]
**What you're doing:** [Explanation]

**Commands:**
```
[command]
```

**Expected result:**
```
[success indicator]
```

---

## Verification

**Test 1: [Primary function test]**
```
[command to verify]
```
**Expected result:** [What proves it's working]  
**Status:** ✅ Pass / ❌ Fail

---

**Test 2: [Secondary verification]**
```
[command]
```
**Expected result:** [Success indicator]  
**Status:** ✅ Pass / ❌ Fail

---

**Test 3: [End-user perspective test]**
- [What the user should be able to do now]
- [How to confirm from user perspective]

**Status:** ✅ Pass / ❌ Fail

---

## Rollback Procedure

**If the procedure fails or makes things worse:**

### Step 1: [Revert action]
```
[command to undo]
```

### Step 2: [Restore previous state]
```
[command to restore]
```

### Step 3: [Verify rollback worked]
```
[verification command]
```

**After rollback:**
- Document what went wrong in incident ticket
- Escalate with details of what was attempted
- Review this runbook for accuracy

---

## Common Failure Modes

### Issue 1: [Common problem during procedure]
**Symptom:** [What you see]  
**Cause:** [Why it happens]  
**Resolution:** [How to fix]

---

### Issue 2: [Another common problem]
**Symptom:** [What you see]  
**Cause:** [Why it happens]  
**Resolution:** [How to fix]

---

### Issue 3: [Edge case]
**Symptom:** [What you see]  
**Cause:** [Why it happens]  
**Resolution:** [How to fix or when to escalate]

---

## Troubleshooting Decision Tree

**If problem still exists after procedure:**

1. **Check which verification test failed:**
   - **Test 1 failed** → [Specific troubleshooting path]
   - **Test 2 failed** → [Specific troubleshooting path]  
   - **Test 3 failed** → [Specific troubleshooting path]

2. **If all tests pass but problem persists:**
   - Re-verify symptoms match this runbook's scope
   - Check for additional issues not covered here
   - See escalation criteria below

3. **If tests pass and problem is resolved:**
   - Document success in ticket
   - Complete post-procedure actions
   - Close ticket

---

## Escalation Criteria

**Escalate to [Team/Person] if:**
- [ ] [Condition that requires escalation]
- [ ] [Another escalation trigger]
- [ ] [Time-based escalation: stuck for > X minutes]

**When escalating, provide:**
- Current state documentation
- Steps already performed
- Error messages or unexpected outputs
- Baseline state captured earlier

**Escalation contact:** [Team email / ticket queue / person]

---

## Post-Procedure Actions

**Immediate:**
- [ ] Verify monitoring is showing healthy state
- [ ] Notify affected users/teams

**Within 24 hours:**
- [ ] Check for recurrence
- [ ] Review if monitoring would catch this earlier

**Ongoing:**
- [ ] Update this runbook if procedure changed
- [ ] Note any new failure modes discovered

---
## Related Documentation
**Related runbooks:**
- [RB-XXX-related-procedure]

**Reference documentation:**
- [Vendor docs / internal wiki links]

**Related incidents:**
- [CASE-XXX - ticket that led to this runbook]

**Scripts/automation:**
- [Path to relevant scripts]

---


**Best practices:**
- 💡 [Operational tip]
- 💡 [Common optimization]

**Historical context:**
- [Why this runbook was created]
- [Frequency of use: daily / weekly / monthly / rare]

**Known limitations:**
- [What this runbook doesn't cover]
- [When a different approach is needed]

---

## Revision History

| Version | Date | Author | Changes |
|---------|------|--------|---------|
| 1.0 | YYYY-MM-DD | [Name] | Initial creation |
| | | | |
| | | | |

---

## Appendix

### Appendix A: Command Reference
**Quick reference for key commands:**

```bash
# [Description]
[command with common flags]

# [Description]
[command with common flags]
```

### Appendix B: Configuration Files
**Relevant config file locations:**

| System | Config Path | Key Parameters |
|--------|-------------|----------------|
| [OS/Service] | `/path/to/config` | [parameter names] |

### Appendix C: Log Locations
**Where to find relevant logs:**

| System | Log Path | What to Look For |
|--------|----------|------------------|
| [System] | `/path/to/log` | [error patterns] |

### Appendix D: Screenshots (if helpful)
- `artifacts/step-3-expected-output.png`
- `artifacts/verification-success.png`## Notes & Tips

**Time to complete:** [Estimated duration]



