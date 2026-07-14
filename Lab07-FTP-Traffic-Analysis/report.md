# Investigation Report

# Lab 7 – FTP Traffic Analysis and Cleartext Credential Detection

---

## Incident Summary

During routine network monitoring, the SOC team observed FTP traffic between an internal workstation and an FTP server. Since FTP is an unencrypted protocol, the investigation focused on determining whether sensitive information such as usernames and passwords could be recovered from captured packets.

---

## Investigation Details

**Protocol:** FTP

**Port:** 21

**Client IP:** 192.168.1.4

**Server IP:** 192.168.1.5

**Tool Used:** Wireshark

---

## Objective

Determine whether FTP credentials and commands are transmitted in plaintext.

---

## Methodology

### Step 1

Started packet capture using Wireshark.

---

### Step 2

Generated FTP traffic by connecting to the Ubuntu FTP server.

---

### Step 3

Applied the filter:

```
ftp
```

---

### Step 4

Reviewed authentication packets.

Observed:

- USER command
- PASS command

---

### Step 5

Opened:

```
Follow → TCP Stream
```

Entire FTP conversation became visible.

---

## Evidence

### Evidence 1 – USER Command

Observed:

```
USER pranav-r-pillai
```

Finding:

Username transmitted in plaintext.

---

### Evidence 2 – PASS Command

Observed:

```
PASS ********
```

(Password intentionally masked for documentation.)

Finding:

Password transmitted without encryption and visible in packet capture.

---

### Evidence 3 – Server Response

Observed:

```
230 Login successful
```

Meaning:

Authentication completed successfully.

---

### Evidence 4 – FTP Banner

Observed:

```
220 (vsFTPd 3.0.5)
```

Meaning:

Server software identified as vsFTPd version 3.0.5.

---

### Evidence 5 – FTP Commands

Observed commands included:

- USER
- PASS
- SYST
- FEAT
- PWD
- LIST
- MKD
- EPSV

These reveal client activity after authentication.

---

### Evidence 6 – TCP Stream

The TCP Stream displayed the complete FTP session, including:

- Username
- Password
- Server responses
- Directory listing
- FTP commands

This confirms that FTP communications are fully readable by anyone capturing network traffic.

---

## Findings

| Observation | Status |
|------------|--------|
| FTP detected | Yes |
| Username exposed | Yes |
| Password exposed | Yes |
| Login successful | Yes |
| Commands visible | Yes |
| Encryption used | No |

---

## Security Impact

High

Any attacker with access to the same network can capture:

- Credentials
- Directory listings
- File operations
- Server information

Compromise of FTP credentials may allow unauthorized access to sensitive files.

---

## SOC Analyst Assessment

The traffic is legitimate but insecure.

No malicious activity was detected during this capture; however, the protocol itself introduces a significant security risk due to the transmission of credentials in cleartext.

---

## Recommendations

1. Replace FTP with SFTP or FTPS.
2. Disable FTP wherever possible.
3. Enforce encrypted file transfer protocols.
4. Monitor FTP authentication attempts.
5. Alert on FTP traffic in enterprise environments.
6. Restrict FTP access using firewall policies.
7. Rotate exposed credentials immediately if FTP has been used on untrusted networks.

---

## Conclusion

The investigation confirmed that FTP transmits usernames, passwords, and commands in plaintext. The captured packets clearly demonstrated credential exposure, highlighting why FTP is considered insecure for modern enterprise environments. Organizations should migrate to encrypted alternatives and continuously monitor legacy protocols to reduce credential theft risks.
