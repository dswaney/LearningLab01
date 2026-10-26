# LearningLab01 Daily Threat Intelligence Report — 2026-10-26

Generated: 2026-10-26T13:15:05.058Z

Report window: 2026-10-25T13:15:05.035Z through 2026-10-26T13:15:05.035Z

> This report summarizes security telemetry and honeypot activity. An alert indicates that a rule matched observed activity; it does not automatically prove that a system was compromised.

## Executive Summary

| Metric | Count |
|---|---:|
| Wazuh alerts | 286,921 |
| Attack-related alerts | 55,962 |
| Honeypot interactions | 274,320 |
| Authentication failures | 3,211 |
| Authentication successes | 1,683 |
| Critical alerts | 348 |
| High alerts | 1,891 |
| T-Pot artifacts observed | 0 |
| Malicious artifact detections | 0 |

### Notable Observations

- 348 critical-severity alerts require priority review.
- 1,891 high-severity alerts should be reviewed after the critical queue.
- Authentication failures exceeded successful authentications by a ratio of 1.91:1.
- Country attribution currently covers only 0.36% of alerts. Country totals should be treated as partial telemetry.
- The most frequent rule was 110204: T-Pot Honeytrap connection from [IP address] to port 5909 (83,853 alerts).

## Wazuh Security Monitoring

### Alert Severity

| Severity | Alerts | Percentage |
|---|---:|---:|
| Critical | 348 | 0.12% |
| High | 1,891 | 0.66% |
| Medium | 3,800 | 1.32% |
| Low | 280,882 | 97.90% |
| Informational | 0 | 0.00% |

Severity represents the priority assigned by the Wazuh rule. Critical and high alerts should be investigated first, but repeated lower-severity events can also reveal scanning, credential attacks, or attacker preparation.

### Authentication Activity

- Authentication failures: 3,211
- Authentication successes: 1,683
- Failure-to-success ratio: 1.91:1

A successful authentication is not considered an attack by itself. Analysts should correlate successful logins with preceding failures, source addresses, usernames, target systems, and expected activity.

### Attack-Type Breakdown

| Category | Alerts | Percentage of attack-related alerts |
|---|---:|---:|
| Network attack | 47,335 | 84.58% |
| Payload delivery | 47,335 | 84.58% |
| Command execution | 3,253 | 5.81% |
| Authentication failure | 3,211 | 5.74% |
| Reconnaissance | 343 | 0.61% |
| Malware | 319 | 0.57% |
| SMTP attack | 87 | 0.16% |
| Network scan | 46 | 0.08% |
| Web attack | 36 | 0.06% |

> Category counts may overlap because one Wazuh alert can belong to multiple rule groups. The attack-related total counts each alert once.

### Country of Origin

Wazuh supplied country information for 1,044 alerts, representing 0.36% of all alerts.

| Country | Alerts | Percentage of all alerts | Relative volume |
|---|---:|---:|---|
| Unknown | 285,877 | 99.64% | Not geolocated |
| United Kingdom | 460 | 0.16% | ████████████████████ |
| Germany | 246 | 0.09% | ███████████ |
| Bulgaria | 130 | 0.05% | ██████ |
| Azerbaijan | 93 | 0.03% | ████ |
| United States | 90 | 0.03% | ████ |
| Netherlands | 12 | 0.00% | █ |
| Ukraine | 4 | 0.00% | █ |
| China | 3 | 0.00% | █ |
| Canada | 2 | 0.00% | █ |
| Australia | 1 | 0.00% | █ |
| Kazakhstan | 1 | 0.00% | █ |
| Republic of Lithuania | 1 | 0.00% | █ |
| Russia | 1 | 0.00% | █ |

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
| Credential Access | 34 |
| Command and Control | 32 |
| Execution | 13 |
| Impact | 11 |

### MITRE ATT&CK Techniques

| Technique | Alerts |
|---|---:|
| Valid Accounts | 291 |
| Remote Services | 97 |
| Brute Force | 34 |
| Ingress Tool Transfer | 32 |
| Command and Scripting Interpreter | 13 |
| Stored Data Manipulation | 11 |
| Disable or Modify Tools | 1 |

MITRE ATT&CK describes adversary behavior rather than declaring that an attack succeeded. These mappings help analysts connect individual alerts to possible attacker objectives and investigative hypotheses.

### Most Frequent Wazuh Rules

