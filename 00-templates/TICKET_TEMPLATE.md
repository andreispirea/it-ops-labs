Ticket: <INC-YYYYMMDD-###> — <Short Title>
Summary

Type: Incident | Service Request | Problem

Priority: P1 | P2 | P3 | P4

Status: New | In Progress | Resolved

Environment: Lab | Production-like Lab

Service/System: <DNS | DHCP | VPN | AD | File Share | Linux Service>

Affected host(s): <hostname / IP>

Opened: <YYYY-MM-DD HH:MM> (TZ)

Closed: <YYYY-MM-DD HH:MM> (TZ)

Impact

User impact: <what the user could not do>

Scope: <single host | subnet | multiple hosts>

Start time: <approx time>

Detection: user report | monitoring | self-detected

Symptoms & Evidence

Symptoms:

<bullet>
<bullet>

Error message(s) (verbatim):

<exact text>

Evidence:

Logs: ./artifacts/logs/…

Screenshots: ./artifacts/screenshots/…

PCAP (if any): ./artifacts/pcaps/…

Checks Performed

 Connectivity (ping/traceroute)

 DNS resolution (nslookup/dig)

 Routing table (route print / ip route)

 Port reachability (Test-NetConnection / nc)

 Service health (services.msc / systemctl)

 Auth/permissions (AD/Entra/groups)

 Local firewall

Investigation (timestamped)

HH:MM Observed: <what you saw>

HH:MM Ran:

<command> → <result summary> (evidence path if relevant)

HH:MM Found: <key discovery>

Resolution

Fix applied: <exact change + where>

Rollback plan: <one-liner>

Verification

 Original reproduction now succeeds

 DNS/DHCP/VPN/service checks pass (as applicable)

Verification evidence: ./artifacts/…

Prevention / Follow-up

 Runbook created/updated: ../runbooks/<name>.md

 Add monitoring/guardrail: <what>

References

Related runbook: ../runbooks/<name>.md

Related lab notes (if any): ./lab.md
