# Home Security Lab Network & T-Pot Standard Deployment

## Overview

This lab uses a layered network architecture built around a **MikroTik router**, **Proxmox virtualization host**, and **pfSense firewall/router**. The environment separates the normal home network from the internal security lab and DMZ while allowing a single trusted management workstation to reach selected administrative services.

The primary management workstation is:

```text
192.168.88.45
```

Access from this workstation is explicitly permitted through pfSense only to the services required for administration.

---

# Network Diagram

```text
                            INTERNET
                               │
                               │
                     ┌─────────▼─────────┐
                     │     MikroTik      │
                     │      Router       │
                     │                   │
                     │ Home LAN Gateway  │
                     │  192.168.88.1     │
                     └─────────┬─────────┘
                               │
                  192.168.88.0/24 Home LAN
                               │
              ┌────────────────┴────────────────┐
              │                                 │
     ┌────────▼────────┐              ┌─────────▼─────────┐
     │ Main Workstation│              │   Proxmox Host    │
     │ 192.168.88.45   │              │ 192.168.88.200    │
     │                 │              │                   │
     │ Trusted Admin   │              │ Security Lab VMs  │
     └────────┬────────┘              └─────────┬─────────┘
              │                                 │
              │                      ┌──────────▼──────────┐
              │                      │      pfSense        │
              │                      │                     │
              │                      │ WAN:                │
              └─────────────────────►│ 192.168.88.54/24    │
                                     │                     │
                                     │ LAN:                │
                                     │ 10.10.10.1/24       │
                                     │                     │
                                     │ DMZ:                │
                                     │ 10.10.20.1/24       │
                                     │                     │
                                     │ COMPTON:            │
                                     │ 10.2.3.1/24         │
                                     └──────┬───────┬──────┘
                                            │       │
                         ┌──────────────────┘       └───────────────┐
                         │                                          │
                  10.10.10.0/24                              10.10.20.0/24
                     LAB LAN                                      DMZ
                         │                                          │
           ┌─────────────┼──────────────┐                           │
           │             │              │                           │
           ▼             ▼              ▼                           ▼
     Security Onion   Elastic       FileServer                  T-Pot
     10.10.10.201   10.10.10.200   10.10.10.202              10.10.20.200
                                      │
                                      ├── n8n
                                      └── Samba
```

---

# Network Addressing

| Network | Purpose | Gateway |
|---|---|---|
| `192.168.88.0/24` | Home / Management LAN | `192.168.88.1` |
| `10.10.10.0/24` | Security Lab LAN | `10.10.10.1` |
| `10.10.20.0/24` | Security Lab DMZ | `10.10.20.1` |
| `10.2.3.0/24` | COMPTON test network | `10.2.3.1` |
| `10.100.100.0/24` | WireGuard network | WireGuard |

---

# MikroTik Router

The MikroTik is the upstream router for the Proxmox / pfSense environment.

## Home LAN

```text
Network: 192.168.88.0/24
Gateway: 192.168.88.1
```

pfSense WAN:

```text
192.168.88.54/24
```

The MikroTik contains static routes allowing the internal lab networks to be reached through pfSense.

### Security Lab LAN

```text
Destination: 10.10.10.0/24
Gateway:     192.168.88.54
```

### Security Lab DMZ

```text
Destination: 10.10.20.0/24
Gateway:     192.168.88.54
```

Conceptually:

```text
10.10.10.0/24 ──► 192.168.88.54 ──► pfSense
10.10.20.0/24 ──► 192.168.88.54 ──► pfSense
```

This allows routed access rather than NAT / port-forwarding individual management connections.

---

# pfSense

pfSense provides segmentation and firewall enforcement between the home network and security lab networks.

## Interfaces

| Interface | Address | Purpose |
|---|---|---|
| WAN | `192.168.88.54/24` | Connection to MikroTik / Home LAN |
| LAN | `10.10.10.1/24` | Security lab management/services |
| DMZ | `10.10.20.1/24` | Honeypot / untrusted systems |
| COMPTON | `10.2.3.1/24` | Compton test environment |

---

# Trusted Management Workstation

The primary workstation is:

```text
192.168.88.45
```

It is treated as the trusted administrative endpoint for the lab.

Rather than permitting the entire:

```text
192.168.88.0/24
```

network through pfSense, firewall rules permit only:

```text
192.168.88.45
```