| Rule ID | Highest Level | Alerts | Description | Agents |
|---|---:|---:|---|---|
| 110204 | 4 | 83,853 | T-Pot Honeytrap connection from [IP address] to port 5909 | tpot (83,853) |
| 110213 | 4 | 67,108 | T-Pot RDP connection from [IP address] to port 3389. | tpot (67,108) |
| 110209 | 5 | 55,745 | T-Pot Conpot snmp event from [IP address]: SNMPv2 Bulk | tpot (55,745) |
| 110205 | 6 | 47,189 | T-Pot Honeytrap received a payload from [IP address] | tpot (47,189) |
| 110207 | 5 | 17,510 | T-Pot SentryPeer SIP activity from [IP address]:64232, method INVITE | tpot (17,510) |
| 110101 | 3 | 3,349 | Cowrie SSH connection from [IP address]. | tpot (3,349) |
| 110102 | 5 | 3,211 | Cowrie failed login from [IP address] using username enable. | tpot (3,211) |
| 110104 | 7 | 2,860 | Cowrie captured a command from [IP address]: ls /home; /bin/busybox BOTNET | tpot (2,860) |
| 110103 | 10 | 1,392 | Cowrie accepted login from [IP address] using username system. | tpot (1,392) |
| 110201 | 4 | 1,035 | T-Pot Dionaea pptpd connection from [IP address] to port 1723 | tpot (1,035) |
| 110219 | 4 | 787 | T-Pot CiscoASA web activity from [IP address]: "GET /+CSCOE+/logon.html HTTP/1.1" 302 - | tpot (787) |
| 110215 | 4 | 360 | T-Pot MiniPrint event: command_received, action request, Request received | tpot (360) |
| 110109 | 13 | 348 | Cowrie captured a destructive, persistence, or defense-evasion command from [IP address]: crontab -l | tpot (348) |
| 110105 | 12 | 274 | Cowrie captured a file download from [IP address]. | tpot (274) |
| 533 | 7 | 217 | Listened ports status (netstat) changed (new port opened or closed). | tpot (217) |
| 5501 | 3 | 194 | PAM: Login session opened. | tpot (192), wazuh (2) |
| 110221 | 7 | 185 | T-Pot CiscoASA detected configuration discovery from [IP address]: "GET /appGet.cgi?hook=get_cfg_clientlist() HTTP/1.1" 404 - | tpot (185) |
| 5502 | 3 | 158 | PAM: Login session closed. | tpot (156), wazuh (2) |
| 110212 | 10 | 146 | T-Pot Honeytrap detected repeated payload activity from [IP address]. | tpot (146) |
| 110216 | 4 | 124 | T-Pot Mailoney received SMTP command from [IP address]: EHLO [IP address]  | tpot (124) |
| 203 | 9 | 122 | Agent event queue is full. Events may be lost. | tpot (122) |
| 202 | 7 | 119 | Agent event queue is 90% full. | tpot (119) |
| 205 | 3 | 119 | Agent event queue is back to normal load. | tpot (119) |
| 5715 | 3 | 97 | sshd: authentication success. | tpot (96), wazuh (1) |
| 110217 | 7 | 87 | T-Pot Mailoney captured suspicious SMTP activity from [IP address]: AUTH LOGIN  | tpot (87) |
| 110220 | 8 | 84 | T-Pot CiscoASA captured a login request from [IP address]: "POST /login.cgi HTTP/1.1" 200 - | tpot (84) |
| 110214 | 9 | 45 | T-Pot RDP honeypot detected a connection burst from [IP address]. | tpot (45) |
| 510 | 7 | 41 | Host-based anomaly detection event (rootcheck). | wazuh (40), tpot (1) |
| 110223 | 5 | 36 | T-Pot HoneyAML received  request from  to  on port . | tpot (36) |
| 110106 | 10 | 34 | Cowrie detected repeated failed logins from [IP address]. | tpot (34) |
| 110107 | 12 | 32 | Cowrie captured a probable payload-retrieval command from $(src_ip): $(input) | tpot (32) |
| 110208 | 7 | 23 | T-Pot SentryPeer detected SIP scanner friendly-scanner from [IP address]:5096 | tpot (23) |
| 110108 | 12 | 13 | Cowrie captured suspicious execution or staging activity from [IP address]: >/var/run/.x&&cd /var/run;>/mnt/.x&&cd /mnt;>/usr/.x&&cd /usr;>/dev/.x&&cd /dev;>/dev/shm/.x&&cd /dev/shm;>/tmp/.x&&cd /tmp;>/var/.x&&cd /var;/bin/busybox echo -e '\x55\x4e\x50\x4c\x53\x5a' | tpot (13) |
| 592 | 8 | 11 | Log file size reduced. | tpot (11) |
| 11 | 4 | 3 | Unknown | tpot (3) |
| 110222 | 9 | 2 | T-Pot CiscoASA detected repeated web requests from one source. | tpot (2) |
| 19004 | 7 | 2 | SCA summary: CIS Ubuntu Linux 24.04 LTS Benchmark v1.0.0.: Score less than 50% (47) | tpot (2) |
| 110211 | 9 | 1 | T-Pot Dionaea detected a connection burst from [IP address]. | tpot (1) |
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
