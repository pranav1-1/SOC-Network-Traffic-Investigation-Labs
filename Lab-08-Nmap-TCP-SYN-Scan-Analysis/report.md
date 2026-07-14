# Investigation Report

## Lab Title

Nmap TCP SYN Port Scan Analysis Using Wireshark

---

# Scenario

A SOC analyst receives an alert indicating that a workstation is sending TCP SYN packets to many different ports on an internal server.

The analyst investigates the packet capture to determine whether the activity is normal or reconnaissance.

---

# Objective

Identify whether the observed traffic is an Nmap TCP SYN scan.

---

# Environment

| Component | Details |
|-----------|----------|
| Scanner | Kali Linux |
| Scanner IP | 192.168.1.4 |
| Target | Ubuntu Server |
| Target IP | 192.168.1.5 |
| Tool | Nmap |
| Analyzer | Wireshark |

---

# Capture Details

Capture Tool:
Wireshark

Protocol:
TCP

Display Filter:

```
tcp.flags.syn==1 && tcp.flags.ack==0
```

---

# Evidence Collected

## Source IP

192.168.1.4

---

## Destination IP

192.168.1.5

---

## Protocol

TCP

---

## Destination Ports Observed

- 21 (FTP)
- 22 (SSH)
- 23 (Telnet)
- 53 (DNS)
- 80 (HTTP)
- 110 (POP3)
- 135 (RPC)
- 139 (NetBIOS)
- 143 (IMAP)
- 443 (HTTPS)
- 445 (SMB)
- 554 (RTSP)
- 993 (IMAPS)
- 995 (POP3S)
- 1723 (PPTP)
- 3306 (MySQL)
- 3389 (RDP)
- 5900 (VNC)
- 8888
- Additional ports

---

# Packet Analysis

The capture shows numerous TCP SYN packets originating from the scanner (192.168.1.4) to the target (192.168.1.5). Each packet targets a different destination port without immediately completing the TCP three-way handshake.

This behavior is consistent with an Nmap TCP SYN (half-open) scan.

---

# Indicators of Reconnaissance

- High number of SYN packets
- Sequential port enumeration
- Single source scanning one target
- Half-open connection attempts
- Multiple service ports targeted

---

# Security Impact

An attacker is attempting to discover:

- Open services
- Running applications
- Exposed network ports
- Potential attack vectors

Reconnaissance is typically the first stage of a cyber attack.

---

# MITRE ATT&CK

| Technique | ID |
|-----------|----|
| Active Scanning | T1595 |
| Network Service Discovery | T1046 |

---

# SOC Analyst Actions

✔ Verify source system ownership

✔ Determine whether the scan was authorized

✔ Review firewall and IDS logs

✔ Correlate with endpoint telemetry

✔ Block malicious source if necessary

✔ Escalate if scanning is unauthorized

---

# Detection Logic

Look for:

- Numerous SYN packets
- Multiple destination ports
- Short time interval
- Same source IP
- Incomplete TCP handshakes

---

# Conclusion

The packet capture confirms an Nmap TCP SYN port scan originating from **192.168.1.4** targeting **192.168.1.5**. The activity represents reconnaissance intended to identify exposed services. Early detection of such scans allows SOC analysts to respond before attackers progress to exploitation.
