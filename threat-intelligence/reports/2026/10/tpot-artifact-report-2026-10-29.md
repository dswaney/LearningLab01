# LearningLab01 Daily Threat Intelligence Report — 2026-10-29

Generated: 2026-10-29T13:15:05.054Z

Report window: 2026-10-28T13:15:05.028Z through 2026-10-29T13:15:05.028Z

> This report summarizes security telemetry and honeypot activity. An alert indicates that a rule matched observed activity; it does not automatically prove that a system was compromised.

## Executive Summary

| Metric | Count |
|---|---:|
| Wazuh alerts | 389,929 |
| Attack-related alerts | 48,979 |
| Honeypot interactions | 349,990 |
| Authentication failures | 17,505 |
| Authentication successes | 599 |
| Critical alerts | 329 |
| High alerts | 975 |
| T-Pot artifacts observed | 0 |
| Malicious artifact detections | 0 |

### Notable Observations

- 329 critical-severity alerts require priority review.
- 975 high-severity alerts should be reviewed after the critical queue.
- Authentication failures exceeded successful authentications by a ratio of 29.22:1.
- Country attribution currently covers only 0.10% of alerts. Country totals should be treated as partial telemetry.
- The most frequent rule was 110207: T-Pot SentryPeer SIP activity from [IP address]:53021, method INVITE (149,211 alerts).

## Wazuh Security Monitoring

### Alert Severity

| Severity | Alerts | Percentage |
|---|---:|---:|
| Critical | 329 | 0.08% |
| High | 975 | 0.25% |
| Medium | 2,781 | 0.71% |
| Low | 385,844 | 98.95% |
| Informational | 0 | 0.00% |

Severity represents the priority assigned by the Wazuh rule. Critical and high alerts should be investigated first, but repeated lower-severity events can also reveal scanning, credential attacks, or attacker preparation.

### Authentication Activity

- Authentication failures: 17,505
- Authentication successes: 599
- Failure-to-success ratio: 29.22:1

A successful authentication is not considered an attack by itself. Analysts should correlate successful logins with preceding failures, source addresses, usernames, target systems, and expected activity.

### Attack-Type Breakdown

| Category | Alerts | Percentage of attack-related alerts |
|---|---:|---:|
| Network attack | 27,689 | 56.53% |
| Payload delivery | 27,689 | 56.53% |
| Authentication failure | 17,505 | 35.74% |
| Command execution | 2,823 | 5.76% |
| Malware | 462 | 0.94% |
| Reconnaissance | 160 | 0.33% |
| Web attack | 112 | 0.23% |
| Network scan | 11 | 0.02% |
| SMTP attack | 0 | 0.00% |

> Category counts may overlap because one Wazuh alert can belong to multiple rule groups. The attack-related total counts each alert once.

### Country of Origin

Wazuh supplied country information for 382 alerts, representing 0.10% of all alerts.

| Country | Alerts | Percentage of all alerts | Relative volume |
|---|---:|---:|---|
| Unknown | 389,547 | 99.90% | Not geolocated |
| United Kingdom | 206 | 0.05% | ████████████████████ |
| United States | 84 | 0.02% | ████████ |
| Azerbaijan | 60 | 0.02% | ██████ |
| Ukraine | 10 | 0.00% | █ |
| Germany | 4 | 0.00% | █ |
| China | 3 | 0.00% | █ |
| Russia | 3 | 0.00% | █ |
| Canada | 2 | 0.00% | █ |
| Panama | 2 | 0.00% | █ |
| Slovakia | 2 | 0.00% | █ |
| Cameroon | 1 | 0.00% | █ |
| Kazakhstan | 1 | 0.00% | █ |
| Palestine | 1 | 0.00% | █ |
| Saudi Arabia | 1 | 0.00% | █ |
| Singapore | 1 | 0.00% | █ |
| Switzerland | 1 | 0.00% | █ |

> Relative-volume bars compare only countries with known geographic attribution. Unknown alerts are excluded from the bar scale.

> Geolocation is approximate. VPNs, proxies, cloud providers, compromised hosts, carrier networks, and incomplete GeoIP coverage can make the apparent country different from the attacker’s location.

### MITRE ATT&CK Tactics

| Tactic | Alerts |
|---|---:|
| Defense Evasion | 292 |
| Initial Access | 291 |
| Persistence | 291 |
| Privilege Escalation | 291 |
| Execution | 224 |
| Lateral Movement | 97 |
| Credential Access | 96 |
| Command and Control | 28 |
| Impact | 13 |

### MITRE ATT&CK Techniques

| Technique | Alerts |
|---|---:|
| Valid Accounts | 291 |
| Command and Scripting Interpreter | 224 |
| Remote Services | 97 |
| Brute Force | 96 |
| Ingress Tool Transfer | 28 |
| Stored Data Manipulation | 13 |
| Disable or Modify Tools | 1 |

MITRE ATT&CK describes adversary behavior rather than declaring that an attack succeeded. These mappings help analysts connect individual alerts to possible attacker objectives and investigative hypotheses.

### Most Frequent Wazuh Rules

