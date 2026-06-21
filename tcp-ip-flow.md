# TCP/IP Data Flow Explained

## 1. What is TCP/IP?
TCP/IP is the core communication protocol of the internet. It defines how data is packaged, sent, and received across networks.

---

## 2. How data moves (step-by-step)

When you send data (e.g., open a website):

### Step 1: Application Layer
Your browser creates a request (HTTP/HTTPS).

### Step 2: Transport Layer
TCP breaks the data into segments and ensures delivery.

### Step 3: Internet Layer
IP adds source and destination addresses.

### Step 4: Network Access Layer
Data is converted into frames and sent physically.

---

## 3. TCP 3-Way Handshake

1. SYN → Client requests connection  
2. SYN-ACK → Server responds  
3. ACK → Connection established  

---

## 4. Simple Example

When you open google.com:
- Your device sends a request
- DNS resolves the IP
- TCP connection is created
- Data is transferred

---

## 5. Why it matters in cybersecurity

Attackers often target:
- TCP handshake manipulation
- packet interception
- session hijacking

Understanding TCP/IP is essential for penetration testing.
