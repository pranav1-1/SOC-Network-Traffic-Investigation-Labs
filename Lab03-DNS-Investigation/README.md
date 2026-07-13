# Lab 3 – DNS Investigation

## Objective

To analyze Domain Name System (DNS) traffic using Wireshark and understand how domain names are resolved into IP addresses. This lab demonstrates how SOC analysts investigate DNS queries, responses, and identify suspicious DNS activity.

---

## Lab Environment

| Device | IP Address |
|----------|------------|
| Kali Linux | 192.168.1.5 |
| Ubuntu Server | 192.168.1.6 |
| Tool | Wireshark |

---

## Protocol Covered

- DNS (Domain Name System)

---

## Tasks Performed

- Started packet capture in Wireshark.
- Generated DNS traffic using `nslookup` and web browsing.
- Captured DNS query and response packets.
- Analyzed Transaction IDs, Query Names, Record Types, and Response Codes.
- Identified the configured DNS server.
- Verified successful domain name resolution.

---

## Wireshark Filters Used

```text
dns
```

```text
ip.addr == 192.168.1.5
```

---

## Key Findings

- DNS queries were successfully resolved.
- DNS responses returned valid IPv4 addresses (A Records).
- Transaction IDs matched between queries and responses.
- No failed lookups (NXDOMAIN) or suspicious DNS activity was observed.

---

## Skills Learned

- DNS packet analysis
- DNS query and response investigation
- DNS record analysis
- DNS troubleshooting
- Network traffic investigation using Wireshark

---

## Screenshots


---

## Conclusion

This lab demonstrated how DNS translates domain names into IP addresses and how DNS traffic can be analyzed using Wireshark. Understanding DNS is essential for SOC analysts to investigate phishing, malware communications, DNS tunneling, and other network-based threats.

---

## SOC Analyst Takeaway

This lab strengthened my understanding of DNS protocol analysis by examining queries, responses, transaction IDs, and record types. These skills are essential for detecting suspicious domain activity and investigating potential cybersecurity incidents.
