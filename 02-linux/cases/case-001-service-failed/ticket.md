# Incident Ticket: Linux Service Failure (nginx)

## Ticket Metadata
| Field | Value |
|-------|-------|
| **Ticket ID** | CASE-001-LINUX-SERVICE-FAILURE |
| **Date Opened** | 15-02-2026 |
| **Environment** | Ubuntu Server 24.04 (VM) |
| **Access Method** | Remote via SSH from Windows 11 VM (192.168.56.10) |
| **Host** | ubu-srv (192.168.56.10) |
| **Service Affected** | nginx |
| **Severity** | Low (Lab simulation) |
| **Status** | Resolved|

---

## Issue Summary

Nginx web service failed to start after configuration modification. The issue was caused by a syntax error in '/etc/nginx/nginx.conf' (missing semicolon in 'user' directive).

## Reported Symptoms

- 'curl http://localhost' -> Connection refused
- 'ps aux | grep nginx' -> No nginx process running
- 'ss -tlnp' -> Port 80 not listening

**Evidence artifacts:**
- `03-symptom-curl-fail.txt`
- `03-symptom-no-process.txt`
- `03-symptom-port-not-listening.txt`

## Impact
 - Web services unavailable locally.
 - No HTTP responses on port 80.

## Investigation
### 5.1 Service Status Check
```bash
sudo systemctl status nginx
```
Result: Service failed to start

**Evidence artifact:** 
`04-diagnostic-systemctl-detail.txt`

### 5.2 Configuration Validation 
```bash
sudo nginx -t
```
Result: invalid number of arguments in "user" directive in /etc/nginx/nginx.conf:2

**Evidence artifact:** 
`04-diagnostic-config-test.txt`

### 5.3 Log Review
```bash
sudo journalctl -u nginx.service -n 20 --no-pager
```
Result: Service failed with exit-code due to configuration syntax error.

**Evidence artifact:** 
`04-diagnostic-journalctl.txt`

## 6 Root Cause
Missing semicolon `;` in nginx configuration file.

## 7 Remediation
1. Edited `/etc/nginx/nginx.conf` to correct syntax error (added missing semicol).
2. Validate configuration with: 
    ```bash
    sudo nginx -t
    ```
    **Evidence artifact:** 
    `05-fix-config-test.txt`

3. Restarted nginx service 
    ```bash
    sudo systemctl restart nginx
    ```
4. Verified service availability
    ```bash
    sudo systemctl status nginx
    ```
    Result: Service active 

    **Evidence artifact:** 
    `05-fix-service-started.txt`

## 8 Verification After Fix
- `curl http://localhost` -> Successful HTTP response 
- `sudo ss -tlnp | grep :80` -> Port 80 listening

**Evidence artifact:** 
- `06-verify-curl-works.txt`
- `06-verify-listening.txt`

# Preventive Measures
- Validate config with `nginx -t`
- Create configuration backups prior to editing. 