# LearningLab01 Daily Threat Intelligence Report â€” 2026-09-19

Generated: 2026-09-19T16:12:54.565Z

Report window: 2026-09-18T16:12:50.314Z through 2026-09-19T16:12:50.314Z

> This report summarizes security telemetry and honeypot activity. An alert indicates that a rule matched observed activity; it does not automatically prove that a system was compromised.

## Executive Summary

| Metric | Count |
|---|---:|
| Wazuh alerts | 179,094 |
| Attack-related alerts | 17,932 |
| Honeypot interactions | 172,468 |
| Authentication failures | 2,513 |
| Authentication successes | 338 |
| Critical alerts | 13 |
| High alerts | 155 |
| New Wazuh rule detections | 0 |
| T-Pot artifacts observed | 0 |
| Malicious artifact detections | 0 |

### Notable Observations

- 13 critical-severity alerts require priority review.
- 155 high-severity alerts should be reviewed after the critical queue.
- Authentication failures exceeded successful authentications by a ratio of 7.43:1.
- Country attribution currently covers only 1.65% of alerts. Country totals should be treated as partial telemetry.
- The most frequent rule was 110213: T-Pot RDP connection from [IP address] to port 3389. (99,243 alerts).

## Wazuh Security Monitoring

### Alert Severity

| Severity | Alerts | Percentage |
|---|---:|---:|
| Critical | 13 | 0.01% |
| High | 155 | 0.09% |
| Medium | 1,085 | 0.61% |
| Low | 177,841 | 99.30% |
| Informational | 0 | 0.00% |

Severity represents the priority assigned by the Wazuh rule. Critical and high alerts should be investigated first, but repeated lower-severity events can also reveal scanning, credential attacks, or attacker preparation.

### Authentication Activity

- Authentication failures: 2,513
- Authentication successes: 338
- Failure-to-success ratio: 7.43:1

A successful authentication is not considered an attack by itself. Analysts should correlate successful logins with preceding failures, source addresses, usernames, target systems, and expected activity.

### Attack-Type Breakdown

| Category | Alerts | Percentage of attack-related alerts |
|---|---:|---:|
| Network attack | 14,513 | 80.93% |
| Payload delivery | 14,513 | 80.93% |
| Authentication failure | 2,513 | 14.01% |
| Reconnaissance | 403 | 2.25% |
| Command execution | 297 | 1.66% |
| Network scan | 266 | 1.48% |
| Malware | 44 | 0.25% |
| Web attack | 29 | 0.16% |
| SMTP attack | 6 | 0.03% |

> Category counts may overlap because one Wazuh alert can belong to multiple rule groups. The attack-related total counts each alert once.

### Country of Origin

Wazuh supplied country information for 2,948 alerts, representing 1.65% of all alerts.

| Country | Alerts | Percentage of all alerts | Relative volume |
|---|---:|---:|---|
| Unknown | 176,146 | 98.35% | Not geolocated |
| New Zealand | 2,648 | 1.48% | â–ˆâ–ˆâ–ˆâ–ˆâ–ˆâ–ˆâ–ˆâ–ˆâ–ˆâ–ˆâ–ˆâ–ˆâ–ˆâ–ˆâ–ˆâ–ˆâ–ˆâ–ˆâ–ˆâ–ˆ |
| United Kingdom | 174 | 0.10% | â–ˆ |
| United States | 62 | 0.03% | â–ˆ |
| Russia | 26 | 0.01% | â–ˆ |
| Denmark | 6 | 0.00% | â–ˆ |
| Sweden | 6 | 0.00% | â–ˆ |
| China | 4 | 0.00% | â–ˆ |
| Turkey | 4 | 0.00% | â–ˆ |
| France | 3 | 0.00% | â–ˆ |
| Japan | 3 | 0.00% | â–ˆ |
| Romania | 3 | 0.00% | â–ˆ |
| Slovakia | 3 | 0.00% | â–ˆ |
| Spain | 3 | 0.00% | â–ˆ |
| Belgium | 1 | 0.00% | â–ˆ |
| Germany | 1 | 0.00% | â–ˆ |
| Iran | 1 | 0.00% | â–ˆ |

> Relative-volume bars compare only countries with known geographic attribution. Unknown alerts are excluded from the bar scale.

> Geolocation is approximate. VPNs, proxies, cloud providers, compromised hosts, carrier networks, and incomplete GeoIP coverage can make the apparent country different from the attackerâ€™s location.

### MITRE ATT&CK Tactics

| Tactic | Alerts |
|---|---:|
| Initial Access | 285 |
| Defense Evasion | 274 |
| Persistence | 273 |
| Privilege Escalation | 273 |
| Lateral Movement | 91 |
| Credential Access | 37 |
| Execution | 35 |
| Impact | 18 |
| Command and Control | 15 |

### MITRE ATT&CK Techniques

| Technique | Alerts |
|---|---:|
| Valid Accounts | 273 |
| Remote Services | 91 |
| Brute Force | 37 |
| Command and Scripting Interpreter | 35 |
| Stored Data Manipulation | 18 |
| Ingress Tool Transfer | 15 |
| Exploit Public-Facing Application | 12 |
| Disable or Modify Tools | 1 |

MITRE ATT&CK describes adversary behavior rather than declaring that an attack succeeded. These mappings help analysts connect individual alerts to possible attacker objectives and investigative hypotheses.

