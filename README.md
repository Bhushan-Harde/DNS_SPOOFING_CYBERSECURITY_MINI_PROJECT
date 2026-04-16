# 🔐 DNS Spoofing Attack Simulation (Cybersecurity Mini Project)

## 📌 Overview
This project demonstrates a **DNS Spoofing (DNS Cache Poisoning) attack simulation** in a controlled lab environment. The objective is to understand how attackers manipulate DNS responses to redirect users to fake websites.

⚠️ **Disclaimer:**  
This project is strictly for **educational purposes only** and conducted in a controlled environment.

---

## 🎯 Objectives
- Understand DNS working
- Perform MITM-based DNS Spoofing
- Redirect traffic to attacker-controlled server
- Analyze packets using Wireshark
- Study detection & prevention techniques

---

## 🛠️ Technologies & Tools Used
- Kali Linux  
- Apache Server  
- Wireshark  
- Nmap  
- Ettercap / Bettercap  
- VirtualBox  

---

## 🧠 Concept

### Normal Flow:
User → DNS Server → Correct IP → Website  

### Attack Flow:
User → Attacker (MITM) → Fake IP → Fake Website  

---

## ⚙️ Methodology

1. Network setup (Attacker + Victim same network)  
2. Scan network using Nmap  
3. Perform ARP Spoofing (MITM)  
4. Intercept DNS requests  
5. Redirect to attacker IP  
6. Serve fake website using Apache  

---

## 🎥 Working Demonstration Video

👉 [Watch Demo Video](https://drive.google.com/drive/folders/1bxDAzDGI6dsfytgG4D1M2bFUS1bxHG5m?usp=sharing)

---

## 📊 Project Presentation

👉 [Download Presentation](Cybersecurity_Mini_Project.pptx)

---

## 📂 Project Structure
DNS-SPOOFING-CYBERSECURITY-MINI-PROJECT/

│── README.md
│── demo/
│── Cybersecurity_Mini_Project.pptx


---

## 🔍 Detection Techniques
- Monitor DNS traffic  
- Use Wireshark for anomaly detection  
- Detect mismatched IP responses  
- IDS alerts  

---

## 🛡️ Prevention
- Use HTTPS  
- Enable DNSSEC  
- Avoid public WiFi  
- Use secure DNS  

---

## ⚠️ Limitations
- Works only in LAN  
- Requires MITM setup  
- HTTPS reduces effectiveness  

---

## 📘 Learning Outcomes
- Practical DNS knowledge  
- Hands-on cybersecurity tools  
- Understanding network attacks  
- Ethical hacking awareness  

---

## 👨‍💻 Author
**Bhushan Harde**
**Sahil Makhija**
**Soumya Gangrade**
**Tavishi Khandelwal**
B.Tech Computer Engineering  

---

## ⭐ Support
If you found this useful, give it a ⭐ on GitHub!
