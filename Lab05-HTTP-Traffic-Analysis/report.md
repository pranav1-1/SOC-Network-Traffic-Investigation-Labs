# HTTP Traffic Analysis Report

## Lab Number

Lab 05 – HTTP Traffic Analysis

---

# Objective

To capture and analyze HTTP traffic using Wireshark and understand the communication between a web browser and a web server.

---

# Lab Setup

| Component | Details |
|-----------|----------|
| Operating System | Kali Linux |
| Tool | Wireshark |
| Browser | Firefox |
| Network Adapter | eth0 |

---

# Steps Performed

### Step 1

Started packet capture in Wireshark.

---

### Step 2

Opened Firefox browser.

---

### Step 3

Visited the website:

```
http://neverssl.com
```

---

### Step 4

Stopped packet capture.

---

### Step 5

Applied the filter:

```
http
```

---

### Step 6

Analyzed the following:

- HTTP GET Request
- HTTP Response
- Status Code
- Request URI
- Host Header
- User-Agent
- Server Header
- Content-Type

---

# Sample Observations

## HTTP Request

Method:

```
GET
```

Host:

```
neverssl.com
```

User-Agent:

```
Mozilla Firefox
```

---

## HTTP Response

Status Code:

```
200 OK
```

Server:

```
Apache
```

Content-Type:

```
text/html
```

---

# Wireshark Filters

Display all HTTP traffic

```
http
```

HTTP Requests

```
http.request
```

HTTP Responses

```
http.response
```

GET Requests

```
http.request.method == "GET"
```

Successful Responses

```
http.response.code == 200
```

---

# Findings

- Browser initiated an HTTP GET request.
- Server responded with HTTP 200 OK.
- HTTP headers were transmitted in plaintext.
- Request and response information was clearly visible.
- User-Agent identified the browser.
- Host header identified the destination server.

---

# Conclusion

This lab demonstrated how HTTP communication occurs between a client and a web server. Using Wireshark, HTTP requests, responses, headers, and status codes were successfully analyzed. The lab highlights why HTTP is considered insecure since all communication is transmitted without encryption.

---

# Skills Gained

- HTTP Packet Analysis
- Wireshark Filtering
- Request/Response Analysis
- Header Inspection
- Web Traffic Investigation
- SOC Network Traffic Analysis
