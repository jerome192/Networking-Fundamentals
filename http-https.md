# HTTP and HTTPS Communication

## Introduction

HTTP (Hypertext Transfer Protocol) and HTTPS (Hypertext Transfer Protocol Secure) are application-layer protocols used for communication between clients and web servers.

They define how web browsers request resources and how servers respond.

Almost every website uses one of these protocols.

In penetration testing, understanding HTTP and HTTPS is essential because most web attacks happen at this layer.

---

## What is HTTP?

HTTP is a protocol used to transfer web content.

It operates at:

```text
Application Layer
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

Each request is independent.

---

## What is HTTPS?

HTTPS is HTTP secured with encryption.

Default port:

```text
443
```

HTTPS uses:

```text
TLS (Transport Layer Security)
```

This protects:

- data confidentiality
- data integrity
- authentication

This prevents attackers from easily reading traffic.

---

## HTTP Request Structure

A request contains:

- Method
- Path
- Headers
- Body (optional)

Example:

```text
GET /index.html HTTP/1.1
Host: example.com
User-Agent: Browser
```

This tells the server what resource is requested.

---

## Common HTTP Methods

| Method | Purpose |
|---|---|
| GET | Retrieve data |
| POST | Send data |
| PUT | Update data |
| DELETE | Remove data |

These methods define client actions.

Understanding them is important in web testing.

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

This tells the client the result.

---

## Common Status Codes

| Code | Meaning |
|---|---|
| 200 | Success |
| 301 | Redirect |
| 403 | Forbidden |
| 404 | Not Found |
| 500 | Server Error |

These help identify server behavior.

Important in enumeration.

---

## HTTP vs HTTPS

| Feature | HTTP | HTTPS |
|---|---|---|
| Encryption | No | Yes |
| Port | 80 | 443 |
| Security | Low | High |
| TLS | No | Yes |

HTTPS is the modern standard.

---

## Cookies and Sessions

Web applications use cookies to maintain sessions.

Example:

```text
Set-Cookie: sessionid=abc123
```

This allows authentication to persist across requests.

This is important for:

- login systems
- session management
- web testing

---

## Security Relevance

HTTP/HTTPS is central in penetration testing.

Examples:

- SQL Injection
- XSS
- CSRF
- Authentication bypass
- Session hijacking
- Directory enumeration

Tools used:

- Burp Suite
- cURL
- Gobuster

Most web attacks happen here.

---

## Key Takeaways

- HTTP is the core web communication protocol.
- HTTPS secures HTTP using TLS.
- Requests and responses form web communication.
- Methods define client actions.
- Status codes reveal server behavior.
- Cookies maintain sessions.

---

## Conclusion

HTTP and HTTPS form the foundation of web communication.

For penetration testers, understanding them is critical because they reveal how applications behave, how users interact with systems, and where vulnerabilities can be found.
