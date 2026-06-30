# HTTP and HTTPS Communication

## Introduction

HTTP (Hypertext Transfer Protocol) and HTTPS (Hypertext Transfer Protocol Secure) are application-layer protocols used for communication between clients and web servers.

They define how browsers request resources and how servers respond.

Almost every website on the internet depends on these protocols.

In penetration testing, understanding HTTP and HTTPS is essential because most web-based attacks happen at this layer.

---

## What is HTTP?

HTTP is a protocol used to transfer web content between a client and a server.

It operates at:

```text
Layer 7 (Application Layer)
```

Default port:

```text
80
```

HTTP follows a request-response model.

This means:

- client sends request
- server sends response

HTTP is stateless.

Each request is treated independently.

---

## What is HTTPS?

HTTPS is the secure version of HTTP.

Default port:

```text
443
```

HTTPS uses:

```text
TLS (Transport Layer Security)
```

This encrypts communication between the client and the server.

This protects:

- confidentiality
- integrity
- authentication

Without HTTPS:

data can be intercepted more easily.

---

## How HTTP Communication Works

Basic process:

1. User enters a URL
2. DNS resolves the domain name
3. TCP connection is established
4. Browser sends HTTP request
5. Server processes request
6. Server sends HTTP response
7. Browser renders content

This is how websites are loaded.

---

## Diagram: HTTP and HTTPS Communication

![HTTP and HTTPS Communication](images/http-https.png)

---

## HTTP Request Structure

An HTTP request contains:

- Method
- Path
- Headers
- Body (optional)

Example:

```text
GET /index.html HTTP/1.1
Host: example.com
User-Agent: Mozilla
```

This tells the server what resource is needed.

---

## Common HTTP Methods

| Method | Purpose |
|---|---|
| GET | Retrieve data |
| POST | Submit data |
| PUT | Update data |
| DELETE | Remove data |

These methods define client actions.

Understanding them is important for web testing.

---

## HTTP Response Structure

A server response contains:

- Status code
- Headers
- Body

Example:

```text
HTTP/1.1 200 OK
Content-Type: text/html
```

This tells the browser the result.

---

## Common Status Codes

| Code | Meaning |
|---|---|
| 200 | Success |
| 301 | Redirect |
| 403 | Forbidden |
| 404 | Not Found |
| 500 | Server Error |

Status codes reveal how servers respond.

This is useful during enumeration.

---

## HTTP vs HTTPS

| Feature | HTTP | HTTPS |
|---|---|---|
| Port | 80 | 443 |
| Encryption | No | Yes |
| Security | Low | High |
| TLS | No | Yes |

HTTPS is the modern standard.

---

## Cookies and Sessions

Web applications use cookies to maintain user sessions.

Example:

```text
Set-Cookie: sessionid=abc123
```

This allows:

- login persistence
- session tracking
- authentication state

These are common targets in web attacks.

---

## Security Relevance

HTTP and HTTPS are critical in penetration testing.

Examples:

- SQL Injection
- XSS
- CSRF
- Session hijacking
- Authentication bypass
- Directory enumeration

Tools used:

- Burp Suite
- cURL
- Gobuster

Most web application attacks happen at this layer.

---

## Key Takeaways

- HTTP enables communication between browsers and servers.
- HTTPS secures communication using TLS.
- Requests and responses form web interactions.
- Methods define client actions.
- Status codes reveal server behavior.
- Cookies maintain sessions.

---

## Conclusion

HTTP and HTTPS are the foundation of web communication.

For penetration testers, understanding them is essential because they expose how applications function and where vulnerabilities can exist.
