# LearningLab01 Daily Threat Intelligence Report — 2026-09-08

Generated: 2026-09-09T02:31:24.695Z

Report window: 2026-09-08T02:31:24.671Z through 2026-09-09T02:31:24.671Z

> This report summarizes security telemetry and honeypot activity. An alert indicates that a rule matched observed activity; it does not automatically prove that a system was compromised.

## Executive Summary

| Metric | Count |
|---|---:|
| Wazuh alerts | 82,637 |
| Attack-related alerts | 22,309 |
| Honeypot interactions | 78,597 |
| Authentication failures | 1,005 |
| Authentication successes | 405 |
| Critical alerts | 19 |
| High alerts | 188 |
| T-Pot artifacts observed | 2 |
| Malicious artifact detections | 0 |

### Notable Observations

- 19 critical-severity alerts require priority review.
- 188 high-severity alerts should be reviewed after the critical queue.
- Authentication failures exceeded successful authentications by a ratio of 2.48:1.
- Country attribution currently covers only 5.90% of alerts. Country totals should be treated as partial telemetry.
- The most frequent rule was 110213: T-Pot RDP connection from [IP address] to port 3389. (34,943 alerts).

## Wazuh Security Monitoring

### Alert Severity

| Severity | Alerts | Percentage |
|---|---:|---:|
| Critical | 19 | 0.02% |
| High | 188 | 0.23% |
| Medium | 978 | 1.18% |
| Low | 81,452 | 98.57% |
| Informational | 0 | 0.00% |

Severity represents the priority assigned by the Wazuh rule. Critical and high alerts should be investigated first, but repeated lower-severity events can also reveal scanning, credential attacks, or attacker preparation.

### Authentication Activity

- Authentication failures: 1,005
- Authentication successes: 405
- Failure-to-success ratio: 2.48:1

A successful authentication is not considered an attack by itself. Analysts should correlate successful logins with preceding failures, source addresses, usernames, target systems, and expected activity.

### Attack-Type Breakdown

| Category | Alerts | Percentage of attack-related alerts |
|---|---:|---:|
| Network attack | 19,137 | 85.78% |
| Payload delivery | 19,137 | 85.78% |
| Web attack | 1,390 | 6.23% |
| Authentication failure | 1,005 | 4.50% |
| Reconnaissance | 370 | 1.66% |
| Command execution | 226 | 1.01% |
| SMTP attack | 132 | 0.59% |
| Network scan | 93 | 0.42% |
| Malware | 51 | 0.23% |

> Category counts may overlap because one Wazuh alert can belong to multiple rule groups. The attack-related total counts each alert once.

### Country of Origin

Wazuh supplied country information for 4,879 alerts, representing 5.90% of all alerts.

| Country | Alerts | Percentage of all alerts | Relative volume |
|---|---:|---:|---|
| Unknown | 77,758 | 94.10% | Not geolocated |
| New Zealand | 2,452 | 2.97% | ████████████████████ |
| United States | 2,162 | 2.62% | ██████████████████ |
| United Kingdom | 191 | 0.23% | ██ |
| Turkey | 18 | 0.02% | █ |
| Germany | 17 | 0.02% | █ |
| China | 11 | 0.01% | █ |
| Canada | 7 | 0.01% | █ |
| Hungary | 6 | 0.01% | █ |
| Romania | 6 | 0.01% | █ |
| Iran | 3 | 0.00% | █ |
| Singapore | 3 | 0.00% | █ |
| South Africa | 2 | 0.00% | █ |
| Ukraine | 1 | 0.00% | █ |

> Relative-volume bars compare only countries with known geographic attribution. Unknown alerts are excluded from the bar scale.

> Geolocation is approximate. VPNs, proxies, cloud providers, compromised hosts, carrier networks, and incomplete GeoIP coverage can make the apparent country different from the attacker’s location.

### MITRE ATT&CK Tactics

| Tactic | Alerts |
|---|---:|
| Defense Evasion | 373 |
| Privilege Escalation | 372 |
| Initial Access | 359 |
| Persistence | 344 |
| Lateral Movement | 109 |
| Execution | 38 |
| Credential Access | 31 |
| Command and Control | 27 |
| Impact | 12 |

### MITRE ATT&CK Techniques

| Technique | Alerts |
|---|---:|
| Valid Accounts | 343 |
| Remote Services | 109 |
| Command and Scripting Interpreter | 38 |
| Brute Force | 31 |
| Sudo and Sudo Caching | 29 |
| Ingress Tool Transfer | 27 |
| Exploit Public-Facing Application | 16 |
| Stored Data Manipulation | 12 |
| Create Account | 1 |
| Disable or Modify Tools | 1 |

