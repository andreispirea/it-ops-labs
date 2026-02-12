# Incident Ticket: DNS Client Misconfiguration

## Ticket Metadata
| Field | Value |
|-------|-------|
| **Ticket ID** | CASE-001-DNS-MISCONFIG |
| **Date Opened** | 11-02-2026 |
| **Severity** | Medium (single user impact) |
| **Status** | Resolved|
| **Category** | Windows / Network |

---

## Issue Summary

Windows 11 workstation unable to resolve domain names. User reported "internet is broken" but IP connectivity was working.


## Reported Symptoms

- User cannont access websites by name (google.com, internal sites)
- 'ping google.com' fails with "Ping request could not find host google.com"
- Browser shows DNS resolution errors
- 'ping 8.8.8.8' succeeds (IP connectivity confirmed working)

**Evidence artifacts:**
- `artifacts/03-symptom-ping-fail.png`
- `artifacts/03-symptom-browser-fail.png`


## Troubleshooting Steps

### Hypothesis: DNS client misconfiguration
**Test 1: Check DNS config**
```cmd
ipconfig /all
```
**Result:** DNS servers set to 1.2.3.4 and 5.6.7.8 (invalid/unreachable)

**Test 2: Verify external DNS works**
```cmd
nslookup google.com 8.8.8.8
```
**Result:**  Success — proves DNS service itself is fine, config is wrong

**Conclusion:**  Confirmed — DNS client has invalid server addresses

**Evidence:**
- `artifacts/04-diagnostic-ipconfig.png`
- `artifacts/04-diagnostic-nslookup-override.png`


## Root Cause
Network adapter (Ethernet 2) was manually configures with invalid DNS server addresses (1.2.3.4, 5.6.7.8). These IPs are unreachable, preventing name resolution.

**Likely cause:** Manual misconfiguration during network troubleshooting or testing.


## Resolution
**Steps taken:**
1. Opened Network Adapter Properties -> IPv4 -> Properties
2. Changed DNS settings from manual (1.2.3.4 / 5.6.7.8) to "Obtain DNS server address automatically"
3. Flushed DNS cache: 'ipconfig /flushdns'

**Evidence**
- 'artifacts/05-fix-dns-restored.png'

## Verification
**Test 1: Name resolution**
```cmd
nslookup google.com
ping google.com
```
**Result:** both succeed

**Test 2: Browser test**
- Loaded google.com successfully
- Evidence: `artifacts/06-verify-browser-works.png`

**Test 3: Config verification**
```cmd
ipconfig /all
```
**Result:** DNS servers now showing correct DHCP-assigned values 

## Prevention
- **Documented:** Created runbook for DNS client troubleshooting (see `runbook.md`)
- **Recommendation:** Check if other workstations have similar manual DNS configs


## Related Documentation
- Runbook: `runbook.md` (reusable fix procedure)


## Key Learning
**Diagnosis pattern learned:**
- "Internet broken" + IP connectivity works = DNS issue
- `nslookup` with explicit DNS server can bypass client config to test
