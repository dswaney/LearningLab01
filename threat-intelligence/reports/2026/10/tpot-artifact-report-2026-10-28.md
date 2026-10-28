# LearningLab01 Daily Threat Intelligence Report — 2026-10-28

Generated: 2026-10-28T13:15:05.046Z

Report window: 2026-10-27T13:15:05.019Z through 2026-10-28T13:15:05.019Z

> This report summarizes security telemetry and honeypot activity. An alert indicates that a rule matched observed activity; it does not automatically prove that a system was compromised.

## Executive Summary

| Metric | Count |
|---|---:|
| Wazuh alerts | 297,269 |
| Attack-related alerts | 37,434 |
| Honeypot interactions | 266,862 |
| Authentication failures | 12,585 |
| Authentication successes | 804 |
| Critical alerts | 339 |
| High alerts | 1,136 |
| T-Pot artifacts observed | 0 |
| Malicious artifact detections | 0 |

### Notable Observations

- 339 critical-severity alerts require priority review.
- 1,136 high-severity alerts should be reviewed after the critical queue.
- Authentication failures exceeded successful authentications by a ratio of 15.65:1.
- Country attribution currently covers only 0.17% of alerts. Country totals should be treated as partial telemetry.
- The most frequent rule was 110209: T-Pot Conpot snmp event from [IP address]: SNMPv2 Bulk (85,571 alerts).

## Wazuh Security Monitoring

### Alert Severity

| Severity | Alerts | Percentage |
|---|---:|---:|
| Critical | 339 | 0.11% |
| High | 1,136 | 0.38% |
| Medium | 2,983 | 1.00% |
| Low | 292,811 | 98.50% |
| Informational | 0 | 0.00% |

Severity represents the priority assigned by the Wazuh rule. Critical and high alerts should be investigated first, but repeated lower-severity events can also reveal scanning, credential attacks, or attacker preparation.

### Authentication Activity

- Authentication failures: 12,585
- Authentication successes: 804
- Failure-to-success ratio: 15.65:1

A successful authentication is not considered an attack by itself. Analysts should correlate successful logins with preceding failures, source addresses, usernames, target systems, and expected activity.

### Attack-Type Breakdown

| Category | Alerts | Percentage of attack-related alerts |
|---|---:|---:|
| Network attack | 20,786 | 55.53% |
| Payload delivery | 20,786 | 55.53% |
| Authentication failure | 12,585 | 33.62% |
| Command execution | 2,634 | 7.04% |
| Malware | 405 | 1.08% |
| Reconnaissance | 385 | 1.03% |
| Network scan | 185 | 0.49% |
| Web attack | 89 | 0.24% |
| SMTP attack | 1 | 0.00% |

> Category counts may overlap because one Wazuh alert can belong to multiple rule groups. The attack-related total counts each alert once.

### Country of Origin

Wazuh supplied country information for 495 alerts, representing 0.17% of all alerts.

| Country | Alerts | Percentage of all alerts | Relative volume |
|---|---:|---:|---|
| Unknown | 296,774 | 99.83% | Not geolocated |
| United Kingdom | 184 | 0.06% | ████████████████████ |
| Bulgaria | 111 | 0.04% | ████████████ |
| Azerbaijan | 93 | 0.03% | ██████████ |
| United States | 82 | 0.03% | █████████ |
| Romania | 6 | 0.00% | █ |
| Slovakia | 6 | 0.00% | █ |
| Estonia | 4 | 0.00% | █ |
| Hong Kong | 3 | 0.00% | █ |
| Bosnia and Herzegovina | 2 | 0.00% | █ |
| Canada | 2 | 0.00% | █ |
| Iran | 1 | 0.00% | █ |
| Turkey | 1 | 0.00% | █ |

> Relative-volume bars compare only countries with known geographic attribution. Unknown alerts are excluded from the bar scale.

