# LearningLab01 Daily Threat Intelligence Report — 2026-10-23

Generated: 2026-10-23T13:15:05.048Z

Report window: 2026-10-22T13:15:05.024Z through 2026-10-23T13:15:05.024Z

> This report summarizes security telemetry and honeypot activity. An alert indicates that a rule matched observed activity; it does not automatically prove that a system was compromised.

## Executive Summary

| Metric | Count |
|---|---:|
| Wazuh alerts | 183,444 |
| Attack-related alerts | 22,019 |
| Honeypot interactions | 161,297 |
| Authentication failures | 8,796 |
| Authentication successes | 582 |
| Critical alerts | 258 |
| High alerts | 686 |
| T-Pot artifacts observed | 0 |
| Malicious artifact detections | 0 |

### Notable Observations

- 258 critical-severity alerts require priority review.
- 686 high-severity alerts should be reviewed after the critical queue.
- Authentication failures exceeded successful authentications by a ratio of 15.11:1.
- Country attribution currently covers only 0.17% of alerts. Country totals should be treated as partial telemetry.
- The most frequent rule was 110207: T-Pot SentryPeer SIP activity from [IP address]:50170, method INVITE (82,569 alerts).

## Wazuh Security Monitoring

### Alert Severity

| Severity | Alerts | Percentage |
|---|---:|---:|
| Critical | 258 | 0.14% |
| High | 686 | 0.37% |
| Medium | 2,367 | 1.29% |
| Low | 180,133 | 98.20% |
| Informational | 0 | 0.00% |

Severity represents the priority assigned by the Wazuh rule. Critical and high alerts should be investigated first, but repeated lower-severity events can also reveal scanning, credential attacks, or attacker preparation.

### Authentication Activity

- Authentication failures: 8,796
- Authentication successes: 582
- Failure-to-success ratio: 15.11:1

A successful authentication is not considered an attack by itself. Analysts should correlate successful logins with preceding failures, source addresses, usernames, target systems, and expected activity.

### Attack-Type Breakdown

| Category | Alerts | Percentage of attack-related alerts |
|---|---:|---:|
| Network attack | 10,281 | 46.69% |
| Payload delivery | 10,281 | 46.69% |
| Authentication failure | 8,796 | 39.95% |
| Command execution | 2,087 | 9.48% |
| Reconnaissance | 205 | 0.93% |
| Malware | 198 | 0.90% |
| SMTP attack | 86 | 0.39% |
| Network scan | 43 | 0.20% |
| Web attack | 34 | 0.15% |

> Category counts may overlap because one Wazuh alert can belong to multiple rule groups. The attack-related total counts each alert once.

### Country of Origin

Wazuh supplied country information for 305 alerts, representing 0.17% of all alerts.

| Country | Alerts | Percentage of all alerts | Relative volume |
|---|---:|---:|---|
| Unknown | 183,139 | 99.83% | Not geolocated |
| United States | 109 | 0.06% | ████████████████████ |
| United Kingdom | 97 | 0.05% | ██████████████████ |
| Germany | 45 | 0.02% | ████████ |
| Bulgaria | 28 | 0.02% | █████ |
| Romania | 19 | 0.01% | ███ |
| Bosnia and Herzegovina | 2 | 0.00% | █ |
| China | 2 | 0.00% | █ |
| Hungary | 2 | 0.00% | █ |
| Russia | 1 | 0.00% | █ |

> Relative-volume bars compare only countries with known geographic attribution. Unknown alerts are excluded from the bar scale.

> Geolocation is approximate. VPNs, proxies, cloud providers, compromised hosts, carrier networks, and incomplete GeoIP coverage can make the apparent country different from the attacker’s location.

### MITRE ATT&CK Tactics

| Tactic | Alerts |
|---|---:|
| Defense Evasion | 302 |
| Initial Access | 292 |
| Persistence | 291 |
| Privilege Escalation | 291 |
| Credential Access | 128 |
| Lateral Movement | 97 |
| Impact | 25 |
| Execution | 16 |
| Command and Control | 9 |

### MITRE ATT&CK Techniques

