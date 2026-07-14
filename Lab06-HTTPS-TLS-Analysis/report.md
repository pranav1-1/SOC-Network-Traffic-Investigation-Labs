# Investigation Report – Lab 10: TLS/HTTPS Handshake Analysis

## Lab Information

| Field | Value |
|-------|-------|
| Lab Number | Lab 10 |
| Lab Title | TLS/HTTPS Handshake Analysis |
| Analyst | Pranav R Pillai |
| Tool Used | Wireshark |
| Protocol | TLS 1.2 / TLS 1.3 |
| Transport Protocol | TCP Port 443 |
| Status | Completed |

---

# Objective

The objective of this investigation is to analyze the TLS (Transport Layer Security) handshake process using Wireshark and understand how secure HTTPS communication is established between a client and a web server.

This lab demonstrates how encryption protects sensitive information during network communication and what evidence a SOC Analyst can extract from encrypted traffic.

---

# Investigation Scenario

A company employee reported slow access while browsing secure websites.

The SOC team needs to verify whether:

- A proper TLS handshake is completed.
- The client connects to a legitimate HTTPS server.
- The server presents a valid certificate.
- Secure encryption is negotiated successfully.
- No suspicious or downgraded encryption is used.

Wireshark was used to capture and inspect the TLS packets.

---

# Network Information

| Item | Value |
|------|------|
| Client Device | Kali Linux VM |
| Client IP | 192.168.1.4 |
| Protocol | TLS over TCP |
| Destination Port | 443 (HTTPS) |

---

# Investigation Steps

## Step 1 – Start Packet Capture

Started Wireshark on Kali Linux.

Applied the filter:

```
tls
```

---

## Step 2 – Generate HTTPS Traffic

Opened Firefox.

Visited an HTTPS website.

The TLS handshake packets were successfully captured.

---

## Step 3 – Analyze Client Hello

Observed the **Client Hello** packet.

### Findings

- Client initiated TLS session.
- Supported TLS versions advertised.
- Multiple Cipher Suites offered.
- Server Name Indication (SNI) present.
- Random value generated.

Evidence:

- TLS Version
- Cipher Suites
- Extensions
- SNI

Screenshot:

```
screenshots/client_hello.png
```

---

## Step 4 – Analyze Server Hello

Observed the **Server Hello** response.

### Findings

The server selected:

- TLS Version
- Cipher Suite
- Session ID
- Encryption parameters

This confirms successful negotiation.

Screenshot:

```
screenshots/server_hello.png
```

---

## Step 5 – Analyze Certificate

Observed the Certificate message.

The server transmitted its X.509 certificate chain.

Verified:

- Certificate Subject
- Issuer
- Signature Algorithm
- Public Key Information
- Validity Fields

Screenshot:

```
screenshots/certificate.png
```

---

## Step 6 – Encryption Begins

After certificate exchange:

- Key exchange completed.
- Change Cipher Spec observed.
- Encrypted Application Data started.

This confirms successful TLS session establishment.

---

# Wireshark Filters Used

```
tls
```

```
tls.handshake.type==1
```

```
tls.handshake.type==2
```

```
tls.handshake.certificate
```

```
tcp.port==443
```

---

# Evidence Collected

| Evidence | Status |
|-----------|--------|
| Client Hello | Observed |
| Server Hello | Observed |
| TLS Version | Verified |
| Cipher Suite | Verified |
| Certificate | Verified |
| Change Cipher Spec | Observed |
| Encrypted Application Data | Observed |

---

# SOC Analyst Observations

The packet capture shows a normal TLS handshake.

The client initiated a secure connection using **Client Hello**, and the server responded with **Server Hello**. The server transmitted its digital certificate, allowing the client to verify its identity. After successful negotiation, encrypted application data was exchanged.

No plaintext HTTP content was visible after the handshake, confirming that communication was encrypted.

---

# Security Importance

A SOC Analyst examines TLS traffic to:

- Verify encrypted communications.
- Detect weak TLS versions.
- Identify deprecated cipher suites.
- Validate server certificates.
- Detect certificate anomalies.
- Investigate HTTPS-based malware communication.
- Confirm secure client-server connections.

---

# Conclusion

The investigation confirms that a secure TLS handshake was successfully completed between the client and the server.

The client and server negotiated encryption parameters, exchanged a valid certificate, and established an encrypted communication channel. The observed traffic is consistent with legitimate HTTPS activity, with no evidence of protocol downgrade or insecure configuration.

**Result:** Secure TLS session successfully established.