to reach specific management services.

This follows the principle:

```text
DEFAULT DENY

        +

EXPLICITLY ALLOW REQUIRED MANAGEMENT TRAFFIC
```

---

# Management Access Matrix

| System | IP | Service | Port | Allowed Source |
|---|---|---|---:|---|
| T-Pot | `10.10.20.200` | SSH | `64295/TCP` | `192.168.88.45` |
| Security Onion | `10.10.10.201` | SSH | `22/TCP` | `192.168.88.45` |
| Security Onion | `10.10.10.201` | SOC Web UI | `443/TCP` | `192.168.88.45` |
| Elastic LogServer | `10.10.10.200` | SSH | `22/TCP` | `192.168.88.45` |
| Elastic LogServer | `10.10.10.200` | Kibana | `5601/TCP` | `192.168.88.45` |
| FileServer / n8n | `10.10.10.202` | SSH / SCP | `22/TCP` | `192.168.88.45` |
| FileServer / n8n | `10.10.10.202` | SMB | `445/TCP` | `192.168.88.45` |
| FileServer / n8n | `10.10.10.202` | n8n | `5678/TCP` | `192.168.88.45` |

---

# T-Pot Honeypot Platform

## Overview

This lab uses a **T-Pot Standard** deployment as the primary honeypot platform.

```text
T-Pot Host
IP Address:      10.10.20.200/24
Default Gateway: 10.10.20.1
Network:         10.10.20.0/24
Zone:            pfSense DMZ

Administrative SSH:
TCP 64295
```

T-Pot uses Docker to run numerous specialized honeypots simultaneously. Each honeypot is designed to emulate a different type of operating system, network service, application, industrial device, medical device, printer, database, or authentication service.

The installed configuration is the **STANDARD** T-Pot profile.

---

# T-Pot Architecture

```text
                     External / Lab Traffic
                              │
                              ▼
                         pfSense DMZ
                         10.10.20.1
                              │
                              ▼
                      T-Pot 10.10.20.200
                              │
                              ▼
                         Docker Engine
                              │
       ┌──────────────────────┼───────────────────────┐
       │                      │                       │
       ▼                      ▼                       ▼
   Honeypots              NSM Sensors             T-Pot Tools
       │                      │                       │
       │                 ┌────┼────┐                  │
       │                 │    │    │                  │
       │              Suricata│   p0f                 │
       │                    FATT                      │
       │                                              │
       ▼                                              ▼
 Attack Events                                Elasticsearch/Kibana
       │                                              │
       └──────────────────────┬───────────────────────┘
                              ▼
                       Security Analysis
```

The Standard configuration also creates separate Docker networks for most honeypots so that the individual deception services remain logically separated from one another.

---

# T-Pot Honeypot Inventory

| Honeypot | Exposed Port(s) | Primary Purpose |
|---|---:|---|
| **ADBHoney** | `5555/TCP` | Android Debug Bridge |
| **CiscoASA** | `5000/UDP`, `8443/TCP` | Cisco ASA / VPN appliance |
| **Conpot IEC104** | `161/UDP`, `2404/TCP` | ICS / IEC-104 |
| **Conpot Guardian AST** | `10001/TCP` | Industrial monitoring equipment |
| **Conpot IPMI** | `623/UDP` | Server/BMC management |
| **Conpot Kamstrup 382** | `1025`, `50100/TCP` | Smart meter / industrial equipment |
| **Cowrie** | `22`, `23/TCP` | SSH / Telnet |
| **DICOMpot** | `104`, `11112/TCP` | Medical imaging / DICOM |
| **Dionaea** | Multiple | Malware and vulnerable network services |
| **ElasticPot** | `9200/TCP` | Elasticsearch |
| **H0neytr4p** | `443`, `2087/TCP` | HTTPS / web attacks |
| **Heralding** | Multiple authentication ports | Credential attacks |
| **HoneyAML** | `3000/TCP` | API attacks |
| **Honeytrap** | Host networking | General network-service attacks |
| **IPPHoney** | `631/TCP` | Internet Printing Protocol |
| **Mailoney** | `25`, `587/TCP` | SMTP |
| **Medpot** | `2575/TCP` | Medical equipment |
| **Miniprint** | `9100/TCP` | Network printers |
| **RDPHoneypot** | `3389/TCP` | Microsoft RDP |
| **RedisHoneypot** | `6379/TCP` | Redis database |
| **SentryPeer** | `5060/TCP+UDP` | SIP / VoIP |
| **SNARE/TANNER** | `80/TCP` | Web applications |
| **Wordpot** | `8080/TCP` | WordPress |

