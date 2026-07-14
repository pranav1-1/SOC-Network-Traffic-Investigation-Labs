# Investigation Report

## Lab Title

DHCP Traffic Analysis Using Wireshark

---

## Investigation Summary

A packet capture containing DHCP traffic was analyzed to examine how a client obtained an IP address from a DHCP server. The investigation focused on the DHCP DORA process and the exchange of DHCP messages between the client and server.

---

## Network Information

| Item | Value |
|------|-------|
| Protocol | DHCP |
| Transport Protocol | UDP |
| Client Port | 68 |
| Server Port | 67 |

---

## Evidence Collected

### 1. DHCP Discover

The client broadcasted a DHCP Discover packet requesting an available IP address from the DHCP server.

---

### 2. DHCP Offer

The DHCP server responded with an available IP address and network configuration.

---

### 3. DHCP Request

The client requested the offered IP address to confirm acceptance.

---

### 4. DHCP ACK

The DHCP server acknowledged the request and officially assigned the IP address to the client.

---

## Security Analysis

### Normal Behavior

✔ DHCP Discover observed

✔ DHCP Offer received

✔ DHCP Request completed

✔ DHCP ACK successfully received

✔ Client obtained a valid IP address

---

### Potential Threats

- Rogue DHCP Server
- DHCP Starvation Attack
- Unauthorized Device Joining the Network
- IP Address Exhaustion
- DHCP Spoofing

---

## SOC Analyst Observations

The DHCP transaction completed successfully using the standard DORA process.

No abnormal DHCP behavior or rogue DHCP responses were identified during the packet capture.

---

## Conclusion

The packet capture confirms successful automatic IP address assignment through the DHCP DORA process. DHCP traffic analysis is an essential SOC skill for identifying network configuration issues and detecting DHCP-related attacks.
