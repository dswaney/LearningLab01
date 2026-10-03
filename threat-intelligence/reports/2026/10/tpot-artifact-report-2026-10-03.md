# LearningLab01 Daily Threat Intelligence Report — 2026-10-03

Generated: 2026-10-03T13:15:05.054Z

Report window: 2026-10-02T13:15:05.027Z through 2026-10-03T13:15:05.027Z

> This report summarizes security telemetry and honeypot activity. An alert indicates that a rule matched observed activity; it does not automatically prove that a system was compromised.

## Executive Summary

| Metric | Count |
|---|---:|
| Wazuh alerts | 308,777 |
| Attack-related alerts | 22,344 |
| Honeypot interactions | 293,097 |
| Authentication failures | 5,849 |
| Authentication successes | 529 |
| Critical alerts | 195 |
| High alerts | 577 |
| T-Pot artifacts observed | 0 |
| Malicious artifact detections | 0 |

### Notable Observations

- 195 critical-severity alerts require priority review.
- 577 high-severity alerts should be reviewed after the critical queue.
- Authentication failures exceeded successful authentications by a ratio of 11.06:1.
- Country attribution currently covers only 12.53% of alerts. Country totals should be treated as partial telemetry.
- The most frequent rule was 110204: T-Pot Honeytrap connection from [IP address] to port 5906 (85,262 alerts).

## Wazuh Security Monitoring

### Alert Severity

| Severity | Alerts | Percentage |
|---|---:|---:|
| Critical | 195 | 0.06% |
| High | 577 | 0.19% |
| Medium | 2,678 | 0.87% |
| Low | 305,327 | 98.88% |
| Informational | 0 | 0.00% |

Severity represents the priority assigned by the Wazuh rule. Critical and high alerts should be investigated first, but repeated lower-severity events can also reveal scanning, credential attacks, or attacker preparation.

### Authentication Activity

- Authentication failures: 5,849
- Authentication successes: 529
- Failure-to-success ratio: 11.06:1

A successful authentication is not considered an attack by itself. Analysts should correlate successful logins with preceding failures, source addresses, usernames, target systems, and expected activity.

### Attack-Type Breakdown

| Category | Alerts | Percentage of attack-related alerts |
|---|---:|---:|
| Network attack | 13,371 | 59.84% |
| Payload delivery | 13,371 | 59.84% |
| Authentication failure | 5,849 | 26.18% |
| Command execution | 2,057 | 9.21% |
| Reconnaissance | 498 | 2.23% |
| Network scan | 275 | 1.23% |
| Malware | 177 | 0.79% |
| Web attack | 66 | 0.30% |
| SMTP attack | 25 | 0.11% |

> Category counts may overlap because one Wazuh alert can belong to multiple rule groups. The attack-related total counts each alert once.

### Country of Origin

Wazuh supplied country information for 38,697 alerts, representing 12.53% of all alerts.

| Country | Alerts | Percentage of all alerts | Relative volume |
|---|---:|---:|---|
| Unknown | 270,080 | 87.47% | Not geolocated |
| Russia | 16,263 | 5.27% | ████████████████████ |
| Kazakhstan | 9,742 | 3.16% | ████████████ |
| United States | 9,180 | 2.97% | ███████████ |
| Republic of Moldova | 2,172 | 0.70% | ███ |
| Germany | 1,138 | 0.37% | █ |
| United Kingdom | 157 | 0.05% | █ |
| Canada | 11 | 0.00% | █ |
| Turkey | 9 | 0.00% | █ |
| Austria | 6 | 0.00% | █ |
| Sweden | 6 | 0.00% | █ |
| Malta | 3 | 0.00% | █ |
| Netherlands | 3 | 0.00% | █ |
| Ukraine | 3 | 0.00% | █ |
| Bulgaria | 2 | 0.00% | █ |
| Hungary | 2 | 0.00% | █ |

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
| Credential Access | 90 |
| Command and Control | 34 |
| Execution | 24 |
| Impact | 15 |

### MITRE ATT&CK Techniques

| Technique | Alerts |
|---|---:|
| Valid Accounts | 291 |
| Remote Services | 97 |
| Brute Force | 90 |
| Ingress Tool Transfer | 34 |
| Command and Scripting Interpreter | 24 |
| Stored Data Manipulation | 15 |
| Disable or Modify Tools | 1 |

MITRE ATT&CK describes adversary behavior rather than declaring that an attack succeeded. These mappings help analysts connect individual alerts to possible attacker objectives and investigative hypotheses.

### Most Frequent Wazuh Rules

