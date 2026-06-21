# DNS Resolution Explained

## 1. What is DNS?
DNS (Domain Name System) translates domain names into IP addresses.

---

## 2. How DNS works

When you type:
google.com

### Step 1: Browser checks cache
### Step 2: OS checks local cache
### Step 3: Request goes to DNS resolver
### Step 4: Root server responds
### Step 5: TLD server responds (.com)
### Step 6: Authoritative server returns IP

---

## 3. Result

google.com → 142.250.x.x

---

## 4. Why DNS matters in security

Attackers can:
- poison DNS
- redirect traffic
- hijack domains

---

## 5. Key takeaway

DNS is the “phonebook of the internet”.