### Most Frequent Wazuh Rules

The table shows the 25 most frequent rules from 44 distinct rule IDs evaluated for historical comparison.

| Rule ID | Highest Level | Severity | Alerts | Description | Agents |
|---|---:|---|---:|---|---|
| 110213 | 4 | Low | 99,243 | T-Pot RDP connection from [IP address] to port 3389. | tpot (99,243) |
| 110207 | 5 | Low | 46,899 | T-Pot SentryPeer SIP activity from [IP address]:6280, method ACK | tpot (46,899) |
| 110205 | 6 | Low | 14,492 | T-Pot Honeytrap received a payload from [IP address] | tpot (14,492) |
| 110204 | 4 | Low | 8,024 | T-Pot Honeytrap connection from [IP address] to port 5909 | tpot (8,024) |
| 110101 | 3 | Low | 2,881 | Cowrie SSH connection from [IP address]. | tpot (2,881) |
| 110219 | 4 | Low | 2,800 | T-Pot CiscoASA web activity from [IP address]: "GET / HTTP/1.1" 200 - | tpot (2,800) |
| 110102 | 5 | Low | 2,513 | Cowrie failed login from [IP address] using username root. | tpot (2,513) |
| 110201 | 4 | Low | 314 | T-Pot Dionaea pptpd connection from [IP address] to port 1723 | tpot (314) |
| 110104 | 7 | Medium | 270 | Cowrie captured a command from [IP address]: uname -s -v -n -r -m | tpot (270) |
| 110214 | 9 | Medium | 263 | T-Pot RDP honeypot detected a connection burst from [IP address]. | tpot (263) |
| 533 | 7 | Medium | 191 | Listened ports status (netstat) changed (new port opened or closed). | tpot (190), wazuh (1) |
| 5501 | 3 | Low | 182 | PAM: Login session opened. | tpot (180), wazuh (2) |
| 5502 | 3 | Low | 170 | PAM: Login session closed. | tpot (169), wazuh (1) |
| 110221 | 7 | Medium | 106 | T-Pot CiscoASA detected configuration discovery from [IP address]: "GET /appGet.cgi?hook=get_cfg_clientlist() HTTP/1.1" 404 - | tpot (106) |
| 5715 | 3 | Low | 91 | sshd: authentication success. | tpot (90), wazuh (1) |
| 110103 | 10 | High | 65 | Cowrie accepted login from [IP address] using username root. | tpot (65) |
| 110209 | 5 | Low | 59 | T-Pot Conpot snmp event from [IP address]: SNMPv2 Bulk | tpot (59) |
| 110216 | 4 | Low | 58 | T-Pot Mailoney received SMTP command from [IP address]:   | tpot (58) |
| 110215 | 4 | Low | 57 | T-Pot MiniPrint event: command_received, action request, Request received | tpot (57) |
| 110220 | 8 | Medium | 57 | T-Pot CiscoASA captured a login request from [IP address]: "POST /login.cgi HTTP/1.1" 200 - | tpot (57) |
| 2904 | 7 | Medium | 47 | Dpkg (Debian Package) half configured. | tpot (24), wazuh (23) |
| 510 | 7 | Medium | 41 | Host-based anomaly detection event (rootcheck). | wazuh (40), tpot (1) |
| 110106 | 10 | High | 37 | Cowrie detected repeated failed logins from [IP address]. | tpot (37) |
| 2902 | 7 | Medium | 30 | New dpkg (Debian Package) installed. | tpot (15), wazuh (15) |
| 110223 | 5 | Low | 29 | T-Pot HoneyAML received  request from  to  on port . | tpot (29) |

### New or Previously Unseen Detections

Historical comparison information was unavailable for this report.

_No rules are classified as newly detected for this report._

> Historical novelty is based on stored daily rule IDs. A rule can be new to this reporting baseline without being a newly created Wazuh rule or a newly discovered attack technique.

### SOC Analyst Learning Notes

1. Begin with critical and high alerts, but validate the underlying event.
2. Determine whether the event represents scanning, attempted access, payload delivery, execution, persistence, or impact.
3. Correlate source IP, username, target, timestamp, and related alerts.
4. Check whether a successful login followed repeated failures.
5. Separate honeypot interaction from activity against production assets.
6. For a newly observed rule, verify whether the change came from attacker behavior, new log coverage, or a Wazuh rule/configuration update.
7. Document evidence supporting both malicious and benign explanations.
8. Escalate based on confirmed risk, affected assets, and confidenceâ€”not alert volume alone.

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
| No artifacts observed | â€” | â€” | â€” | â€” | â€” | â€” |

## Security Onion Network Monitoring

_Planned integration._

This section will eventually contain Suricata alerts, Zeek observations, network attack types, source-country information, targeted services, new network behaviors, and correlations with Wazuh endpoint alerts.

## Report Limitations

- Alert counts represent rule matches, not necessarily unique attackers.
- Attack-category counts may overlap.
- Historical novelty is based on rule IDs stored by this reporting pipeline.
- A new rule detection may result from newly added telemetry or rule changes.
- Honeypot traffic is intentionally exposed and is not equivalent to a compromise of a production system.
- GeoIP attribution is approximate and currently has incomplete coverage.
- VirusTotal results can change as vendors update their detections.

Generated automatically by the LearningLab01 threat-intelligence pipeline.
