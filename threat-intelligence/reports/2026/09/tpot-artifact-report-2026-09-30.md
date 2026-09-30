# LearningLab01 Daily Threat Intelligence Report — 2026-09-30

Generated: 2026-09-30T13:15:05.052Z

Report window: 2026-09-29T13:15:05.024Z through 2026-09-30T13:15:05.024Z

> This report summarizes security telemetry and honeypot activity. An alert indicates that a rule matched observed activity; it does not automatically prove that a system was compromised.

## Executive Summary

| Metric | Count |
|---|---:|
| Wazuh alerts | 217,038 |
| Attack-related alerts | 34,989 |
| Honeypot interactions | 195,565 |
| Authentication failures | 8,181 |
| Authentication successes | 681 |
| Critical alerts | 253 |
| High alerts | 801 |
| T-Pot artifacts observed | 0 |
| Malicious artifact detections | 0 |

### Notable Observations

- 253 critical-severity alerts require priority review.
- 801 high-severity alerts should be reviewed after the critical queue.
- Authentication failures exceeded successful authentications by a ratio of 12.01:1.
- Country attribution currently covers only 2.45% of alerts. Country totals should be treated as partial telemetry.
- The most frequent rule was 110209: T-Pot Conpot snmp event from [IP address]: SNMPv2 Bulk (103,227 alerts).

## Wazuh Security Monitoring

### Alert Severity

| Severity | Alerts | Percentage |
|---|---:|---:|
| Critical | 253 | 0.12% |
| High | 801 | 0.37% |
| Medium | 3,211 | 1.48% |
| Low | 212,773 | 98.03% |
| Informational | 0 | 0.00% |

Severity represents the priority assigned by the Wazuh rule. Critical and high alerts should be investigated first, but repeated lower-severity events can also reveal scanning, credential attacks, or attacker preparation.

### Authentication Activity

- Authentication failures: 8,181
- Authentication successes: 681
- Failure-to-success ratio: 12.01:1

A successful authentication is not considered an attack by itself. Analysts should correlate successful logins with preceding failures, source addresses, usernames, target systems, and expected activity.

### Attack-Type Breakdown

| Category | Alerts | Percentage of attack-related alerts |
|---|---:|---:|
| Network attack | 23,089 | 65.99% |
| Payload delivery | 23,089 | 65.99% |
| Authentication failure | 8,181 | 23.38% |
| Command execution | 2,599 | 7.43% |
| Reconnaissance | 328 | 0.94% |
| Malware | 176 | 0.50% |
| SMTP attack | 101 | 0.29% |
| Web attack | 67 | 0.19% |
| Network scan | 62 | 0.18% |

> Category counts may overlap because one Wazuh alert can belong to multiple rule groups. The attack-related total counts each alert once.

### Country of Origin

Wazuh supplied country information for 5,322 alerts, representing 2.45% of all alerts.

| Country | Alerts | Percentage of all alerts | Relative volume |
|---|---:|---:|---|
| Unknown | 211,716 | 97.55% | Not geolocated |
| Republic of Moldova | 2,164 | 1.00% | ████████████████████ |
| Germany | 2,017 | 0.93% | ███████████████████ |
| New Zealand | 648 | 0.30% | ██████ |
| United Kingdom | 204 | 0.09% | ██ |
| United States | 141 | 0.06% | █ |
| Russia | 28 | 0.01% | █ |
| Nigeria | 20 | 0.01% | █ |
| China | 15 | 0.01% | █ |
| Netherlands | 13 | 0.01% | █ |
| Turkey | 11 | 0.01% | █ |
| Ukraine | 9 | 0.00% | █ |
| Austria | 6 | 0.00% | █ |
| Denmark | 6 | 0.00% | █ |
| France | 6 | 0.00% | █ |
| Malta | 6 | 0.00% | █ |
| Palestine | 6 | 0.00% | █ |
| Canada | 3 | 0.00% | █ |
| Iraq | 3 | 0.00% | █ |
| Japan | 3 | 0.00% | █ |

> Relative-volume bars compare only countries with known geographic attribution. Unknown alerts are excluded from the bar scale.