| Rule ID | Highest Level | Alerts | Description | Agents |
|---|---:|---:|---|---|
| 110207 | 5 | 149,211 | T-Pot SentryPeer SIP activity from [IP address]:53021, method INVITE | tpot (149,211) |
| 110204 | 4 | 64,596 | T-Pot Honeytrap connection from [IP address] to port 5905 | tpot (64,596) |
| 110213 | 4 | 59,218 | T-Pot RDP connection from [IP address] to port 3389. | tpot (59,218) |
| 110209 | 5 | 47,726 | T-Pot Conpot snmp event from [IP address]: SNMPv2 Bulk | tpot (47,726) |
| 110205 | 6 | 27,580 | T-Pot Honeytrap received a payload from [IP address] | tpot (27,580) |
| 110101 | 3 | 18,233 | Cowrie SSH connection from [IP address]. | tpot (18,233) |
| 110102 | 5 | 17,505 | Cowrie failed login from [IP address] using username root. | tpot (17,505) |
| 110104 | 7 | 2,242 | Cowrie captured a command from [IP address]: whoami | tpot (2,242) |
| 110201 | 4 | 943 | T-Pot Dionaea pptpd connection from [IP address] to port 1723 | tpot (943) |
| 110109 | 13 | 329 | Cowrie captured a destructive, persistence, or defense-evasion command from [IP address]: cd ~ && rm -rf .ssh && mkdir .ssh && echo "ssh-rsa AAAAB3NzaC1yc2EAAAABJQAAAQEArDp4cun2lhr4KUhBGE7VvAcwdli2a8dbnrTOrbMz1+5O73fcBOx8NVbUT0bUanUV9tJ2/9p7+vD0EpZ3Tz/+0kX34uAx1RV/75GVOmNx+9EuWOnvNoaJe0QXxziIg9eLBHpgLMuakb5+BgTFB+rKJAw9u9FSTDengvS8hX1kNFS4Mjux0hJOK8rvcEmPecjdySYMb66nylAKGwCEE6WEQHmd1mUPgHwGQ0hWCwsQk13yCGPK5w6hYp5zYkFnvlC8hGmd4Ww+u97k6pfTGTUbJk14ujvcD9iUKQTTWYYjIIu5PmUux5bsZ0R4WFwdIe6+i6rBLAsPKgAySVKPRK+oRw== mdrfckr">>.ssh/authorized_keys && chmod -R go= ~/.ssh && cd ~ | tpot (329) |
| 110103 | 10 | 308 | Cowrie accepted login from [IP address] using username root. | tpot (308) |
| 533 | 7 | 240 | Listened ports status (netstat) changed (new port opened or closed). | tpot (240) |
| 110108 | 12 | 224 | Cowrie captured suspicious execution or staging activity from [IP address]: rm -f /tmp/.a | tpot (224) |
| 110105 | 12 | 210 | Cowrie captured a file download from [IP address]. | tpot (210) |
| 5501 | 3 | 194 | PAM: Login session opened. | tpot (192), wazuh (2) |
| 110219 | 4 | 176 | T-Pot CiscoASA web activity from [IP address]: "GET /+CSCOE+/logon.html HTTP/1.1" 302 - | tpot (176) |
| 5502 | 3 | 162 | PAM: Login session closed. | tpot (161), wazuh (1) |
| 110221 | 7 | 129 | T-Pot CiscoASA detected configuration discovery from [IP address]: "GET /appGet.cgi?hook=get_cfg_clientlist() HTTP/1.1" 404 - | tpot (129) |
| 110223 | 5 | 112 | T-Pot HoneyAML received  request from  to  on port . | tpot (112) |
| 110212 | 10 | 109 | T-Pot Honeytrap detected repeated payload activity from [IP address]. | tpot (109) |
| 5715 | 3 | 97 | sshd: authentication success. | tpot (96), wazuh (1) |
| 110106 | 10 | 96 | Cowrie detected repeated failed logins from [IP address]. | tpot (96) |
| 110220 | 8 | 76 | T-Pot CiscoASA captured a login request from [IP address]: "POST /login.cgi HTTP/1.1" 200 - | tpot (76) |
| 110215 | 4 | 59 | T-Pot MiniPrint event: connection, action open_conn, Connection opened | tpot (59) |
| 510 | 7 | 41 | Host-based anomaly detection event (rootcheck). | wazuh (40), tpot (1) |
| 110107 | 12 | 28 | Cowrie captured a probable payload-retrieval command from [IP address]: which wget | tpot (28) |
| 110216 | 4 | 24 | T-Pot Mailoney received SMTP command from [IP address]:   | tpot (24) |
| 110208 | 7 | 19 | T-Pot SentryPeer detected SIP scanner friendly-scanner from [IP address]:28536 | tpot (19) |
| 592 | 8 | 11 | Log file size reduced. | tpot (11) |
| 110214 | 9 | 6 | T-Pot RDP honeypot detected a connection burst from [IP address]. | tpot (6) |
| 110211 | 9 | 5 | T-Pot Dionaea detected a connection burst from [IP address]. | tpot (5) |
| 203 | 9 | 4 | Agent event queue is full. Events may be lost. | tpot (4) |
| 11 | 4 | 2 | Unknown | tpot (2) |
| 19004 | 7 | 2 | SCA summary: CIS Ubuntu Linux 24.04 LTS Benchmark v1.0.0.: Score less than 50% (47) | tpot (2) |
| 202 | 7 | 2 | Agent event queue is 90% full. | tpot (2) |
| 205 | 3 | 2 | Agent event queue is back to normal load. | tpot (2) |
| 550 | 7 | 2 | Integrity checksum changed. | tpot (1), wazuh (1) |
| 110222 | 9 | 1 | T-Pot CiscoASA detected repeated web requests from one source. | tpot (1) |
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
