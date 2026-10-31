# LearningLab01 Daily Threat Intelligence Report — 2026-10-31

Generated: 2026-10-31T13:15:05.049Z

Report window: 2026-10-30T13:15:05.023Z through 2026-10-31T13:15:05.023Z

> This report summarizes security telemetry and honeypot activity. An alert indicates that a rule matched observed activity; it does not automatically prove that a system was compromised.

## Executive Summary

| Metric | Count |
|---|---:|
| Wazuh alerts | 251,596 |
| Attack-related alerts | 32,026 |
| Honeypot interactions | 231,919 |
| Authentication failures | 7,261 |
| Authentication successes | 591 |
| Critical alerts | 194 |
| High alerts | 775 |
| T-Pot artifacts observed | 0 |
| Malicious artifact detections | 0 |

### Notable Observations

- 194 critical-severity alerts require priority review.
- 775 high-severity alerts should be reviewed after the critical queue.
- Authentication failures exceeded successful authentications by a ratio of 12.29:1.
- Country attribution currently covers only 0.18% of alerts. Country totals should be treated as partial telemetry.
- The most frequent rule was 110209: T-Pot Conpot snmp event from [IP address]: SNMPv2 Bulk (76,452 alerts).

## Wazuh Security Monitoring

### Alert Severity

| Severity | Alerts | Percentage |
|---|---:|---:|
| Critical | 194 | 0.08% |
| High | 775 | 0.31% |
| Medium | 2,359 | 0.94% |
| Low | 248,268 | 98.68% |
| Informational | 0 | 0.00% |

Severity represents the priority assigned by the Wazuh rule. Critical and high alerts should be investigated first, but repeated lower-severity events can also reveal scanning, credential attacks, or attacker preparation.

### Authentication Activity

- Authentication failures: 7,261
- Authentication successes: 591
- Failure-to-success ratio: 12.29:1

A successful authentication is not considered an attack by itself. Analysts should correlate successful logins with preceding failures, source addresses, usernames, target systems, and expected activity.

### Attack-Type Breakdown

| Category | Alerts | Percentage of attack-related alerts |
|---|---:|---:|
| Network attack | 21,676 | 67.68% |
| Payload delivery | 21,676 | 67.68% |
| Authentication failure | 7,261 | 22.67% |
| Command execution | 1,968 | 6.15% |
| Reconnaissance | 333 | 1.04% |
| Malware | 281 | 0.88% |
| Network scan | 198 | 0.62% |
| Web attack | 192 | 0.60% |
| SMTP attack | 0 | 0.00% |

> Category counts may overlap because one Wazuh alert can belong to multiple rule groups. The attack-related total counts each alert once.

### Country of Origin

Wazuh supplied country information for 445 alerts, representing 0.18% of all alerts.

| Country | Alerts | Percentage of all alerts | Relative volume |
|---|---:|---:|---|
| Unknown | 251,151 | 99.82% | Not geolocated |
| United Kingdom | 188 | 0.07% | ████████████████████ |
| Azerbaijan | 183 | 0.07% | ███████████████████ |
| United States | 53 | 0.02% | ██████ |
| Hungary | 4 | 0.00% | █ |
| China | 3 | 0.00% | █ |
| Netherlands | 3 | 0.00% | █ |
| Russia | 3 | 0.00% | █ |
| Germany | 2 | 0.00% | █ |
| Iran | 2 | 0.00% | █ |
| Panama | 2 | 0.00% | █ |
| Central African Republic | 1 | 0.00% | █ |
| Switzerland | 1 | 0.00% | █ |

> Relative-volume bars compare only countries with known geographic attribution. Unknown alerts are excluded from the bar scale.

> Geolocation is approximate. VPNs, proxies, cloud providers, compromised hosts, carrier networks, and incomplete GeoIP coverage can make the apparent country different from the attacker’s location.

### MITRE ATT&CK Tactics

