# SMB File Sharing Investigation Report

## Incident Summary

An alert was generated indicating SMB file-sharing activity between two internal systems. The objective of this investigation was to determine whether the observed activity represented legitimate user behavior or suspicious access.

---

# Investigation Details

| Item | Value |
|------|-------|
| Investigation Type | SMB Traffic Analysis |
| Protocol | SMB2 |
| Client | Kali Linux |
| Server | Ubuntu Samba Server |
| Client IP | 192.168.1.5 |
| Server IP | 192.168.1.7 |
| Destination Port | TCP 445 |
| Tool Used | Wireshark |

---

# Investigation Steps

1. Started packet capture using Wireshark.
2. Connected from Kali Linux to the Ubuntu Samba share.
3. Accessed the shared folder.
4. Viewed existing files.
5. Created a test file.
6. Copied the file into the SMB share.
7. Renamed the file.
8. Deleted the file.
9. Stopped packet capture.
10. Applied the SMB2 display filter.

---

# Evidence Collected

## Network Traffic

Display Filter

```
smb2
```

Observed Operations

- SMB2 Negotiate Protocol
- SMB2 Session Setup
- SMB2 Tree Connect
- SMB2 Create Request
- SMB2 Read Request
- SMB2 Write Request
- SMB2 Close Request

---

# Packet Analysis

## Source Host

Kali Linux
192.168.1.5

## Destination Host

Ubuntu Samba Server
192.168.1.7

## Destination Port

445/TCP

## Protocol

SMB2

---

# Findings

The packet capture showed successful SMB2 communication between the Kali Linux client and the Ubuntu Samba server.

The client successfully connected to the shared folder and performed normal file operations including reading, writing, renaming, and deleting files.

No suspicious behavior such as unauthorized access attempts, abnormal authentication failures, or unusual file operations was identified.

---

# Security Assessment

Risk Level: Low

Reason:

The observed SMB traffic matched expected administrative and file-sharing activities performed during the laboratory exercise.

---

# SOC Analyst Observations

- SMB2 was used instead of SMBv1, indicating a modern and more secure configuration.
- Authentication completed successfully.
- File operations were completed without errors.
- No evidence of lateral movement or malicious file activity was observed.

---

# Recommendations

- Continue using SMB2/SMB3 and keep SMBv1 disabled.
- Restrict SMB access to authorized users.
- Monitor SMB write operations for unusual file modifications.
- Enable logging and alerting for failed authentication attempts.
- Regularly review SMB activity for signs of lateral movement.

---

# Conclusion

The SMB traffic observed during this investigation represents legitimate file-sharing activity between the Kali Linux client and the Ubuntu Samba server. The investigation confirmed successful SMB session establishment and normal file operations. No indicators of compromise or malicious activity were identified.

---

# Analyst

Pranav R Pillai

SOC Analyst Home Lab

Date: July 2026