MITRE ATT&CK describes adversary behavior rather than declaring that an attack succeeded. These mappings help analysts connect individual alerts to possible attacker objectives and investigative hypotheses.

### Most Frequent Wazuh Rules

| Rule ID | Highest Level | Alerts | Description | Agents |
|---|---:|---:|---|---|
| 110213 | 4 | 34,943 | T-Pot RDP connection from [IP address] to port 3389. | tpot (34,943) |
| 110205 | 6 | 19,079 | T-Pot Honeytrap received a payload from [IP address] | tpot (19,079) |
| 110207 | 5 | 9,098 | T-Pot SentryPeer SIP activity from [IP address]:63356, method INVITE | tpot (9,098) |
| 110204 | 4 | 7,698 | T-Pot Honeytrap connection from [IP address] to port 2222 | tpot (7,698) |
| 110219 | 4 | 4,805 | T-Pot CiscoASA web activity from [IP address]: "GET / HTTP/1.1" 200 - | tpot (4,805) |
| 110101 | 3 | 1,786 | Cowrie SSH connection from [IP address]. | tpot (1,786) |
| 110223 | 5 | 1,367 | T-Pot HoneyAML received GET request from [IP address] to /fetch on port 3000. | tpot (1,367) |
| 110102 | 5 | 1,005 | Cowrie failed login from [IP address] using username root. | tpot (1,005) |
| 110201 | 4 | 533 | T-Pot Dionaea pptpd connection from [IP address] to port 1723 | tpot (533) |
| 110216 | 4 | 308 | T-Pot Mailoney received SMTP command from [IP address]: EHLO User  | tpot (308) |
| 533 | 7 | 241 | Listened ports status (netstat) changed (new port opened or closed). | tpot (240), wazuh (1) |
| 5501 | 3 | 234 | PAM: Login session opened. | tpot (203), wazuh (31) |
| 5502 | 3 | 213 | PAM: Login session closed. | tpot (184), wazuh (29) |
| 110104 | 7 | 190 | Cowrie captured a command from [IP address]: config terminal | tpot (190) |
| 110209 | 5 | 157 | T-Pot Conpot snmp event from [IP address]: SNMPv2 Bulk | tpot (157) |
| 110217 | 7 | 132 | T-Pot Mailoney captured suspicious SMTP activity from [IP address]: AUTH LOGIN  | tpot (132) |
| 110221 | 7 | 121 | T-Pot CiscoASA detected configuration discovery from [IP address]: "GET /SETTINGS.CFG HTTP/1.1" 404 - | tpot (121) |
| 5715 | 3 | 109 | sshd: authentication success. | tpot (107), wazuh (2) |
| 110214 | 9 | 86 | T-Pot RDP honeypot detected a connection burst from [IP address]. | tpot (86) |
| 110215 | 4 | 71 | T-Pot MiniPrint event: connection, action open_conn, Connection opened | tpot (71) |
| 110220 | 8 | 70 | T-Pot CiscoASA captured a login request from [IP address]: "POST /login.cgi HTTP/1.1" 200 - | tpot (70) |
| 110103 | 10 | 62 | Cowrie accepted login from [IP address] using username root. | tpot (62) |
| 110212 | 10 | 58 | T-Pot Honeytrap detected repeated payload activity from [IP address]. | tpot (58) |
| 510 | 7 | 41 | Host-based anomaly detection event (rootcheck). | wazuh (40), tpot (1) |
| 110106 | 10 | 31 | Cowrie detected repeated failed logins from [IP address]. | tpot (31) |

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

- Artifacts observed: 2
- Known hashes: 2
- Uploaded or analyzed: 0
- Malicious detections: 0
- Suspicious detections: 0
- Lookup errors: 0

### Artifacts

| SHA-256 | Bytes | Status | Malicious | Suspicious | Undetected | VirusTotal |
|---|---:|---|---:|---:|---:|---|
| ae8d459595257f2f22c9d1ff74c4fb8a91643fad7899b57556496716692b904e | 55 | known | 0 | 0 | 60 | [Open](https://www.virustotal.com/gui/file/ae8d459595257f2f22c9d1ff74c4fb8a91643fad7899b57556496716692b904e) |
| 0db4656687a425c47d19000db866db52c7e415dbfaf6b5c651adcb9275ab23ca | 405 | known | 0 | 0 | 60 | [Open](https://www.virustotal.com/gui/file/0db4656687a425c47d19000db866db52c7e415dbfaf6b5c651adcb9275ab23ca) |

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