| Tactic | Alerts |
|---|---:|
| Initial Access | 301 |
| Defense Evasion | 292 |
| Persistence | 291 |
| Privilege Escalation | 291 |
| Execution | 149 |
| Lateral Movement | 97 |
| Credential Access | 92 |
| Command and Control | 17 |
| Impact | 11 |

### MITRE ATT&CK Techniques

| Technique | Alerts |
|---|---:|
| Valid Accounts | 291 |
| Command and Scripting Interpreter | 149 |
| Remote Services | 97 |
| Brute Force | 92 |
| Ingress Tool Transfer | 17 |
| Stored Data Manipulation | 11 |
| Exploit Public-Facing Application | 10 |
| Disable or Modify Tools | 1 |

MITRE ATT&CK describes adversary behavior rather than declaring that an attack succeeded. These mappings help analysts connect individual alerts to possible attacker objectives and investigative hypotheses.

### Most Frequent Wazuh Rules

| Rule ID | Highest Level | Alerts | Description | Agents |
|---|---:|---:|---|---|
| 110209 | 5 | 76,452 | T-Pot Conpot snmp event from [IP address]: SNMPv2 Bulk | tpot (76,452) |
| 110213 | 4 | 66,218 | T-Pot RDP connection from [IP address] to port 3389. | tpot (66,218) |
| 110207 | 5 | 33,180 | T-Pot SentryPeer SIP activity from [IP address]:7093, method ACK | tpot (33,180) |
| 110204 | 4 | 31,820 | T-Pot Honeytrap connection from [IP address] to port 5909 | tpot (31,820) |
| 110205 | 6 | 21,566 | T-Pot Honeytrap received a payload from [IP address] | tpot (21,566) |
| 110101 | 3 | 9,141 | Cowrie SSH connection from [IP address]. | tpot (9,141) |
| 110102 | 5 | 7,261 | Cowrie failed login from [IP address] using username root. | tpot (7,261) |
| 110104 | 7 | 1,638 | Cowrie captured a command from [IP address]: &k`g&k\|zpkfq)ES[M | tpot (1,638) |
| 110201 | 4 | 1,512 | T-Pot Dionaea mssqld connection from [IP address] to port 1433 | tpot (1,512) |
| 110103 | 10 | 300 | Cowrie accepted login from [IP address] using username zalee	. | tpot (300) |
| 110219 | 4 | 260 | T-Pot CiscoASA web activity from [IP address]: "GET /+CSCOE+/logon.html HTTP/1.1" 302 - | tpot (260) |
| 533 | 7 | 239 | Listened ports status (netstat) changed (new port opened or closed). | tpot (239) |
| 5501 | 3 | 194 | PAM: Login session opened. | tpot (192), wazuh (2) |
| 110214 | 9 | 192 | T-Pot RDP honeypot detected a connection burst from [IP address]. | tpot (192) |
| 110223 | 5 | 192 | T-Pot HoneyAML received  request from  to  on port . | tpot (192) |
| 110109 | 13 | 184 | Cowrie captured a destructive, persistence, or defense-evasion command from [IP address]: cd ~ && rm -rf .ssh && mkdir .ssh && echo "ssh-rsa AAAAB3NzaC1yc2EAAAABJQAAAQEArDp4cun2lhr4KUhBGE7VvAcwdli2a8dbnrTOrbMz1+5O73fcBOx8NVbUT0bUanUV9tJ2/9p7+vD0EpZ3Tz/+0kX34uAx1RV/75GVOmNx+9EuWOnvNoaJe0QXxziIg9eLBHpgLMuakb5+BgTFB+rKJAw9u9FSTDengvS8hX1kNFS4Mjux0hJOK8rvcEmPecjdySYMb66nylAKGwCEE6WEQHmd1mUPgHwGQ0hWCwsQk13yCGPK5w6hYp5zYkFnvlC8hGmd4Ww+u97k6pfTGTUbJk14ujvcD9iUKQTTWYYjIIu5PmUux5bsZ0R4WFwdIe6+i6rBLAsPKgAySVKPRK+oRw== mdrfckr">>.ssh/authorized_keys && chmod -R go= ~/.ssh && cd ~ | tpot (184) |
| 5502 | 3 | 166 | PAM: Login session closed. | tpot (164), wazuh (2) |
| 110108 | 12 | 139 | Cowrie captured suspicious execution or staging activity from [IP address]: >/var/run/.x&&cd /var/run;>/mnt/.x&&cd /mnt;>/usr/.x&&cd /usr;>/dev/.x&&cd /dev;>/dev/shm/.x&&cd /dev/shm;>/tmp/.x&&cd /tmp;>/var/.x&&cd /var;/bin/busybox echo -e '\x5a\x59\x47\x54\x56\x4e' | tpot (139) |
| 110216 | 4 | 129 | T-Pot Mailoney received SMTP command from [IP address]:   | tpot (129) |
| 110105 | 12 | 125 | Cowrie captured a file download from [IP address]. | tpot (125) |
| 110221 | 7 | 116 | T-Pot CiscoASA detected configuration discovery from [IP address]: "GET /appGet.cgi?hook=get_cfg_clientlist() HTTP/1.1" 404 - | tpot (116) |
| 110212 | 10 | 110 | T-Pot Honeytrap detected repeated payload activity from [IP address]. | tpot (110) |
| 5715 | 3 | 97 | sshd: authentication success. | tpot (96), wazuh (1) |
| 110106 | 10 | 92 | Cowrie detected repeated failed logins from [IP address]. | tpot (92) |
| 110220 | 8 | 69 | T-Pot CiscoASA captured a login request from [IP address]: "POST /login.cgi HTTP/1.1" 200 - | tpot (69) |
| 110215 | 4 | 67 | T-Pot MiniPrint event: connection, action open_conn, Connection opened | tpot (67) |
| 510 | 7 | 41 | Host-based anomaly detection event (rootcheck). | wazuh (40), tpot (1) |
| 203 | 9 | 18 | Agent event queue is full. Events may be lost. | tpot (18) |
| 110208 | 7 | 16 | T-Pot SentryPeer detected SIP scanner friendly-scanner from [IP address]:20702 | tpot (16) |
| 592 | 8 | 11 | Log file size reduced. | tpot (11) |
| 110225 | 13 | 10 | T-Pot HoneyAML detected a probable remote-code-execution and payload-delivery attempt from [IP address]. | tpot (10) |
| 202 | 7 | 8 | Agent event queue is 90% full. | tpot (8) |
| 205 | 3 | 8 | Agent event queue is back to normal load. | tpot (8) |
| 110107 | 12 | 7 | Cowrie captured a probable payload-retrieval command from [IP address]: uname -s; uname -m; test -r /proc/cpuinfo && grep -E 'CPU architecture\|model name\|Processor\|Features\|Hardware\|cpu model' /proc/cpuinfo; test -r /etc/openwrt_release && grep DISTRIB_ARCH /etc/openwrt_release; command -v curl; command -v wget; command -v busybox; command -v python3; command -v python; command -v sh; command -v bash; id -u; uname -a; test -f /system/build.prop && printf 'NW_%s\n' AOS; test -d /data/data/com.termux/files && printf 'NW_%s\n' TX; command -v termux-info >/dev/null 2>&1 && printf 'NW_%s\n' TX; test -f /etc/openwrt_release && printf 'NW_%s\n' OW; test -f /etc/rc.common && printf 'NW_%s\n' RC; test -x /system/bin/linker64 && printf 'NW_%s\n' L64; test -x /system/bin/linker && printf 'NW_%s\n' L32; true | tpot (7) |
| 110211 | 9 | 6 | T-Pot Dionaea detected a connection burst from [IP address]. | tpot (6) |
| 110226 | 10 | 2 | T-Pot HoneyAML detected repeated web requests from one source. | tpot (2) |
| 19004 | 7 | 2 | SCA summary: CIS Ubuntu Linux 24.04 LTS Benchmark v1.0.0.: Score less than 50% (47) | tpot (2) |
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