| Technique | Alerts |
|---|---:|
| Valid Accounts | 291 |
| Brute Force | 128 |
| Remote Services | 97 |
| Command and Scripting Interpreter | 16 |
| Stored Data Manipulation | 15 |
| Data Destruction | 10 |
| File Deletion | 10 |
| Ingress Tool Transfer | 9 |
| Disable or Modify Tools | 1 |
| Exploit Public-Facing Application | 1 |

MITRE ATT&CK describes adversary behavior rather than declaring that an attack succeeded. These mappings help analysts connect individual alerts to possible attacker objectives and investigative hypotheses.

### Most Frequent Wazuh Rules

| Rule ID | Highest Level | Alerts | Description | Agents |
|---|---:|---:|---|---|
| 110207 | 5 | 82,569 | T-Pot SentryPeer SIP activity from [IP address]:50170, method INVITE | tpot (82,569) |
| 110213 | 4 | 45,235 | T-Pot RDP connection from [IP address] to port 3389. | tpot (45,235) |
| 110204 | 4 | 21,294 | T-Pot Honeytrap connection from [IP address] to port 5909 | tpot (21,294) |
| 110205 | 6 | 10,211 | T-Pot Honeytrap received a payload from [IP address] | tpot (10,211) |
| 110101 | 3 | 9,856 | Cowrie SSH connection from [IP address]. | tpot (9,856) |
| 110102 | 5 | 8,796 | Cowrie failed login from [IP address] using username root. | tpot (8,796) |
| 110104 | 7 | 1,807 | Cowrie captured a command from $(src_ip): $(input) | tpot (1,807) |
| 110201 | 4 | 1,118 | T-Pot Dionaea mssqld connection from [IP address] to port 1433 | tpot (1,118) |
| 110103 | 10 | 291 | Cowrie accepted login from [IP address] using username ssh. | tpot (291) |
| 110109 | 13 | 257 | Cowrie captured a destructive, persistence, or defense-evasion command from [IP address]: cd ~ && rm -rf .ssh && mkdir .ssh && echo "ssh-rsa AAAAB3NzaC1yc2EAAAABJQAAAQEArDp4cun2lhr4KUhBGE7VvAcwdli2a8dbnrTOrbMz1+5O73fcBOx8NVbUT0bUanUV9tJ2/9p7+vD0EpZ3Tz/+0kX34uAx1RV/75GVOmNx+9EuWOnvNoaJe0QXxziIg9eLBHpgLMuakb5+BgTFB+rKJAw9u9FSTDengvS8hX1kNFS4Mjux0hJOK8rvcEmPecjdySYMb66nylAKGwCEE6WEQHmd1mUPgHwGQ0hWCwsQk13yCGPK5w6hYp5zYkFnvlC8hGmd4Ww+u97k6pfTGTUbJk14ujvcD9iUKQTTWYYjIIu5PmUux5bsZ0R4WFwdIe6+i6rBLAsPKgAySVKPRK+oRw== mdrfckr">>.ssh/authorized_keys && chmod -R go= ~/.ssh && cd ~ | tpot (257) |
| 533 | 7 | 242 | Listened ports status (netstat) changed (new port opened or closed). | tpot (241), wazuh (1) |
| 110219 | 4 | 240 | T-Pot CiscoASA web activity from [IP address]: "GET /+CSCOE+/logon.html?fcadbadd=1 HTTP/1.1" 200 - | tpot (240) |
| 5501 | 3 | 194 | PAM: Login session opened. | tpot (192), wazuh (2) |
| 110105 | 12 | 174 | Cowrie captured a file download from [IP address]. | tpot (174) |
| 5502 | 3 | 170 | PAM: Login session closed. | tpot (169), wazuh (1) |
| 110216 | 4 | 153 | T-Pot Mailoney received SMTP command from [IP address]: EHLO [IP address]  | tpot (153) |
| 110106 | 10 | 128 | Cowrie detected repeated failed logins from [IP address]. | tpot (128) |
| 5715 | 3 | 97 | sshd: authentication success. | tpot (96), wazuh (1) |
| 110217 | 7 | 86 | T-Pot Mailoney captured suspicious SMTP activity from [IP address]: AUTH LOGIN  | tpot (86) |
| 110209 | 5 | 78 | T-Pot Conpot IEC104 event from [IP address]: NEW_CONNECTION | tpot (78) |
| 110212 | 10 | 70 | T-Pot Honeytrap detected repeated payload activity from [IP address]. | tpot (70) |
| 110215 | 4 | 66 | T-Pot MiniPrint event: command_received, action request, Request received | tpot (66) |
| 110221 | 7 | 43 | T-Pot CiscoASA detected configuration discovery from [IP address]: "GET /appGet.cgi?hook=get_cfg_clientlist() HTTP/1.1" 404 - | tpot (43) |
| 510 | 7 | 41 | Host-based anomaly detection event (rootcheck). | wazuh (40), tpot (1) |
| 110214 | 9 | 37 | T-Pot RDP honeypot detected a connection burst from [IP address]. | tpot (37) |
| 110223 | 5 | 34 | T-Pot HoneyAML received  request from  to  on port . | tpot (34) |
| 110208 | 7 | 33 | T-Pot SentryPeer detected SIP scanner friendly-scanner from [IP address]:5106 | tpot (33) |
| 110220 | 8 | 22 | T-Pot CiscoASA captured a login request from [IP address]: "POST /login.cgi HTTP/1.1" 200 - | tpot (22) |
| 110108 | 12 | 15 | Cowrie captured suspicious execution or staging activity from $(src_ip): $(input) | tpot (15) |
| 592 | 8 | 11 | Log file size reduced. | tpot (11) |
| 553 | 7 | 10 | File deleted. | tpot (10) |
| 203 | 9 | 9 | Agent event queue is full. Events may be lost. | tpot (9) |
| 110107 | 12 | 8 | Cowrie captured a probable payload-retrieval command from [IP address]: uname -s; uname -m; test -r /proc/cpuinfo && grep -E 'CPU architecture\|model name\|Processor\|Features\|Hardware\|cpu model' /proc/cpuinfo; test -r /etc/openwrt_release && grep DISTRIB_ARCH /etc/openwrt_release; command -v curl; command -v wget; command -v busybox; command -v python3; command -v python; command -v sh; command -v bash; id -u; uname -a; test -f /system/build.prop && printf 'NW_%s\n' AOS; test -d /data/data/com.termux/files && printf 'NW_%s\n' TX; command -v termux-info >/dev/null 2>&1 && printf 'NW_%s\n' TX; test -f /etc/openwrt_release && printf 'NW_%s\n' OW; test -f /etc/rc.common && printf 'NW_%s\n' RC; test -x /system/bin/linker64 && printf 'NW_%s\n' L64; test -x /system/bin/linker && printf 'NW_%s\n' L32; true | tpot (8) |
| 202 | 7 | 8 | Agent event queue is 90% full. | tpot (8) |
| 205 | 3 | 8 | Agent event queue is back to normal load. | tpot (8) |
| 554 | 5 | 8 | File added to the system. | tpot (8) |
| 110211 | 9 | 6 | T-Pot Dionaea detected a connection burst from [IP address]. | tpot (6) |
| 550 | 7 | 4 | Integrity checksum changed. | tpot (4) |
| 2904 | 7 | 3 | Dpkg (Debian Package) half configured. | tpot (3) |
| 2902 | 7 | 2 | New dpkg (Debian Package) installed. | tpot (2) |
| 86003 | 3 | 2 | Docker: Error message | tpot (2) |
| 110218 | 9 | 1 | T-Pot Mailoney detected repeated SMTP activity from one source. | tpot (1) |
| 110225 | 13 | 1 | T-Pot HoneyAML detected a probable remote-code-execution and payload-delivery attempt from [IP address]. | tpot (1) |
| 19004 | 7 | 1 | SCA summary: CIS Ubuntu Linux 24.04 LTS Benchmark v1.0.0.: Score less than 50% (47) | tpot (1) |
| 19011 | 9 | 1 | CIS Ubuntu Linux 24.04 LTS Benchmark v1.0.0.: Ensure nftables default deny firewall policy.: Status changed from passed to failed | tpot (1) |
| 502 | 3 | 1 | Wazuh server started. | wazuh (1) |
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
