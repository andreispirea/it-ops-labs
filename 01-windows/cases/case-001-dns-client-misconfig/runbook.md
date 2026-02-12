# Runbook: Windows DNS Client Troubleshooting

## Purpose
Fix DNS resolution failures on Windows clients where IP connectivity works but name resolution fails.

## Symptoms
- User cannot access websites by name
- `ping google.com` fails with "could not find host"
- `ping 8.8.8.8` succeeds

## Prerequisites
- Admin access to affected workstation
- Known-good DNS server IPs (e.g., 8.8.8.8 or corporate DNS)

## Diagnostic Procedure

### Step 1: Verify Symptom
```cmd
ping google.com
ping 8.8.8.8
```
**Expected:** First fails, second succeeds → DNS issue

### Step 2: Check DNS Configuration
```cmd
ipconfig /all
```
**Look for:** DNS Servers line under active adapter

**Common issues:**
- Invalid IPs (e.g., 1.2.3.4)
- Empty/missing
- Wrong corporate DNS

### Step 3: Test Manual DNS Query
```cmd
nslookup google.com 8.8.8.8
```
**If this works:** Config issue, not DNS service issue

## Fix Procedure

### Option A: Restore DHCP 
1. Open Network Adapter Properties
   - Control Panel → Network and Sharing Center → Change adapter settings
   - Right-click active adapter → Properties → IPv4 → Properties
2. Select "Obtain DNS server address automatically"
3. Click OK

### Option B: Set Manual DNS
1. Same path as above
2. Select "Use the following DNS server addresses"
3. Set Preferred DNS: `8.8.8.8`
4. Set Alternate DNS: `8.8.4.4`
5. Click OK

### Step 4: Flush Cache
```cmd
ipconfig /flushdns
```

### Step 5: Verify
```cmd
nslookup google.com
ping google.com
```
**Expected:** Both succeed

## Escalation Criteria
Escalate if:
- Fix doesn't work after applying
- DHCP server is not providing DNS 
- Corporate DNS servers are down

