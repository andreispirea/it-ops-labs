# Incident Ticket: Default Gateway Misconfiguration (Lab)

## Ticket Metadata

| Field | Value |
|---|---|
| **Ticket ID** | CASE-001-GATEWAY-MISCONFIGURATION |
| **Date** | 2026-02-22 |
| **Status** | Resolved |
| **Severity** | Low (Lab simulation) |
| **Category** | Network → L3 Routing |
| **Environment** | Home Lab (VirtualBox) |
| **Affected Host** | **WIN11** (Windows 11 VM) |
| **Primary Symptom** | Off-subnet connectivity failure |
| **Root Cause Type** | Misconfiguration (Incorrect default gateway) |

---

## Environment / Topology

### Hosts
- **WIN11 (Windows 11 VM)**  
  - Host-only NIC: `192.168.56.10/24`
  - Default gateway (expected): `10.10.10.1`
- **UBU-SRV (Ubuntu Server VM)**  
  - Host-only NIC: `192.168.56.20/24`

### Networks / Subnets
- **Host-only subnet (LAN):** `192.168.56.0/24`
- **Upstream / NAT subnet (gateway network):** `10.10.10.0/24` (gateway: `10.10.10.1`)

> Notes: Host-only provides local L2/L3 connectivity between VMs. Off-subnet traffic requires a valid default route via the configured gateway.

---

## Issue Summary

WIN11 could communicate with local subnet resources but could not reach any off-subnet destinations (e.g., public IPs). The default gateway was misconfigured to a non-existent next-hop (`10.10.10.99`), causing all non-local traffic to fail because the host had no valid route to forward packets beyond its local subnet.

---

## Reported Symptoms

- Local subnet reachable (LAN traffic works).
- Off-subnet destinations unreachable (internet/public IPs fail).
- Traceroute fails early / does not progress beyond the first hop.

---

## Impact

- WIN11 unable to access any off-subnet services (internet, remote networks).
- Local services on `192.168.56.0/24` remain reachable.

Scope is limited to the affected endpoint (WIN11) in a lab environment.

---

## Evidence / Artifacts

- **Baseline configuration:** `artifacts/01-baseline.png` (ipconfig /all)
- **Baseline connectivity tests:** `artifacts/01-baseline-connectivity.png` (ping local + ping 8.8.8.8 + tracert 8.8.8.8)
- **Baseline routing table:** `artifacts/01-routing-table.png` (route print)
- **Change (break) command:** `artifacts/02-broke-gateway-command.png` (netsh set gateway → 10.10.10.99)
- **Failure observed:** `artifacts/03-failure-observed.png` (ping/tracert showing off-subnet failure while local still works)
- **Fix applied:** `artifacts/04-fix-applied.png` (netsh set gateway → 10.10.10.1 + ipconfig)
- **Verification after fix:** `artifacts/04-test.png` (ping 8.8.8.8 + tracert successful)

---

## Investigation

### 1) Baseline (Known good)
- Confirmed default gateway and interface configuration.
- Verified:
  - Local connectivity to UBU-SRV (`192.168.56.20`) works.
  - Off-subnet connectivity to `8.8.8.8` works.
  - Traceroute to `8.8.8.8` progresses normally.

**Key evidence:** `01-baseline.png`, `01-baseline-connectivity.png`, `01-routing-table.png`

### 2) Induced change (Reproduction)
- Modified default gateway on WIN11 to `10.10.10.99` via netsh.

**Key evidence:** `02-broke-gateway-command.png`

### 3) Observed failure signature
- Local subnet remained reachable (UBU-SRV reachable).
- Off-subnet traffic failed:
  - `ping 8.8.8.8` fails
  - `tracert 8.8.8.8` fails early / does not progress

This pattern strongly indicates a routing / default route problem rather than DNS (failure reproduced by IP).

**Key evidence:** `03-failure-observed.png`

### 4) Root cause validation
- `route print` shows the default route relies on the configured gateway.
- With gateway set to a non-existent next hop, the host cannot forward traffic off-subnet.

(If you captured route print during failure, add it here; if not, baseline + config change + symptom pattern is still sufficient for this lab.)

---

## Root Cause

WIN11 default gateway was misconfigured to `10.10.10.99` (invalid / unreachable next-hop). As a result, the host had no functional path for non-local destinations and could only communicate within the directly connected subnet `192.168.56.0/24`.

---

## Remediation

- Restored correct default gateway to `10.10.10.1` via netsh.
- Confirmed gateway value applied with `ipconfig /all`.

**Key evidence:** `04-fix-applied.png`

---

## Verification After Fix

- `ping 192.168.56.20`  (local subnet)
- `ping 8.8.8.8`  (off-subnet)
- `tracert 8.8.8.8`  (path progresses)

**Key evidence:** `04-test.png`

---

## Preventive Measures / Lessons Learned

- **Endpoint checklist:** When off-subnet fails but local works, immediately check:
  - `ipconfig /all` (gateway present and correct)
  - `route print` (default route exists and points to expected next-hop)
  - `tracert <public IP>` (does it leave the host / reach first hop?)
- **Configuration control:** Prefer DHCP-managed gateway settings (where appropriate) to reduce manual misconfig.
- **Documentation:** Maintain an IP plan that states expected gateway per subnet to speed up triage.

---