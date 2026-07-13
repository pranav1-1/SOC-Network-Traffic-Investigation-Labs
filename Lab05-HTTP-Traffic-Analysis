# Lab 5 – HTTP Traffic Analysis

## Objective

The objective of this lab is to analyze HTTP traffic using Wireshark and understand how web communication works. The lab focuses on identifying HTTP requests, responses, methods, status codes, headers, and transferred objects.

---

## Lab Environment

| Device | IP Address |
|---------|------------|
| Kali Linux | 192.168.1.5 |
| Router/Gateway | 192.168.1.1 |

---

## Tools Used

- Kali Linux
- Wireshark
- Firefox Web Browser

---

## Procedure

1. Start Wireshark capture.
2. Open Firefox.
3. Visit an HTTP website (http://neverssl.com).
4. Stop packet capture.
5. Apply the filter:

```
http
```

6. Analyze:
   - HTTP GET Request
   - HTTP Response
   - Status Code
   - HTTP Headers
   - Host Header
   - User-Agent

---

## Wireshark Filters Used

```
http
```

```
http.request
```

```
http.response
```

```
http.request.method == "GET"
```

```
http.response.code == 200
```

---

## Files Included

```
Lab05-HTTP-Analysis/
│
├── README.md
├── report.md
├── http_lab.pcapng
└── screenshots/
```

---

## Learning Outcome

- Learned HTTP request and response flow.
- Identified HTTP GET requests.
- Examined response status codes.
- Analyzed HTTP headers.
- Understood why HTTP traffic is visible in plaintext.
- Improved packet analysis skills using Wireshark.

---

## Author

**Pranav R Pillai**

SOC Analyst Home Lab Series
