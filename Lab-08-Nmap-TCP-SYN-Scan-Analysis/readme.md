# Lab 8: Nmap TCP SYN Port Scan Analysis Using Wireshark

## Overview

This lab demonstrates how to detect and analyze an Nmap TCP SYN port scan using Wireshark. The objective is to understand how reconnaissance activity appears in packet captures and how SOC analysts identify port scanning attempts before an attack begins.

---

## Objective

- Generate an Nmap SYN scan against a target host.
- Capture the network traffic using Wireshark.
- Analyze TCP SYN packets.
- Identify open, closed, and filtered ports.
- Understand how reconnaissance appears from a defender's perspective.

---

## Lab Environment

| Device | IP Address | Role |
|---------|------------|------|
| Kali Linux | 192.168.1.4 | Attacker / Scanner |
| Ubuntu Server | 192.168.1.5 | Target |
| Tool Used | Nmap | Port Scanner |
| Packet Analyzer | Wireshark | Traffic Analysis |

---

## Scan Performed

Example command:

```bash
sudo nmap -sS 192.168.1.5
```

---

## Wireshark Filter

```
tcp.flags.syn==1 && tcp.flags.ack==0
```

This filter displays TCP SYN packets sent by the scanner.

---

## Investigation Steps

1. Start packet capture in Wireshark.
2. Execute the Nmap SYN scan.
3. Apply the SYN packet filter.
4. Observe destination ports.
5. Identify responses from the target.
6. Determine which ports are open or closed.
7. Document the reconnaissance activity.

---

## Key Findings

- Large number of SYN packets sent from one source.
- Multiple destination ports targeted.
- Minimal TCP connections completed.
- Pattern matches an Nmap TCP SYN ("Half-Open") scan.
- Reconnaissance activity detected successfully.

---

## Skills Learned

- Nmap reconnaissance
- TCP SYN scan analysis
- Wireshark packet filtering
- Port scan detection
- SOC investigation workflow
- Network traffic analysis

---

## MITRE ATT&CK Mapping

| Technique | ID |
|------------|----|
| Active Scanning | T1595 |
| Network Service Discovery | T1046 |

---

## Screenshots

- Nmap SYN Scan
- SYN Packet Filter
- Multiple Destination Ports
- Packet Details
- TCP Flags Analysis

---

## Conclusion

This lab demonstrates how Wireshark can identify Nmap SYN scans by analyzing TCP SYN packets sent to multiple ports. Such reconnaissance is often the first phase of an attack and should be detected and investigated by SOC analysts.