---

# Honeypot Details

## ADBHoney

Emulates an exposed **Android Debug Bridge (ADB)** service on `5555/TCP`.

Useful for observing:

- ADB discovery
- Unauthorized ADB connections
- Command execution attempts
- Malware deployment
- Automated botnet behavior

---

## CiscoASA

Emulates aspects of a **Cisco ASA security appliance**.

```text
5000/UDP
8443/TCP
```

Useful for detecting:

- Cisco ASA reconnaissance
- VPN appliance scanning
- Firewall-management probes
- Appliance-specific exploitation attempts

---

## Conpot IEC104

Industrial-control honeypot profile exposing:

```text
161/UDP
2404/TCP
```

Useful for observing attacks against:

- SCADA networks
- Power infrastructure
- IEC-104 devices
- Industrial telemetry systems

---

## Conpot Guardian AST

Exposes:

```text
10001/TCP
```

Provides deception for specialized industrial monitoring equipment.

---

## Conpot IPMI

Exposes:

```text
623/UDP
```

Useful for detecting reconnaissance and attack activity against server BMC / out-of-band management infrastructure.

---

## Conpot Kamstrup 382

Exposes:

```text
1025/TCP
50100/TCP
```

Provides additional industrial / smart-meter deception.

---

## Cowrie

Cowrie is the SSH / Telnet honeypot.

```text
22/TCP   SSH Honeypot
23/TCP   Telnet Honeypot
```

The real T-Pot administrative SSH server therefore runs on:

```text
64295/TCP
```

Cowrie can capture:

- SSH brute forcing
- Telnet brute forcing
- Username guessing
- Password spraying
- Default credential attempts
- Shell commands
- Reconnaissance
- Malware download commands
- Botnet behavior
- Terminal sessions

Persistent data includes:

```text
${TPOT_DATA_PATH}/cowrie/downloads
${TPOT_DATA_PATH}/cowrie/keys
${TPOT_DATA_PATH}/cowrie/log
${TPOT_DATA_PATH}/cowrie/log/tty
```

---

## DICOMpot

Medical imaging honeypot for **DICOM**.

```text
104/TCP
11112/TCP
```

Useful for observing reconnaissance targeting:

- PACS servers
- MRI systems
- CT systems
- Radiology infrastructure
- Medical imaging systems

---

## Dionaea

Dionaea emulates a wide range of vulnerable services.

Configured ports include:

```text
20/TCP       FTP Data
21/TCP       FTP
42/TCP
69/UDP       TFTP
81/TCP
135/TCP      RPC
445/TCP      SMB
1433/TCP     MSSQL
1723/TCP     PPTP
1883/TCP     MQTT
3306/TCP     MySQL
27017/TCP    MongoDB
```

It is particularly useful for observing:

- Worms
- Malware loaders
- Automated exploitation
- Network-service scans
- Payload delivery

---

## ElasticPot

Elasticsearch honeypot:

```text
9200/TCP
```

This is intentionally separate from the real Elastic server:

```text
Real Elastic LogServer:
10.10.10.200

T-Pot ElasticPot:
10.10.20.200:9200
```

---

## H0neytr4p

HTTPS-focused honeypot:

```text
443/TCP
2087/TCP
```

Useful for:

- Web vulnerability scanners
- Automated bots
- Malicious HTTP requests
- Control-panel scanning
- Payload delivery attempts

---

## Heralding

Credential-capture honeypot exposing:

```text
110/TCP    POP3
143/TCP    IMAP
465/TCP    SMTPS
993/TCP    IMAPS
995/TCP    POP3S
1080/TCP   SOCKS
5432/TCP   PostgreSQL
5900/TCP   VNC
```

Useful for studying brute force and credential-spraying behavior.

---

## HoneyAML

API-focused honeypot exposed as:

```text
T-Pot TCP 3000
     │
     ▼
Container TCP 8080
```

Useful for API discovery, token probing, authentication attacks, and automated API scanning.

---

## Honeytrap

Runs with:

```text
network_mode: host
```

Provides a flexible network honeypot capable of capturing traffic that may not match the more specialized deception services.

Persistent directories include:

