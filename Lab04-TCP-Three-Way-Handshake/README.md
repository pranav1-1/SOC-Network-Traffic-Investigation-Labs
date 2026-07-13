# Lab 4 – TCP Three-Way Handshake Investigation

## Objective

To analyze the TCP Three-Way Handshake using Wireshark and understand how reliable network connections are established and terminated. This lab demonstrates how SOC analysts investigate TCP sessions, ports, flags, and connection states during network communication.

---

## Lab Environment

| Device | IP Address |
|----------|------------|
| Kali Linux | 192.168.1.5 |
| Ubuntu Server | 192.168.1.6 |
| Service | Apache Web Server |
| Tool | Wireshark |

---

## Protocol Covered

- TCP (Transmission Control Protocol)

---

## Tasks Performed

- Started packet capture using Wireshark.
- Generated HTTP traffic from Kali to the Ubuntu Apache server.
- Applied TCP display filters.
- Identified the TCP Three-Way Handshake.
- Analyzed TCP Flags (SYN, SYN-ACK, ACK, FIN).
- Examined source and destination ports.
- Investigated sequence and acknowledgment numbers.
- Followed the TCP Stream.
- Verified graceful connection termination using FIN/ACK packets.

---

## Wireshark Filters Used

```text
tcp
```

```text
ip.addr == 192.168.1.5 && ip.addr == 192.168.1.6
```

---

## TCP Three-Way Handshake

1. SYN – Client requests a connection.
2. SYN-ACK – Server acknowledges the request and responds.
3. ACK – Client confirms the connection.

After these three steps, the TCP session is successfully established.

---

## Key Findings

- TCP connection was established successfully.
- Client initiated communication with the web server.
- Destination port 80 (HTTP) was used.
- TCP flags followed the expected sequence (SYN → SYN-ACK → ACK).
- Connection closed gracefully using FIN/ACK.
- No abnormal TCP Reset (RST) packets were observed.

---

## Skills Learned

- TCP packet analysis
- Three-Way Handshake investigation
- TCP Flags analysis
- Port analysis
- Sequence & Acknowledgment Number analysis
- TCP Stream reconstruction
- Network troubleshooting
- Wireshark traffic analysis

---


---

## Conclusion

This lab demonstrated how TCP establishes reliable communication using the Three-Way Handshake and terminates sessions gracefully. Understanding TCP sessions, flags, ports, and packet flow is essential for SOC analysts investigating suspicious network activity, malware communications, and intrusion attempts.

---

## SOC Analyst Takeaway

This lab strengthened my understanding of TCP connection establishment, session management, and packet analysis using Wireshark. These skills are fundamental for investigating network-based attacks, identifying connection anomalies, and performing incident response in a Security Operations Center (SOC).
