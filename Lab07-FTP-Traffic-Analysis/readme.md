# Lab 7: FTP Traffic Analysis – Detecting Cleartext Credential Exposure Using Wireshark

## Overview

This lab demonstrates why the File Transfer Protocol (FTP) is considered an insecure protocol. FTP sends usernames, passwords, and commands in cleartext, allowing anyone with network access to capture sensitive credentials using a packet analyzer like Wireshark.

In this lab, an FTP login session was generated between a Kali Linux client and an Ubuntu FTP server. The captured packets were analyzed to identify authentication details and FTP commands.

---

## Objective

- Understand how FTP authentication works.
- Capture FTP traffic using Wireshark.
- Identify usernames and passwords transmitted in plaintext.
- Analyze FTP commands exchanged between client and server.
- Learn why FTP should be replaced with secure alternatives such as SFTP or FTPS.

---

## Lab Environment

| Component | Details |
|-----------|---------|
| Client Machine | Kali Linux |
| Server Machine | Ubuntu Linux (vsftpd FTP Server) |
| Analysis Tool | Wireshark |
| Protocol | FTP (Port 21) |

---

## Network Information

| Device | IP Address |
|---------|------------|
| Kali Linux | 192.168.1.4 |
| Ubuntu FTP Server | 192.168.1.5 |

---

## Procedure

1. Started Wireshark capture on Kali Linux.
2. Connected to the Ubuntu FTP server.
3. Logged in using FTP credentials.
4. Executed basic FTP commands.
5. Stopped packet capture.
6. Filtered packets using:

```
ftp
```

7. Followed the TCP Stream.
8. Examined USER and PASS packets.
9. Identified FTP commands exchanged during the session.

---

## Wireshark Filters Used

### Display FTP Packets

```
ftp
```

### Find Login Commands

```
ftp.request.command == "USER"
```

```
ftp.request.command == "PASS"
```

### Follow Entire Conversation

```
Right Click → Follow → TCP Stream
```

---

## Key Findings

- Username transmitted in plaintext.
- Password transmitted in plaintext.
- FTP server banner visible.
- Login successful.
- Directory listing commands observed.
- File management commands visible.
- No encryption is used by FTP.

---

## Evidence Collected

- USER command
- PASS command
- FTP Login Success
- TCP Stream
- Directory Listing
- FTP Commands

---

## Security Risk

FTP provides no encryption.

An attacker connected to the same network can capture:

- Usernames
- Passwords
- File names
- Directory structure
- FTP commands

This makes FTP unsuitable for production environments.

---

## Mitigation

- Replace FTP with SFTP.
- Use FTPS where FTP compatibility is required.
- Disable anonymous login.
- Restrict FTP access using firewall rules.
- Monitor FTP authentication events using a SIEM solution.

---

## Skills Gained

- FTP Packet Analysis
- Credential Hunting
- Network Traffic Analysis
- Wireshark Investigation
- SOC Investigation
- Incident Analysis

---

## Tools Used

- Kali Linux
- Ubuntu Linux
- vsftpd
- Wireshark

---

## Learning Outcome

This lab demonstrates one of the most common security weaknesses still found in legacy environments—cleartext credential transmission over FTP. A SOC analyst must quickly identify this issue and recommend migration to encrypted protocols.