> Geolocation is approximate. VPNs, proxies, cloud providers, compromised hosts, carrier networks, and incomplete GeoIP coverage can make the apparent country different from the attacker’s location.

### MITRE ATT&CK Tactics

| Tactic | Alerts |
|---|---:|
| Initial Access | 303 |
| Defense Evasion | 292 |
| Persistence | 291 |
| Privilege Escalation | 291 |
| Credential Access | 123 |
| Lateral Movement | 97 |
| Execution | 32 |
| Command and Control | 16 |
| Impact | 14 |

### MITRE ATT&CK Techniques

| Technique | Alerts |
|---|---:|
| Valid Accounts | 291 |
| Brute Force | 123 |
| Remote Services | 97 |
| Command and Scripting Interpreter | 32 |
| Ingress Tool Transfer | 16 |
| Stored Data Manipulation | 14 |
| Exploit Public-Facing Application | 12 |
| Disable or Modify Tools | 1 |

MITRE ATT&CK describes adversary behavior rather than declaring that an attack succeeded. These mappings help analysts connect individual alerts to possible attacker objectives and investigative hypotheses.

### Most Frequent Wazuh Rules

| Rule ID | Highest Level | Alerts | Description | Agents |
|---|---:|---:|---|---|
| 110209 | 5 | 103,227 | T-Pot Conpot snmp event from [IP address]: SNMPv2 Bulk | tpot (103,227) |
| 110213 | 4 | 34,918 | T-Pot RDP connection from [IP address] to port 3389. | tpot (34,918) |
| 110205 | 6 | 22,965 | T-Pot Honeytrap received a payload from [IP address] | tpot (22,965) |
| 110204 | 4 | 12,874 | T-Pot Honeytrap connection from [IP address] to port 5908 | tpot (12,874) |
| 110207 | 5 | 12,827 | T-Pot SentryPeer SIP activity from [IP address]:64859, method INVITE | tpot (12,827) |
| 110101 | 3 | 9,094 | Cowrie SSH connection from [IP address]. | tpot (9,094) |
| 110102 | 5 | 8,181 | Cowrie failed login from [IP address] using username root. | tpot (8,181) |
| 110219 | 4 | 5,149 | T-Pot CiscoASA web activity from [IP address]: "GET / HTTP/1.1" 200 - | tpot (5,149) |
| 110201 | 4 | 2,677 | T-Pot Dionaea mssqld connection from [IP address] to port 1433 | tpot (2,677) |
| 110104 | 7 | 2,334 | Cowrie captured a command from [IP address]: ls /home; /bin/busybox BOTNET | tpot (2,334) |
| 110103 | 10 | 390 | Cowrie accepted login from [IP address] using username enable. | tpot (390) |
| 110216 | 4 | 260 | T-Pot Mailoney received SMTP command from [IP address]: EHLO User  | tpot (260) |
| 110109 | 13 | 241 | Cowrie captured a destructive, persistence, or defense-evasion command from [IP address]: cd ~ && rm -rf .ssh && mkdir .ssh && echo "ssh-rsa AAAAB3NzaC1yc2EAAAABJQAAAQEArDp4cun2lhr4KUhBGE7VvAcwdli2a8dbnrTOrbMz1+5O73fcBOx8NVbUT0bUanUV9tJ2/9p7+vD0EpZ3Tz/+0kX34uAx1RV/75GVOmNx+9EuWOnvNoaJe0QXxziIg9eLBHpgLMuakb5+BgTFB+rKJAw9u9FSTDengvS8hX1kNFS4Mjux0hJOK8rvcEmPecjdySYMb66nylAKGwCEE6WEQHmd1mUPgHwGQ0hWCwsQk13yCGPK5w6hYp5zYkFnvlC8hGmd4Ww+u97k6pfTGTUbJk14ujvcD9iUKQTTWYYjIIu5PmUux5bsZ0R4WFwdIe6+i6rBLAsPKgAySVKPRK+oRw== mdrfckr">>.ssh/authorized_keys && chmod -R go= ~/.ssh && cd ~ | tpot (241) |
| 533 | 7 | 238 | Listened ports status (netstat) changed (new port opened or closed). | tpot (237), wazuh (1) |
| 5501 | 3 | 194 | PAM: Login session opened. | tpot (192), wazuh (2) |
| 203 | 9 | 170 | Agent event queue is full. Events may be lost. | tpot (170) |
| 5502 | 3 | 152 | PAM: Login session closed. | tpot (151), wazuh (1) |
| 110105 | 12 | 140 | Cowrie captured a file download from [IP address]. | tpot (140) |
| 110221 | 7 | 132 | T-Pot CiscoASA detected configuration discovery from [IP address]: "GET /appGet.cgi?hook=get_cfg_clientlist() HTTP/1.1" 404 - | tpot (132) |
| 110212 | 10 | 124 | T-Pot Honeytrap detected repeated payload activity from [IP address]. | tpot (124) |
| 110106 | 10 | 123 | Cowrie detected repeated failed logins from [IP address]. | tpot (123) |
| 110217 | 7 | 101 | T-Pot Mailoney captured suspicious SMTP activity from [IP address]: AUTH LOGIN  | tpot (101) |
| 5715 | 3 | 97 | sshd: authentication success. | tpot (96), wazuh (1) |
| 110215 | 4 | 77 | T-Pot MiniPrint event: connection, action open_conn, Connection opened | tpot (77) |
| 110223 | 5 | 66 | T-Pot HoneyAML received  request from  to  on port . | tpot (66) |
| 110220 | 8 | 60 | T-Pot CiscoASA captured a login request from [IP address]: "POST /login.cgi HTTP/1.1" 200 - | tpot (60) |
| 110214 | 9 | 52 | T-Pot RDP honeypot detected a connection burst from [IP address]. | tpot (52) |
| 510 | 7 | 41 | Host-based anomaly detection event (rootcheck). | wazuh (40), tpot (1) |
| 110208 | 7 | 30 | T-Pot SentryPeer detected SIP scanner Friendly-Scanner/1.1 from [IP address]:51336 | tpot (30) |
| 110108 | 12 | 20 | Cowrie captured suspicious execution or staging activity from $(src_ip): $(input) | tpot (20) |
| 110225 | 13 | 12 | T-Pot HoneyAML detected a probable remote-code-execution and payload-delivery attempt from [IP address]. | tpot (12) |
| 592 | 8 | 11 | Log file size reduced. | tpot (11) |
| 110211 | 9 | 10 | T-Pot Dionaea detected a connection burst from [IP address]. | tpot (10) |
| 202 | 7 | 9 | Agent event queue is 90% full. | tpot (9) |
| 205 | 3 | 9 | Agent event queue is back to normal load. | tpot (9) |
| 2904 | 7 | 8 | Dpkg (Debian Package) half configured. | wazuh (8) |
| 2902 | 7 | 5 | New dpkg (Debian Package) installed. | wazuh (5) |
| 110107 | 12 | 4 | Cowrie captured a probable payload-retrieval command from [IP address]: tftp -h \|\| echo ZXC10057 | tpot (4) |
| 110222 | 9 | 3 | T-Pot CiscoASA detected repeated web requests from one source. | tpot (3) |
| 550 | 7 | 3 | Integrity checksum changed. | wazuh (3) |
| 19004 | 7 | 2 | SCA summary: CIS Ubuntu Linux 24.04 LTS Benchmark v1.0.0.: Score less than 50% (47) | tpot (2) |
| 11 | 4 | 1 | Unknown | tpot (1) |
| 110224 | 7 | 1 | T-Pot HoneyAML received an HTTP POST from [IP address] to /mcp. | tpot (1) |
| 19010 | 3 | 1 | CIS Ubuntu Linux 24.04 LTS Benchmark v1.0.0.: Ensure nftables default deny firewall policy.: Status changed from failed to passed | tpot (1) |
| 19011 | 9 | 1 | CIS Ubuntu Linux 24.04 LTS Benchmark v1.0.0.: Ensure nftables default deny firewall policy.: Status changed from passed to failed | tpot (1) |
| 503 | 3 | 1 | Wazuh agent started. | tpot (1) |
| 506 | 3 | 1 | Wazuh agent stopped. | tpot (1) |
| 591 | 3 | 1 | Log file rotated. | tpot (1) |
| 86003 | 3 | 1 | Docker: Error message | tpot (1) |

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