```text
honeytrap/attacks
honeytrap/downloads
honeytrap/log
```

---

## IPPHoney

Internet Printing Protocol honeypot:

```text
631/TCP
```

Useful for detecting printer / CUPS / IPP reconnaissance.

---

## Mailoney

SMTP honeypot:

```text
25/TCP
587/TCP
```

Useful for observing spam bots, relay testing, and SMTP reconnaissance.

---

## Medpot

Medical-device honeypot:

```text
2575/TCP
```

Complements DICOMpot by broadening healthcare-device deception coverage.

---

## Miniprint

Printer honeypot:

```text
9100/TCP
```

Useful for observing raw printing attacks, printer enumeration, and uploads.

---

## RDPHoneypot

Microsoft Remote Desktop honeypot:

```text
3389/TCP
```

Useful for:

- RDP scanning
- Brute force
- Password spraying
- Initial-access attempts

---

## RedisHoneypot

Redis database honeypot:

```text
6379/TCP
```

Useful for detecting exposed-Redis reconnaissance and exploitation attempts.

---

## SentryPeer

SIP / VoIP honeypot:

```text
5060/TCP
5060/UDP
```

Useful for detecting attacks against SIP servers, PBXs, and VoIP infrastructure.

---

## SNARE / TANNER

Web application deception stack using:

```text
tanner_redis
tanner_phpox
tanner_api
tanner
snare
```

Externally exposed through:

```text
80/TCP
```

Useful for web scanning, injection attempts, malicious parameters, and automated exploitation.

---

## Wordpot

WordPress honeypot:

```text
8080/TCP → container TCP 80
```

Useful for observing:

- `/wp-admin` enumeration
- Login attacks
- Plugin scanning
- Theme scanning
- WordPress exploit attempts

---

# T-Pot Honeypot Exposure Summary

```text
T-Pot 10.10.20.200
│
├── 22       Cowrie SSH
├── 23       Cowrie Telnet
├── 25       Mailoney SMTP
├── 80       SNARE/TANNER
├── 104      DICOMpot
├── 110      Heralding POP3
├── 135      Dionaea RPC
├── 143      Heralding IMAP
├── 161/UDP  Conpot IEC104
├── 445      Dionaea SMB
├── 465      Heralding SMTPS
├── 587      Mailoney SMTP
├── 623/UDP  Conpot IPMI
├── 631      IPPHoney
├── 993      Heralding IMAPS
├── 995      Heralding POP3S
├── 1025     Conpot Kamstrup
├── 1080     Heralding SOCKS
├── 1433     Dionaea MSSQL
├── 1723     Dionaea PPTP
├── 1883     Dionaea MQTT
├── 2087     H0neytr4p
├── 2404     Conpot IEC104
├── 2575     Medpot
├── 3000     HoneyAML
├── 3306     Dionaea MySQL
├── 3389     RDPHoneypot
├── 5000/UDP CiscoASA
├── 5060     SentryPeer TCP/UDP
├── 5432     Heralding PostgreSQL
├── 5555     ADBHoney
├── 5900     Heralding VNC
├── 6379     RedisHoneypot
├── 8080     Wordpot
├── 8443     CiscoASA
├── 9100     Miniprint
├── 9200     ElasticPot
├── 10001    Conpot Guardian AST
├── 11112    DICOMpot
├── 27017    Dionaea MongoDB
└── 50100    Conpot Kamstrup
```

---

# T-Pot Network Security Monitoring Components

T-Pot Standard also runs Network Security Monitoring components.

## FATT

FATT performs network metadata extraction and runs in host networking mode.

Persistent logs:

```text
${TPOT_DATA_PATH}/fatt/log
```

---

## p0f

p0f provides passive operating-system fingerprinting by analyzing TCP/IP characteristics without actively probing the remote system.

---

## Suricata

Suricata provides IDS / network-security monitoring capabilities.

It can generate:

- IDS signatures
- Protocol metadata
- Attack alerts
- Network indicators

---

# T-Pot Internal Elastic Stack

T-Pot Standard includes its own internal Elastic Stack:

```text
Elasticsearch
Kibana
Logstash
```

This is separate from the standalone Elastic LogServer at:

```text
10.10.10.200
```

## Internal Elasticsearch

```text
127.0.0.1:64298 → Elasticsearch:9200
```

Configured with approximately:

```text
JVM Heap: 2 GB
Container Memory Limit: 4 GB
```

## Internal Kibana

```text
127.0.0.1:64296 → Kibana:5601
```

## Internal Logstash

```text
127.0.0.1:64305
```

The real Elastic/Kibana services are therefore separated from the public honeypot ports.

---

# T-Pot nginx Frontend

T-Pot includes nginx exposing:

```text
64294/TCP
64297/TCP
```

nginx acts as the frontend for T-Pot web-based management and visualization components.

---

# T-Pot Attack Map

The Standard installation includes:

```text
map_redis
map_web
map_data
```

Conceptually:

```text
Honeypots
    │
    ▼
Logstash
    │
    ▼
Elasticsearch
    │
    ├──────────────► Kibana
    │
    └──────────────► Attack Map
```

---

# SpiderFoot

SpiderFoot is included as a supporting OSINT / reconnaissance tool.

```text
127.0.0.1:64303 → SpiderFoot:8080
```

---

# EWSPoster

EWSPoster processes and can forward honeypot events to external sharing systems.

In this deployment:

```text
EWS_HPFEEDS_ENABLE=false
```

so HPFeeds forwarding is disabled by default.

---

# T-Pot Data Flow

```text
                 Incoming Attack
                       │
                       ▼
                   Honeypot
                       │
          ┌────────────┴────────────┐
          │                         │
          ▼                         ▼
     Honeypot Logs             Network Traffic
          │                         │
          │                 ┌───────┼────────┐
          │                 │       │        │
          │                 ▼       ▼        ▼
          │              Suricata  p0f      FATT
          │
          ▼
       Logstash
          │
          ▼
    Elasticsearch
          │
       ┌──┴────────────┐
       │               │
       ▼               ▼
     Kibana        Attack Map
```

---

# T-Pot + Security Onion

This lab adds another monitoring layer beyond the normal T-Pot Standard design.

Traffic involving T-Pot is mirrored by the Proxmox host to the Security Onion monitoring interface.

```text
                   Attacker / Scanner
                          │
                          ▼
                    T-Pot Honeypot
                     10.10.20.200
                          │
              ┌───────────┴───────────┐
              │                       │
              ▼                       ▼
       Application Logs          Network Traffic
              │                       │
              ▼                       ▼
       T-Pot Elastic            Proxmox Mirror
                                      │
                                      ▼
                               Security Onion
                                10.10.10.201
                                      │
                         ┌────────────┼────────────┐
                         │            │            │
                         ▼            ▼            ▼
                       Zeek       Suricata     Network
                                              Telemetry
```

This provides both application-level and network-level visibility into attacks.

---

# Proxmox Traffic Mirroring

Traffic mirroring is implemented using Linux `tc`.

Hookscript:

```text
/var/lib/vz/snippets/tpot-mirror.sh
```

Relevant VMs:

```text
VM 101  Security Onion
VM 107  T-Pot
```

The mirror copies T-Pot ingress and egress traffic to the Security Onion monitoring interface without placing Security Onion inline.

---

# T-Pot Management Security

T-Pot should be considered an **untrusted system** because its purpose is to intentionally interact with hostile traffic.

It is therefore isolated on:

```text
DMZ
10.10.20.0/24
```

rather than on:

```text
Security LAN
10.10.10.0/24
```

Administrative SSH:

```text
10.10.20.200:64295
```

Allowed only from:

```text
192.168.88.45
```

---

# T-Pot Return Route

T-Pot creates several large Docker networks. One overlaps with the `192.168.88.0/24` management network.

A specific host route is therefore used:

```text
192.168.88.45/32
        │
        ▼
10.10.20.1
        │
        ▼
pfSense
```

This prevents replies to the management workstation from being incorrectly sent into a Docker bridge.

---

# Important T-Pot Port Separation

```text
TCP 22
   │
   └── Cowrie Honeypot
       NOT real SSH

TCP 64295
   │
   └── Real T-Pot Administrative SSH
```

Likewise:

```text
TCP 9200
   │
   └── ElasticPot Honeypot

127.0.0.1:64298
   │
   └── Real internal T-Pot Elasticsearch
```

---

# Security Onion

## Address

```text
10.10.10.201
```

Administrative access from the trusted workstation:

```text
22/TCP   SSH
443/TCP  SOC Web UI
```

Security Onion was also configured to authorize the management workstation in its host firewall:

```bash
sudo so-firewall includehost analyst 192.168.88.45
sudo so-firewall apply
```

---

# Elastic LogServer

## Address

```text
10.10.10.200
```

Relevant services include:

```text
22/TCP     SSH
5601/TCP   Kibana
9200/TCP   Elasticsearch
```

Only the required workstation-management services are permitted through pfSense:

```text
192.168.88.45 → 10.10.10.200:22
192.168.88.45 → 10.10.10.200:5601
```

The LogServer previously had both `10.10.10.104` and `10.10.10.200` assigned due to an old DHCP NetworkManager profile. The obsolete DHCP profile was removed, leaving:

```text
ens18  UP  10.10.10.200/24
```

---

# n8n / File Server

## Address

```text
10.10.10.202
```

This Ubuntu Server provides:

```text
22/TCP     SSH / SCP
445/TCP    SMB
5678/TCP   n8n
```

### SSH / SCP

```bash
ssh grey@10.10.10.202
```

```bash
scp file.txt grey@10.10.10.202:/destination/
```

### SMB

Windows access:

```text
\\10.10.10.202
```

Modern SMB access uses TCP `445`; TCP `139` is not required for the current setup.

### n8n

```text
http://10.10.10.202:5678
```

---

# Overall Traffic Flow

```text
Main Workstation
192.168.88.45
       │
       ▼
MikroTik
192.168.88.1
       │
       │ Static Routes
       ▼
pfSense WAN
192.168.88.54
       │
       ├─────────────► LAN
       │               10.10.10.0/24
       │
       │               ├── Elastic
       │               │   10.10.10.200
       │               │
       │               ├── Security Onion
       │               │   10.10.10.201
       │               │
       │               └── FileServer / n8n
       │                   10.10.10.202
       │
       └─────────────► DMZ
                       10.10.20.0/24
                              │
                              └── T-Pot
                                  10.10.20.200
```

---

# Firewall Philosophy

The management design follows a least-privilege model.

Instead of:

```text
192.168.88.0/24
        │
        ▼
ALLOW EVERYTHING
        │
        ▼
Security Lab
```

the configuration uses:

```text
192.168.88.45
        │
        ▼
ONLY REQUIRED PORTS
        │
        ▼
SPECIFIC LAB SERVER
```

Current management rules include:

```text
192.168.88.45 → 10.10.20.200:64295
192.168.88.45 → 10.10.10.201:22
192.168.88.45 → 10.10.10.201:443
192.168.88.45 → 10.10.10.200:22
192.168.88.45 → 10.10.10.200:5601
192.168.88.45 → 10.10.10.202:22
192.168.88.45 → 10.10.10.202:445
192.168.88.45 → 10.10.10.202:5678
```

Everything else remains subject to the normal pfSense deny policy.

---

# Quick Reference

## Main Workstation

```text
IP:   192.168.88.45
Role: Trusted administrative workstation
```

## MikroTik

```text
Gateway: 192.168.88.1

Static Route:
10.10.10.0/24 → 192.168.88.54

Static Route:
10.10.20.0/24 → 192.168.88.54
```

## pfSense

```text
WAN:     192.168.88.54/24
LAN:     10.10.10.1/24
DMZ:     10.10.20.1/24
COMPTON: 10.2.3.1/24
```

## T-Pot

```text
IP:  10.10.20.200
SSH: 64295
```

```bash
ssh -p 64295 grey@10.10.20.200
```

## Security Onion

```text
IP:   10.10.10.201
SSH:  22
Web:  HTTPS/443
```

## Elastic LogServer

```text
IP:            10.10.10.200
SSH:           22
Kibana:        5601
Elasticsearch: 9200 internal / service use
```

## FileServer / n8n

```text
IP:       10.10.10.202
SSH/SCP:  22
SMB:      445
n8n:      5678
```

---

# Summary

This environment combines:

- MikroTik routing
- pfSense segmentation and least-privilege firewalling
- Proxmox virtualization
- T-Pot Standard multi-honeypot deception
- Security Onion network-security monitoring
- Elastic/Kibana centralized logging
- n8n automation
- Samba file services
- Proxmox traffic mirroring
- Restricted management access from a single workstation

The result is a compact but capable blue-team and attack-analysis lab that provides both **deception telemetry** and **network-level visibility** while maintaining clear security boundaries between trusted management systems and intentionally exposed honeypot services.
