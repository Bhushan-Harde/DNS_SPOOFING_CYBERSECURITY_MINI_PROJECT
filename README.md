# 📄 DNS Spoofing Simulation Project

## 🧠 Overview

This project demonstrates a **controlled simulation of DNS Spoofing** using local DNS resolution and web server redirection.
Instead of performing real network-level attacks, this implementation safely replicates the **effect of DNS spoofing** in a virtual environment.

---

## 🎯 Objective

* To understand how DNS spoofing works
* To simulate redirection to a fake website
* To detect the attack using network analysis and scripting
* To demonstrate basic prevention mechanisms

---

## ⚙️ Technologies & Tools Used

| Tool                      | Purpose                        |
| ------------------------- | ------------------------------ |
| Kali Linux                | Environment for implementation |
| Apache2                   | Web server to host websites    |
| VirtualBox                | Virtual environment            |
| Hosts File (`/etc/hosts`) | Local DNS resolution           |
| Python (requests)         | Detection script               |
| Wireshark                 | Network traffic analysis       |

---

## 🧩 Project Structure

```
/var/www/
 ├── original/   → Legitimate website
 ├── fake/       → Fake (malicious) website
```

---

## 🔐 Working Principle

### 🟢 Normal Scenario

```
abc.local → (hosts file) → Kali IP → Apache → Original Website
```

### 🔴 Attack Scenario

```
abc.local → Kali IP → Apache → HTTP 302 Redirect → fake.local → Fake Website
```

---

## ⚡ Implementation Steps

### 1. Website Setup

* Created two websites:

  * Original website
  * Fake website

---

### 2. Apache Virtual Host Configuration

Configured Apache to serve multiple websites:

```apache
<VirtualHost *:80>
    ServerName abc.local
    DocumentRoot /var/www/original
</VirtualHost>

<VirtualHost *:80>
    ServerName fake.local
    DocumentRoot /var/www/fake
</VirtualHost>
```

---

### 3. Local DNS Mapping (Hosts File)

Edited `/etc/hosts`:

```text
192.168.x.x abc.local
192.168.x.x fake.local
```

---

### 4. Attack Simulation (Redirection)

Modified Apache configuration:

```apache
<VirtualHost *:80>
    ServerName abc.local
    Redirect 302 / http://fake.local/
</VirtualHost>
```

---

## 🔍 Detection

### 1. Wireshark Analysis

* Captured HTTP traffic on loopback (`lo`)
* Observed:

```
HTTP/1.1 302 Found
Location: http://fake.local
```

---

### 2. Python Detection Script

```python
import requests

url = "http://abc.local"

response = requests.get(url, allow_redirects=False)

if response.status_code in [301, 302]:
    print("⚠️ REDIRECTION DETECTED!")
    print("Redirecting to:", response.headers.get("Location"))
else:
    print("✅ Safe")
```

---

## 🛡️ Prevention (Simulation)

* Detects redirection using HTTP status codes
* Alerts user about suspicious behavior
* Blocks further processing (simulation)

---

## ⚠️ Important Notes

* This is a **simulation**, not a real DNS spoofing attack
* Real DNS spoofing occurs at the **network layer**
* This project demonstrates behavior using:

  * Local DNS override
  * Server-side redirection

---

## 🧠 Key Learning Outcomes

* Understanding DNS resolution process
* Difference between DNS spoofing and HTTP redirection
* Practical experience with Apache and networking tools
* Basic intrusion detection concepts

---

## 🔍 Limitations

* Does not perform real ARP/DNS poisoning
* Works only in controlled environment
* Depends on hosts file mapping

---

## 🚀 Conclusion

This project successfully demonstrates the **concept and impact of DNS spoofing** using a safe and controlled approach.
It also includes detection and prevention techniques, making it a complete cybersecurity mini-project.

---

## Authors :

1. Bhushan Harde
2. Sahil Makhija
3. Soumya Gangrade
4. tavishi Khandelwal