| Rule ID | Highest Level | Alerts | Description | Agents |
|---|---:|---:|---|---|
| 110204 | 4 | 85,262 | T-Pot Honeytrap connection from [IP address] to port 5906 | tpot (85,262) |
| 110209 | 5 | 85,257 | T-Pot Conpot snmp event from [IP address]: SNMPv2 Bulk | tpot (85,257) |
| 110213 | 4 | 68,380 | T-Pot RDP connection from [IP address] to port 3389. | tpot (68,380) |
| 110219 | 4 | 38,469 | T-Pot CiscoASA web activity from [IP address]: "POST /+webvpn+/index.html?fcadbadd=1 HTTP/1.1" 200 - | tpot (38,469) |
| 110205 | 6 | 13,300 | T-Pot Honeytrap received a payload from [IP address] | tpot (13,300) |
| 110101 | 3 | 6,542 | Cowrie SSH connection from [IP address]. | tpot (6,542) |
| 110102 | 5 | 5,849 | Cowrie failed login from [IP address] using username root. | tpot (5,849) |
| 110104 | 7 | 1,804 | Cowrie captured a command from [IP address]: ls /home; /bin/busybox BOTNET | tpot (1,804) |
| 110207 | 5 | 1,102 | T-Pot SentryPeer SIP activity from [IP address]:5060, method INVITE | tpot (1,102) |
| 110201 | 4 | 454 | T-Pot Dionaea pptpd connection from [IP address] to port 1723 | tpot (454) |
| 110214 | 9 | 272 | T-Pot RDP honeypot detected a connection burst from [IP address]. | tpot (272) |
| 533 | 7 | 240 | Listened ports status (netstat) changed (new port opened or closed). | tpot (239), wazuh (1) |
| 110103 | 10 | 238 | Cowrie accepted login from [IP address] using username system. | tpot (238) |
| 110109 | 13 | 195 | Cowrie captured a destructive, persistence, or defense-evasion command from [IP address]: cd ~ && rm -rf .ssh && mkdir .ssh && echo "ssh-rsa AAAAB3NzaC1yc2EAAAABJQAAAQEArDp4cun2lhr4KUhBGE7VvAcwdli2a8dbnrTOrbMz1+5O73fcBOx8NVbUT0bUanUV9tJ2/9p7+vD0EpZ3Tz/+0kX34uAx1RV/75GVOmNx+9EuWOnvNoaJe0QXxziIg9eLBHpgLMuakb5+BgTFB+rKJAw9u9FSTDengvS8hX1kNFS4Mjux0hJOK8rvcEmPecjdySYMb66nylAKGwCEE6WEQHmd1mUPgHwGQ0hWCwsQk13yCGPK5w6hYp5zYkFnvlC8hGmd4Ww+u97k6pfTGTUbJk14ujvcD9iUKQTTWYYjIIu5PmUux5bsZ0R4WFwdIe6+i6rBLAsPKgAySVKPRK+oRw== mdrfckr">>.ssh/authorized_keys && chmod -R go= ~/.ssh && cd ~ | tpot (195) |
| 5501 | 3 | 194 | PAM: Login session opened. | tpot (192), wazuh (2) |
| 5502 | 3 | 161 | PAM: Login session closed. | tpot (160), wazuh (1) |
| 110105 | 12 | 119 | Cowrie captured a file download from [IP address]. | tpot (119) |
| 110216 | 4 | 109 | T-Pot Mailoney received SMTP command from [IP address]: EHLO User  | tpot (109) |
| 110221 | 7 | 97 | T-Pot CiscoASA detected configuration discovery from [IP address]: "GET /appGet.cgi?hook=get_cfg_clientlist() HTTP/1.1" 404 - | tpot (97) |
| 5715 | 3 | 97 | sshd: authentication success. | tpot (96), wazuh (1) |
| 110106 | 10 | 90 | Cowrie detected repeated failed logins from [IP address]. | tpot (90) |
| 110222 | 9 | 82 | T-Pot CiscoASA detected repeated web requests from one source. | tpot (82) |
| 110215 | 4 | 72 | T-Pot MiniPrint event: connection, action open_conn, Connection opened | tpot (72) |
| 110212 | 10 | 71 | T-Pot Honeytrap detected repeated payload activity from [IP address]. | tpot (71) |
| 110223 | 5 | 66 | T-Pot HoneyAML received  request from  to  on port . | tpot (66) |
| 110220 | 8 | 56 | T-Pot CiscoASA captured a login request from [IP address]: "POST /login.cgi HTTP/1.1" 200 - | tpot (56) |
| 510 | 7 | 41 | Host-based anomaly detection event (rootcheck). | wazuh (40), tpot (1) |
| 110107 | 12 | 34 | Cowrie captured a probable payload-retrieval command from [IP address]: command -v curl | tpot (34) |
| 110217 | 7 | 25 | T-Pot Mailoney captured suspicious SMTP activity from [IP address]: AUTH LOGIN  | tpot (25) |
| 110108 | 12 | 24 | Cowrie captured suspicious execution or staging activity from $(src_ip): $(input) | tpot (24) |
| 110208 | 7 | 18 | T-Pot SentryPeer detected SIP scanner friendly-scanner from [IP address]:51151 | tpot (18) |
| 592 | 8 | 11 | Log file size reduced. | tpot (11) |
| 2904 | 7 | 8 | Dpkg (Debian Package) half configured. | wazuh (8) |
| 203 | 9 | 5 | Agent event queue is full. Events may be lost. | tpot (5) |
| 2902 | 7 | 5 | New dpkg (Debian Package) installed. | wazuh (5) |
| 11 | 4 | 4 | Unknown | tpot (4) |
| 550 | 7 | 4 | Integrity checksum changed. | wazuh (3), tpot (1) |
| 110211 | 9 | 3 | T-Pot Dionaea detected a connection burst from [IP address]. | tpot (3) |
| 202 | 7 | 3 | Agent event queue is 90% full. | tpot (3) |
| 205 | 3 | 3 | Agent event queue is back to normal load. | tpot (3) |
| 19004 | 7 | 2 | SCA summary: CIS Ubuntu Linux 24.04 LTS Benchmark v1.0.0.: Score less than 50% (47) | tpot (2) |
| 86003 | 3 | 2 | Docker: Error message | tpot (2) |
| 110218 | 9 | 1 | T-Pot Mailoney detected repeated SMTP activity from one source. | tpot (1) |
| 110226 | 10 | 1 | T-Pot HoneyAML detected repeated web requests from one source. | tpot (1) |
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
