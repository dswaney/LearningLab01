# LearningLab01 Daily Threat Intelligence Report — 2026-10-30

Generated: 2026-10-30T13:15:05.048Z

Report window: 2026-10-29T13:15:05.023Z through 2026-10-30T13:15:05.023Z

> This report summarizes security telemetry and honeypot activity. An alert indicates that a rule matched observed activity; it does not automatically prove that a system was compromised.

## Executive Summary

| Metric | Count |
|---|---:|
| Wazuh alerts | 260,016 |
| Attack-related alerts | 26,590 |
| Honeypot interactions | 243,275 |
| Authentication failures | 4,567 |
| Authentication successes | 979 |
| Critical alerts | 557 |
| High alerts | 1,360 |
| T-Pot artifacts observed | 0 |
| Malicious artifact detections | 0 |

### Notable Observations

- 557 critical-severity alerts require priority review.
- 1,360 high-severity alerts should be reviewed after the critical queue.
- Authentication failures exceeded successful authentications by a ratio of 4.66:1.
- Country attribution currently covers only 0.15% of alerts. Country totals should be treated as partial telemetry.
- The most frequent rule was 110209: T-Pot Conpot snmp event from [IP address]: SNMPv2 Bulk (87,622 alerts).

## Wazuh Security Monitoring

### Alert Severity

| Severity | Alerts | Percentage |
|---|---:|---:|
| Critical | 557 | 0.21% |
| High | 1,360 | 0.52% |
| Medium | 4,263 | 1.64% |
| Low | 253,836 | 97.62% |
| Informational | 0 | 0.00% |

Severity represents the priority assigned by the Wazuh rule. Critical and high alerts should be investigated first, but repeated lower-severity events can also reveal scanning, credential attacks, or attacker preparation.

### Authentication Activity

- Authentication failures: 4,567
- Authentication successes: 979
- Failure-to-success ratio: 4.66:1

A successful authentication is not considered an attack by itself. Analysts should correlate successful logins with preceding failures, source addresses, usernames, target systems, and expected activity.

### Attack-Type Breakdown

| Category | Alerts | Percentage of attack-related alerts |
|---|---:|---:|
| Network attack | 16,212 | 60.97% |
| Payload delivery | 16,212 | 60.97% |
| Authentication failure | 4,567 | 17.18% |
| Command execution | 4,338 | 16.31% |
| Malware | 447 | 1.68% |
| Reconnaissance | 191 | 0.72% |
| Web attack | 86 | 0.32% |
| Network scan | 47 | 0.18% |
| SMTP attack | 1 | 0.00% |

> Category counts may overlap because one Wazuh alert can belong to multiple rule groups. The attack-related total counts each alert once.

### Country of Origin

Wazuh supplied country information for 396 alerts, representing 0.15% of all alerts.

| Country | Alerts | Percentage of all alerts | Relative volume |
|---|---:|---:|---|
| Unknown | 259,620 | 99.85% | Not geolocated |
| United Kingdom | 182 | 0.07% | ████████████████████ |
| United States | 101 | 0.04% | ███████████ |
| Azerbaijan | 63 | 0.02% | ███████ |
| Hong Kong | 20 | 0.01% | ██ |
| Ukraine | 13 | 0.00% | █ |
| Germany | 6 | 0.00% | █ |
| France | 5 | 0.00% | █ |
| China | 3 | 0.00% | █ |
| Hungary | 2 | 0.00% | █ |
| Netherlands | 1 | 0.00% | █ |

> Relative-volume bars compare only countries with known geographic attribution. Unknown alerts are excluded from the bar scale.

> Geolocation is approximate. VPNs, proxies, cloud providers, compromised hosts, carrier networks, and incomplete GeoIP coverage can make the apparent country different from the attacker’s location.

### MITRE ATT&CK Tactics

| Tactic | Alerts |
|---|---:|
| Initial Access | 294 |
| Defense Evasion | 292 |
| Persistence | 291 |
| Privilege Escalation | 291 |
| Lateral Movement | 97 |
| Execution | 83 |
| Credential Access | 79 |
| Impact | 11 |
| Command and Control | 3 |

### MITRE ATT&CK Techniques

| Technique | Alerts |
|---|---:|
| Valid Accounts | 291 |
| Remote Services | 97 |
| Command and Scripting Interpreter | 83 |
| Brute Force | 79 |
| Stored Data Manipulation | 11 |
| Exploit Public-Facing Application | 3 |
| Ingress Tool Transfer | 3 |
| Disable or Modify Tools | 1 |

MITRE ATT&CK describes adversary behavior rather than declaring that an attack succeeded. These mappings help analysts connect individual alerts to possible attacker objectives and investigative hypotheses.

### Most Frequent Wazuh Rules

