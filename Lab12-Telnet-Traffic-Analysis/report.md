# Telnet Traffic Investigation Report

## Incident Summary

The Security Operations Center (SOC) received an alert indicating that a legacy Linux server was accessed using the Telnet protocol. Because Telnet transmits data without encryption, the session was investigated to determine whether sensitive information was exposed during communication.

---

# Investigation Details

| Item | Value |
|------|-------|
| Investigation Type | Telnet Traffic Analysis |
| Protocol | Telnet |
| Client | Kali Linux |
| Server | Ubuntu Server |
| Client IP | 192.168.1.5 |
| Server IP | 192.168.1.7 |
| Destination Port | TCP 23 |
| Tool Used | Wireshark |

---

# Investigation Steps

1. Enabled the Telnet service on the Ubuntu server.
2. Started packet capture using Wireshark.
3. Connected from Kali Linux to the Telnet server.
4. Logged in using a valid Ubuntu user account.
5. Executed Linux commands.
6. Closed the Telnet session.
7. Stopped packet capture.
8. Applied the `telnet` display filter.
9. Used **Follow TCP Stream** to inspect the Telnet session.

---

# Evidence Collected

## Display Filter

```
telnet
```

Observed Traffic

- TCP Connection
- Telnet Session
- User Authentication
- Command Execution
- Session Termination

---

# Packet Analysis

## Source Host

Kali Linux

192.168.1.5

## Destination Host

Ubuntu Server

192.168.1.7

## Destination Port

23/TCP

## Protocol

Telnet

---

# Investigation Findings

The packet capture showed a successful Telnet connection initiated from the Kali Linux client to the Ubuntu server over TCP port 23.

The user authenticated successfully and executed several Linux commands including:

- whoami
- hostname
- pwd
- ls
- exit

Using the **Follow TCP Stream** feature, the Telnet session contents were visible because the protocol does not encrypt communication.

---

# Security Assessment

Risk Level: High

Reason:

Telnet transmits authentication data and user commands without encryption, allowing an attacker with network access to intercept sensitive information.

---

# SOC Analyst Observations

- Remote administration was performed using Telnet.
- Communication occurred over TCP port 23.
- Session data was transmitted in clear text.
- Legacy protocols such as Telnet should not be used in production environments.

---

# Recommendations

- Disable the Telnet service.
- Replace Telnet with SSH for secure remote administration.
- Block TCP port 23 unless absolutely required.
- Monitor for Telnet connections in enterprise environments.
- Review systems using legacy protocols and migrate them to secure alternatives.

---

# Conclusion

The investigation confirmed successful Telnet communication between the Kali Linux client and the Ubuntu server. Because the protocol does not provide encryption, the session represents a significant security risk. Organizations should replace Telnet with SSH to protect administrative communications.

---

# Analyst

Pranav R Pillai

SOC Analyst Home Lab

Date: July 2026