> Geolocation is approximate. VPNs, proxies, cloud providers, compromised hosts, carrier networks, and incomplete GeoIP coverage can make the apparent country different from the attacker’s location.

### MITRE ATT&CK Tactics

| Tactic | Alerts |
|---|---:|
| Defense Evasion | 292 |
| Initial Access | 291 |
| Persistence | 291 |
| Privilege Escalation | 291 |
| Execution | 156 |
| Lateral Movement | 97 |
| Credential Access | 92 |
| Impact | 11 |
| Command and Control | 2 |

### MITRE ATT&CK Techniques

| Technique | Alerts |
|---|---:|
| Valid Accounts | 291 |
| Command and Scripting Interpreter | 156 |
| Remote Services | 97 |
| Brute Force | 92 |
| Stored Data Manipulation | 11 |
| Ingress Tool Transfer | 2 |
| Disable or Modify Tools | 1 |

MITRE ATT&CK describes adversary behavior rather than declaring that an attack succeeded. These mappings help analysts connect individual alerts to possible attacker objectives and investigative hypotheses.

### Most Frequent Wazuh Rules

| Rule ID | Highest Level | Alerts | Description | Agents |
|---|---:|---:|---|---|
| 110209 | 5 | 85,571 | T-Pot Conpot snmp event from [IP address]: SNMPv2 Bulk | tpot (85,571) |
| 110213 | 4 | 79,084 | T-Pot RDP connection from [IP address] to port 3389. | tpot (79,084) |
| 110204 | 4 | 32,974 | T-Pot Honeytrap connection from [IP address] to port 5908 | tpot (32,974) |
| 110201 | 4 | 26,612 | T-Pot Dionaea mssqld connection from [IP address] to port 1433 | tpot (26,612) |
| 110207 | 5 | 20,942 | T-Pot SentryPeer SIP activity from [IP address]:55436, method INVITE | tpot (20,942) |
| 110205 | 6 | 20,660 | T-Pot Honeytrap received a payload from [IP address] | tpot (20,660) |
| 110101 | 3 | 13,503 | Cowrie SSH connection from [IP address]. | tpot (13,503) |
| 110102 | 5 | 12,585 | Cowrie failed login from [IP address] using username root. | tpot (12,585) |
| 110104 | 7 | 2,137 | Cowrie captured a command from [IP address]: &k`g&k\|zpkfq)ES[M | tpot (2,137) |
| 110103 | 10 | 513 | Cowrie accepted login from [IP address] using username lghkel	. | tpot (513) |
| 110109 | 13 | 339 | Cowrie captured a destructive, persistence, or defense-evasion command from [IP address]: cd ~ && rm -rf .ssh && mkdir .ssh && echo "ssh-rsa AAAAB3NzaC1yc2EAAAABJQAAAQEArDp4cun2lhr4KUhBGE7VvAcwdli2a8dbnrTOrbMz1+5O73fcBOx8NVbUT0bUanUV9tJ2/9p7+vD0EpZ3Tz/+0kX34uAx1RV/75GVOmNx+9EuWOnvNoaJe0QXxziIg9eLBHpgLMuakb5+BgTFB+rKJAw9u9FSTDengvS8hX1kNFS4Mjux0hJOK8rvcEmPecjdySYMb66nylAKGwCEE6WEQHmd1mUPgHwGQ0hWCwsQk13yCGPK5w6hYp5zYkFnvlC8hGmd4Ww+u97k6pfTGTUbJk14ujvcD9iUKQTTWYYjIIu5PmUux5bsZ0R4WFwdIe6+i6rBLAsPKgAySVKPRK+oRw== mdrfckr">>.ssh/authorized_keys && chmod -R go= ~/.ssh && cd ~ | tpot (339) |
| 110105 | 12 | 247 | Cowrie captured a file download from [IP address]. | tpot (247) |
| 533 | 7 | 239 | Listened ports status (netstat) changed (new port opened or closed). | tpot (239) |
| 110219 | 4 | 215 | T-Pot CiscoASA web activity from [IP address]: "GET /+CSCOE+/logon.html HTTP/1.1" 302 - | tpot (215) |
| 5501 | 3 | 194 | PAM: Login session opened. | tpot (192), wazuh (2) |
| 110221 | 7 | 180 | T-Pot CiscoASA detected configuration discovery from [IP address]: "GET /appGet.cgi?hook=get_cfg_clientlist() HTTP/1.1" 404 - | tpot (180) |
| 5502 | 3 | 172 | PAM: Login session closed. | tpot (170), wazuh (2) |
| 110108 | 12 | 156 | Cowrie captured suspicious execution or staging activity from [IP address]: chmod +x '/root/.16' | tpot (156) |
| 110212 | 10 | 126 | T-Pot Honeytrap detected repeated payload activity from [IP address]. | tpot (126) |
| 110211 | 9 | 120 | T-Pot Dionaea detected a connection burst from [IP address]. | tpot (120) |
| 110220 | 8 | 103 | T-Pot CiscoASA captured a login request from [IP address]: "POST /login.cgi HTTP/1.1" 200 - | tpot (103) |
| 5715 | 3 | 97 | sshd: authentication success. | tpot (96), wazuh (1) |
| 110106 | 10 | 92 | Cowrie detected repeated failed logins from [IP address]. | tpot (92) |
| 110223 | 5 | 85 | T-Pot HoneyAML received  request from  to  on port . | tpot (85) |
| 110214 | 9 | 65 | T-Pot RDP honeypot detected a connection burst from [IP address]. | tpot (65) |
| 110215 | 4 | 63 | T-Pot MiniPrint event: connection, action open_conn, Connection opened | tpot (63) |
| 510 | 7 | 41 | Host-based anomaly detection event (rootcheck). | wazuh (40), tpot (1) |
| 203 | 9 | 39 | Agent event queue is full. Events may be lost. | tpot (39) |
| 110216 | 4 | 38 | T-Pot Mailoney received SMTP command from [IP address]:  | tpot (38) |
| 110208 | 7 | 19 | T-Pot SentryPeer detected SIP scanner friendly-scanner from [IP address]:22337 | tpot (19) |
| 202 | 7 | 11 | Agent event queue is 90% full. | tpot (11) |
| 205 | 3 | 11 | Agent event queue is back to normal load. | tpot (11) |
| 592 | 8 | 11 | Log file size reduced. | tpot (11) |
| 2904 | 7 | 6 | Dpkg (Debian Package) half configured. | tpot (3), wazuh (3) |
| 110224 | 7 | 4 | T-Pot HoneyAML received an HTTP POST from [IP address] to /. | tpot (4) |
| 2902 | 7 | 4 | New dpkg (Debian Package) installed. | tpot (2), wazuh (2) |
| 110107 | 12 | 2 | Cowrie captured a probable payload-retrieval command from [IP address]: Origin: http://[IP address]:23 | tpot (2) |
| 19004 | 7 | 2 | SCA summary: CIS Ubuntu Linux 24.04 LTS Benchmark v1.0.0.: Score less than 50% (47) | tpot (2) |
| 11 | 4 | 1 | Unknown | tpot (1) |
| 110217 | 7 | 1 | T-Pot Mailoney captured suspicious SMTP activity from [IP address]: AUTH NTLM  | tpot (1) |
| 19010 | 3 | 1 | CIS Ubuntu Linux 24.04 LTS Benchmark v1.0.0.: Ensure nftables default deny firewall policy.: Status changed from failed to passed | tpot (1) |
| 19011 | 9 | 1 | CIS Ubuntu Linux 24.04 LTS Benchmark v1.0.0.: Ensure nftables default deny firewall policy.: Status changed from passed to failed | tpot (1) |
| 503 | 3 | 1 | Wazuh agent started. | tpot (1) |
| 506 | 3 | 1 | Wazuh agent stopped. | tpot (1) |
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