| Rule ID | Highest Level | Alerts | Description | Agents |
|---|---:|---:|---|---|
| 110209 | 5 | 87,622 | T-Pot Conpot snmp event from [IP address]: SNMPv2 Bulk | tpot (87,622) |
| 110204 | 4 | 63,874 | T-Pot Honeytrap connection from [IP address] to port 5904 | tpot (63,874) |
| 110213 | 4 | 54,395 | T-Pot RDP connection from [IP address] to port 3389. | tpot (54,395) |
| 110207 | 5 | 19,539 | T-Pot SentryPeer SIP activity from [IP address]:55738, method INVITE | tpot (19,539) |
| 110205 | 6 | 16,065 | T-Pot Honeytrap received a payload from [IP address] | tpot (16,065) |
| 110101 | 3 | 5,942 | Cowrie SSH connection from [IP address]. | tpot (5,942) |
| 110102 | 5 | 4,567 | Cowrie failed login from [IP address] using username root. | tpot (4,567) |
| 110104 | 7 | 3,704 | Cowrie captured a command from [IP address]: cat /proc/cpuinfo \| grep model \| grep name \| wc -l | tpot (3,704) |
| 110201 | 4 | 905 | T-Pot Dionaea pptpd connection from [IP address] to port 1723 | tpot (905) |
| 110103 | 10 | 688 | Cowrie accepted login from [IP address] using username intel. | tpot (688) |
| 110109 | 13 | 554 | Cowrie captured a destructive, persistence, or defense-evasion command from [IP address]: cd ~ && rm -rf .ssh && mkdir .ssh && echo "ssh-rsa AAAAB3NzaC1yc2EAAAABJQAAAQEArDp4cun2lhr4KUhBGE7VvAcwdli2a8dbnrTOrbMz1+5O73fcBOx8NVbUT0bUanUV9tJ2/9p7+vD0EpZ3Tz/+0kX34uAx1RV/75GVOmNx+9EuWOnvNoaJe0QXxziIg9eLBHpgLMuakb5+BgTFB+rKJAw9u9FSTDengvS8hX1kNFS4Mjux0hJOK8rvcEmPecjdySYMb66nylAKGwCEE6WEQHmd1mUPgHwGQ0hWCwsQk13yCGPK5w6hYp5zYkFnvlC8hGmd4Ww+u97k6pfTGTUbJk14ujvcD9iUKQTTWYYjIIu5PmUux5bsZ0R4WFwdIe6+i6rBLAsPKgAySVKPRK+oRw== mdrfckr">>.ssh/authorized_keys && chmod -R go= ~/.ssh && cd ~ | tpot (554) |
| 110105 | 12 | 364 | Cowrie captured a file download from [IP address]. | tpot (364) |
| 533 | 7 | 240 | Listened ports status (netstat) changed (new port opened or closed). | tpot (240) |
| 110219 | 4 | 210 | T-Pot CiscoASA web activity from [IP address]: "GET /+CSCOE+/logon.html HTTP/1.1" 302 - | tpot (210) |
| 5501 | 3 | 194 | PAM: Login session opened. | tpot (192), wazuh (2) |
| 5502 | 3 | 159 | PAM: Login session closed. | tpot (158), wazuh (1) |
| 110212 | 10 | 147 | T-Pot Honeytrap detected repeated payload activity from [IP address]. | tpot (147) |
| 110221 | 7 | 121 | T-Pot CiscoASA detected configuration discovery from [IP address]: "GET /appGet.cgi?hook=get_cfg_clientlist() HTTP/1.1" 404 - | tpot (121) |
| 110215 | 4 | 99 | T-Pot MiniPrint event: command_received, action request, Request received | tpot (99) |
| 5715 | 3 | 97 | sshd: authentication success. | tpot (96), wazuh (1) |
| 110223 | 5 | 84 | T-Pot HoneyAML received  request from  to  on port . | tpot (84) |
| 110108 | 12 | 80 | Cowrie captured suspicious execution or staging activity from [IP address]: >/var/run/.x&&cd /var/run;>/mnt/.x&&cd /mnt;>/usr/.x&&cd /usr;>/dev/.x&&cd /dev;>/dev/shm/.x&&cd /dev/shm;>/tmp/.x&&cd /tmp;>/var/.x&&cd /var;/bin/busybox echo -e '\x55\x5a\x4a\x42\x50\x46' | tpot (80) |
| 110106 | 10 | 79 | Cowrie detected repeated failed logins from [IP address]. | tpot (79) |
| 110216 | 4 | 76 | T-Pot Mailoney received SMTP command from [IP address]:   | tpot (76) |
| 110220 | 8 | 62 | T-Pot CiscoASA captured a login request from [IP address]: "POST /login.cgi HTTP/1.1" 200 - | tpot (62) |
| 110214 | 9 | 42 | T-Pot RDP honeypot detected a connection burst from [IP address]. | tpot (42) |
| 510 | 7 | 41 | Host-based anomaly detection event (rootcheck). | wazuh (40), tpot (1) |
| 110208 | 7 | 16 | T-Pot SentryPeer detected SIP scanner Friendly-Scanner/1.1 from [IP address]:46281 | tpot (16) |
| 592 | 8 | 11 | Log file size reduced. | tpot (11) |
| 203 | 9 | 7 | Agent event queue is full. Events may be lost. | tpot (7) |
| 110211 | 9 | 5 | T-Pot Dionaea detected a connection burst from [IP address]. | tpot (5) |
| 110222 | 9 | 4 | T-Pot CiscoASA detected repeated web requests from one source. | tpot (4) |
| 110225 | 13 | 3 | T-Pot HoneyAML detected a probable remote-code-execution and payload-delivery attempt from [IP address]. | tpot (3) |
| 202 | 7 | 3 | Agent event queue is 90% full. | tpot (3) |
| 205 | 3 | 3 | Agent event queue is back to normal load. | tpot (3) |
| 110224 | 7 | 2 | T-Pot HoneyAML received an HTTP POST from [IP address] to /api/json. | tpot (2) |
| 110226 | 10 | 2 | T-Pot HoneyAML detected repeated web requests from one source. | tpot (2) |
| 19004 | 7 | 2 | SCA summary: CIS Ubuntu Linux 24.04 LTS Benchmark v1.0.0.: Score less than 50% (47) | tpot (2) |
| 110217 | 7 | 1 | T-Pot Mailoney captured suspicious SMTP activity from [IP address]: AUTH NTLM  | tpot (1) |
| 110218 | 9 | 1 | T-Pot Mailoney detected repeated SMTP activity from one source. | tpot (1) |
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
