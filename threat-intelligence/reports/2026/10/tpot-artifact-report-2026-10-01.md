# LearningLab01 Daily Threat Intelligence Report — 2026-10-01

Generated: 2026-10-01T13:15:05.053Z

Report window: 2026-09-30T13:15:05.027Z through 2026-10-01T13:15:05.027Z

> This report summarizes security telemetry and honeypot activity. An alert indicates that a rule matched observed activity; it does not automatically prove that a system was compromised.

## Executive Summary

| Metric | Count |
|---|---:|
| Wazuh alerts | 201,808 |
| Attack-related alerts | 25,674 |
| Honeypot interactions | 186,732 |
| Authentication failures | 5,615 |
| Authentication successes | 504 |
| Critical alerts | 189 |
| High alerts | 559 |
| T-Pot artifacts observed | 0 |
| Malicious artifact detections | 0 |

### Notable Observations

- 189 critical-severity alerts require priority review.
- 559 high-severity alerts should be reviewed after the critical queue.
- Authentication failures exceeded successful authentications by a ratio of 11.14:1.
- Country attribution currently covers only 3.71% of alerts. Country totals should be treated as partial telemetry.
- The most frequent rule was 110209: T-Pot Conpot snmp event from [IP address]: SNMPv2 Bulk (94,351 alerts).

## Wazuh Security Monitoring

### Alert Severity

| Severity | Alerts | Percentage |
|---|---:|---:|
| Critical | 189 | 0.09% |
| High | 559 | 0.28% |
| Medium | 2,350 | 1.16% |
| Low | 198,710 | 98.46% |
| Informational | 0 | 0.00% |

Severity represents the priority assigned by the Wazuh rule. Critical and high alerts should be investigated first, but repeated lower-severity events can also reveal scanning, credential attacks, or attacker preparation.

### Authentication Activity

- Authentication failures: 5,615
- Authentication successes: 504
- Failure-to-success ratio: 11.14:1

A successful authentication is not considered an attack by itself. Analysts should correlate successful logins with preceding failures, source addresses, usernames, target systems, and expected activity.

### Attack-Type Breakdown

| Category | Alerts | Percentage of attack-related alerts |
|---|---:|---:|
| Network attack | 17,349 | 67.57% |
| Payload delivery | 17,349 | 67.57% |
| Authentication failure | 5,615 | 21.87% |
| Command execution | 1,804 | 7.03% |
| Reconnaissance | 396 | 1.54% |
| Network scan | 183 | 0.71% |
| Malware | 144 | 0.56% |
| SMTP attack | 103 | 0.40% |
| Web attack | 51 | 0.20% |

> Category counts may overlap because one Wazuh alert can belong to multiple rule groups. The attack-related total counts each alert once.

### Country of Origin

Wazuh supplied country information for 7,489 alerts, representing 3.71% of all alerts.

| Country | Alerts | Percentage of all alerts | Relative volume |
|---|---:|---:|---|
| Unknown | 194,319 | 96.29% | Not geolocated |
| Ukraine | 4,505 | 2.23% | ████████████████████ |
| Republic of Moldova | 1,728 | 0.86% | ████████ |
| Germany | 991 | 0.49% | ████ |
| United Kingdom | 106 | 0.05% | █ |
| United States | 82 | 0.04% | █ |
| Russia | 27 | 0.01% | █ |
| Turkey | 12 | 0.01% | █ |
| France | 6 | 0.00% | █ |
| Malta | 6 | 0.00% | █ |
| Slovakia | 6 | 0.00% | █ |
| Netherlands | 5 | 0.00% | █ |
| Austria | 3 | 0.00% | █ |
| Azerbaijan | 3 | 0.00% | █ |
| Iraq | 3 | 0.00% | █ |
| Sweden | 3 | 0.00% | █ |
| Canada | 2 | 0.00% | █ |
| Belgium | 1 | 0.00% | █ |

> Relative-volume bars compare only countries with known geographic attribution. Unknown alerts are excluded from the bar scale.

