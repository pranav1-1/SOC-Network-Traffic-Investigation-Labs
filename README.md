# 🛡️ SOC Network Traffic Investigation Labs

> A hands-on SOC Analyst home lab project focused on network traffic analysis, protocol investigation, and packet-level forensics using Wireshark.

![Platform](https://img.shields.io/badge/Platform-Kali%20Linux%20%7C%20Ubuntu-blue)
![Tool](https://img.shields.io/badge/Tool-Wireshark-orange)
![Focus](https://img.shields.io/badge/Focus-Network%20Traffic%20Analysis-red)
![Level](https://img.shields.io/badge/Level-SOC%20Analyst-success)

---

# 📖 Overview

This repository documents my practical journey in learning **Network Traffic Analysis** from the perspective of a **Security Operations Center (SOC) Analyst**.

Instead of simply studying networking concepts, each lab simulates a realistic enterprise scenario where network traffic is captured and investigated using **Wireshark**.

The goal is to develop practical skills in packet analysis, protocol investigation, incident documentation, and threat detection that align with the responsibilities of a Tier-1 SOC Analyst.

---

# 🎯 Project Objectives

- Build a complete SOC home lab from scratch.
- Learn how common network protocols operate.
- Capture and analyze network traffic using Wireshark.
- Understand normal and suspicious network behavior.
- Investigate network communications like a SOC Analyst.
- Develop professional incident investigation and reporting skills.
- Build a GitHub portfolio showcasing practical cybersecurity skills.

---

# 🖥️ Lab Environment

| Component | Details |
|-----------|----------|
| Virtualization | Oracle VirtualBox |
| Attacker Machine | Kali Linux |
| Target Machine | Ubuntu Server |
| Packet Analyzer | Wireshark |
| Network Type | Host-Only Network |
| Communication | Client ↔ Server |

---

# 🛠️ Tools & Technologies

- Wireshark
- Kali Linux
- Ubuntu Server
- Oracle VirtualBox
- Nmap
- OpenSSH
- Samba (SMB)
- Telnet
- FTP
- Apache HTTP Server
- DNS Utilities
- DHCP

---

# 🧠 Skills Demonstrated

- Network Traffic Analysis
- Packet Capture
- Protocol Analysis
- TCP/IP Fundamentals
- Network Forensics
- Incident Investigation
- Security Monitoring
- IOC Identification
- Threat Detection
- Wireshark Analysis
- Technical Documentation

---

# 📚 Labs Included

| Lab | Investigation | Protocol | SOC Relevance |
|------|--------------|----------|---------------|
| **Lab 01** | SOC Home Lab Environment Setup | VirtualBox, Kali, Ubuntu | ⭐⭐⭐⭐⭐ |
| **Lab 02** | ARP & ICMP Investigation | ARP / ICMP | ⭐⭐⭐⭐ |
| **Lab 03** | TCP Three-Way Handshake Analysis | TCP | ⭐⭐⭐⭐ |
| **Lab 04** | DNS Investigation | DNS | ⭐⭐⭐⭐⭐ |
| **Lab 05** | HTTP Traffic Analysis | HTTP | ⭐⭐⭐⭐⭐ |
| **Lab 06** | HTTPS/TLS Traffic Analysis | HTTPS / TLS | ⭐⭐⭐⭐⭐ |
| **Lab 07** | FTP Traffic Analysis | FTP | ⭐⭐⭐ |
| **Lab 08** | Nmap Port Scan Detection | TCP | ⭐⭐⭐⭐⭐ |
| **Lab 09** | SSH Traffic Analysis | SSH | ⭐⭐⭐⭐⭐ |
| **Lab 10** | DHCP Traffic Analysis | DHCP | ⭐⭐⭐ |
| **Lab 11** | SMB File Sharing Investigation | SMB2 | ⭐⭐⭐⭐⭐ |
| **Lab 12** | Telnet Traffic Analysis | Telnet | ⭐⭐⭐⭐ |

---

# 📂 Repository Structure

```
SOC-Network-Traffic-Investigation-Labs/

│
├── Lab-01-SOC-Home-Lab-Environment-Setup/
├── Lab-02-ARP-ICMP-Investigation/
├── Lab-03-TCP-Three-Way-Handshake/
├── Lab-04-DNS-Investigation/
├── Lab-05-HTTP-Traffic-Analysis/
├── Lab-06-HTTPS-TLS-Traffic-Analysis/
├── Lab-07-FTP-Traffic-Analysis/
├── Lab-08-Nmap-Port-Scan-Detection/
├── Lab-09-SSH-Traffic-Analysis/
├── Lab-10-DHCP-Traffic-Analysis/
├── Lab-11-SMB-File-Sharing-Investigation/
├── Lab-12-Telnet-Traffic-Analysis/
└── README.md
```

---

# 🔎 Investigation Workflow

```text
Environment Setup
        │
        ▼
Generate Network Traffic
        │
        ▼
Capture Packets using Wireshark
        │
        ▼
Apply Display Filters
        │
        ▼
Inspect Packet Details
        │
        ▼
Analyze Protocol Behavior
        │
        ▼
Identify Findings
        │
        ▼
Prepare Investigation Report
```

---

# 📁 Contents of Each Lab

Each lab contains the following files:

```text
README.md
report.md
Capture/
    └── lab.pcapng
Screenshots/
```

---

# 🎓 Learning Outcomes

After completing these labs, I gained practical experience in:

- Building a SOC home lab using VirtualBox
- Configuring Kali Linux and Ubuntu Server
- Setting up Host-Only networking
- Capturing packets using Wireshark
- Understanding Layer 2 to Layer 7 protocols
- Investigating network communications
- Detecting reconnaissance activities
- Analyzing client-server interactions
- Investigating secure and insecure protocols
- Documenting investigations professionally

---

# 📖 Protocols Covered

- ARP
- ICMP
- TCP
- DNS
- HTTP
- HTTPS
- FTP
- SSH
- DHCP
- SMB2
- Telnet

---

# 🎯 SOC Analyst Skills Developed

✅ Packet Analysis

✅ Protocol Investigation

✅ TCP/IP Analysis

✅ Network Forensics

✅ Traffic Correlation

✅ Incident Investigation

✅ IOC Identification

✅ Threat Detection

✅ Wireshark Analysis

✅ Technical Documentation

---

# 🚀 Future Work

The next repository in this series focuses on real-world SOC detection and incident response scenarios.

Upcoming investigations include:

- SSH Brute Force Detection (Hydra)
- SQL Injection Detection
- Malware Download Investigation
- DNS Tunneling Detection
- Reverse Shell Detection
- Web Shell Upload Investigation
- Ransomware Traffic Analysis
- IOC-Based Incident Investigation
- Wazuh Detection Labs
- Splunk Detection Labs

---

# 👨‍💻 Author

## Pranav R Pillai

**M.Sc. Cyber Forensics & Information Security**

Aspiring SOC Analyst | Network Security | Digital Forensics | Threat Detection

---

# ⚠️ Disclaimer

All activities in this repository were performed in an isolated virtual laboratory environment for educational and cybersecurity learning purposes only.

The tools and techniques demonstrated here should only be used on systems that you own or have explicit authorization to test.

---

# ⭐ Acknowledgement

If you found this repository useful, consider giving it a ⭐ on GitHub.
It motivates me to continue building and sharing practical SOC Analyst projects.