> Geolocation is approximate. VPNs, proxies, cloud providers, compromised hosts, carrier networks, and incomplete GeoIP coverage can make the apparent country different from the attacker’s location.

### MITRE ATT&CK Tactics

| Tactic | Alerts |
|---|---:|
| Initial Access | 297 |
| Defense Evasion | 292 |
| Persistence | 291 |
| Privilege Escalation | 291 |
| Credential Access | 98 |
| Lateral Movement | 97 |
| Execution | 27 |
| Command and Control | 13 |
| Impact | 11 |

### MITRE ATT&CK Techniques

| Technique | Alerts |
|---|---:|
| Valid Accounts | 291 |
| Brute Force | 98 |
| Remote Services | 97 |
| Command and Scripting Interpreter | 27 |
| Ingress Tool Transfer | 13 |
| Stored Data Manipulation | 11 |
| Exploit Public-Facing Application | 6 |
| Disable or Modify Tools | 1 |

MITRE ATT&CK describes adversary behavior rather than declaring that an attack succeeded. These mappings help analysts connect individual alerts to possible attacker objectives and investigative hypotheses.

### Most Frequent Wazuh Rules

| Rule ID | Highest Level | Alerts | Description | Agents |
|---|---:|---:|---|---|
| 110209 | 5 | 94,351 | T-Pot Conpot snmp event from [IP address]: SNMPv2 Bulk | tpot (94,351) |
| 110213 | 4 | 45,295 | T-Pot RDP connection from [IP address] to port 3389. | tpot (45,295) |
| 110205 | 6 | 17,239 | T-Pot Honeytrap received a payload from [IP address] | tpot (17,239) |
| 110204 | 4 | 13,960 | T-Pot Honeytrap connection from [IP address] to port 5908 | tpot (13,960) |
| 110219 | 4 | 7,388 | T-Pot CiscoASA web activity from [IP address]: "POST /+webvpn+/index.html HTTP/1.1" 200 - | tpot (7,388) |
| 110207 | 5 | 7,160 | T-Pot SentryPeer SIP activity from [IP address]:63496, method INVITE | tpot (7,160) |
| 110101 | 3 | 6,444 | Cowrie SSH connection from [IP address]. | tpot (6,444) |
| 110102 | 5 | 5,615 | Cowrie failed login from [IP address] using username root. | tpot (5,615) |
| 110104 | 7 | 1,593 | Cowrie captured a command from [IP address]: &k`g&k\|zpkfq)ES[M | tpot (1,593) |
| 110201 | 4 | 417 | T-Pot Dionaea pptpd connection from [IP address] to port 1723 | tpot (417) |
| 110216 | 4 | 265 | T-Pot Mailoney received SMTP command from [IP address]: EHLO User  | tpot (265) |
| 533 | 7 | 239 | Listened ports status (netstat) changed (new port opened or closed). | tpot (239) |
| 110103 | 10 | 213 | Cowrie accepted login from [IP address] using username zalee	. | tpot (213) |
| 5501 | 3 | 194 | PAM: Login session opened. | tpot (192), wazuh (2) |
| 110109 | 13 | 183 | Cowrie captured a destructive, persistence, or defense-evasion command from [IP address]: cd ~ && rm -rf .ssh && mkdir .ssh && echo "ssh-rsa AAAAB3NzaC1yc2EAAAABJQAAAQEArDp4cun2lhr4KUhBGE7VvAcwdli2a8dbnrTOrbMz1+5O73fcBOx8NVbUT0bUanUV9tJ2/9p7+vD0EpZ3Tz/+0kX34uAx1RV/75GVOmNx+9EuWOnvNoaJe0QXxziIg9eLBHpgLMuakb5+BgTFB+rKJAw9u9FSTDengvS8hX1kNFS4Mjux0hJOK8rvcEmPecjdySYMb66nylAKGwCEE6WEQHmd1mUPgHwGQ0hWCwsQk13yCGPK5w6hYp5zYkFnvlC8hGmd4Ww+u97k6pfTGTUbJk14ujvcD9iUKQTTWYYjIIu5PmUux5bsZ0R4WFwdIe6+i6rBLAsPKgAySVKPRK+oRw== mdrfckr">>.ssh/authorized_keys && chmod -R go= ~/.ssh && cd ~ | tpot (183) |
| 110214 | 9 | 181 | T-Pot RDP honeypot detected a connection burst from [IP address]. | tpot (181) |
| 5502 | 3 | 160 | PAM: Login session closed. | tpot (159), wazuh (1) |
| 110105 | 12 | 110 | Cowrie captured a file download from [IP address]. | tpot (110) |
| 110212 | 10 | 110 | T-Pot Honeytrap detected repeated payload activity from [IP address]. | tpot (110) |
| 110217 | 7 | 103 | T-Pot Mailoney captured suspicious SMTP activity from [IP address]: AUTH LOGIN  | tpot (103) |
| 110106 | 10 | 98 | Cowrie detected repeated failed logins from [IP address]. | tpot (98) |
| 5715 | 3 | 97 | sshd: authentication success. | tpot (96), wazuh (1) |
| 110221 | 7 | 67 | T-Pot CiscoASA detected configuration discovery from [IP address]: "GET /appGet.cgi?hook=get_cfg_clientlist() HTTP/1.1" 404 - | tpot (67) |
| 110215 | 4 | 62 | T-Pot MiniPrint event: connection, action open_conn, Connection opened | tpot (62) |
| 110223 | 5 | 51 | T-Pot HoneyAML received  request from  to  on port . | tpot (51) |
| 510 | 7 | 41 | Host-based anomaly detection event (rootcheck). | wazuh (40), tpot (1) |
| 110220 | 8 | 32 | T-Pot CiscoASA captured a login request from [IP address]: "POST /login.cgi HTTP/1.1" 200 - | tpot (32) |
| 110208 | 7 | 23 | T-Pot SentryPeer detected SIP scanner friendly-scanner from [IP address]:5077 | tpot (23) |
| 110108 | 12 | 21 | Cowrie captured suspicious execution or staging activity from $(src_ip): $(input) | tpot (21) |
| 110222 | 9 | 20 | T-Pot CiscoASA detected repeated web requests from one source. | tpot (20) |
| 2904 | 7 | 14 | Dpkg (Debian Package) half configured. | tpot (14) |
| 592 | 8 | 11 | Log file size reduced. | tpot (11) |
| 203 | 9 | 8 | Agent event queue is full. Events may be lost. | tpot (8) |
| 2902 | 7 | 8 | New dpkg (Debian Package) installed. | tpot (8) |
| 110107 | 12 | 7 | Cowrie captured a probable payload-retrieval command from [IP address]: which wget curl 2>/dev/null \|\| command -v wget curl 2>/dev/null | tpot (7) |
| 110225 | 13 | 6 | T-Pot HoneyAML detected a probable remote-code-execution and payload-delivery attempt from [IP address]. | tpot (6) |
| 202 | 7 | 4 | Agent event queue is 90% full. | tpot (4) |
| 205 | 3 | 4 | Agent event queue is back to normal load. | tpot (4) |
| 11 | 4 | 3 | Unknown | tpot (3) |
| 110211 | 9 | 2 | T-Pot Dionaea detected a connection burst from [IP address]. | tpot (2) |
| 19004 | 7 | 2 | SCA summary: CIS Ubuntu Linux 24.04 LTS Benchmark v1.0.0.: Score less than 50% (47) | tpot (2) |
| 19010 | 3 | 2 | CIS Ubuntu Linux 24.04 LTS Benchmark v1.0.0.: Ensure all AppArmor Profiles are in enforce or complain mode.: Status changed from failed to passed | tpot (2) |
| 19011 | 9 | 2 | CIS Ubuntu Linux 24.04 LTS Benchmark v1.0.0.: Ensure all AppArmor Profiles are in enforce or complain mode.: Status changed from passed to failed | tpot (2) |
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
