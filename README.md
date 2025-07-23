# 📦 Scapy Packet Crafting Lab — Custom Network Attack Simulation  
> “Why download tools when you can build the packet yourself?” — `@mSameerMalik`  
This lab demonstrates how raw packet crafting can simulate attacks, scan networks, and understand protocol structures. Using Python's Scapy library, custom TCP, UDP, ICMP, and spoofed packets were crafted and analyzed in a controlled virtual environment.

## 🎯 Objectives  
- Learn the fundamentals of packet crafting with Scapy  
- Build and send custom ICMP, TCP SYN, and UDP packets  
- Simulate spoofed traffic for red-team tactics  
- Analyze packet responses and identify host behavior  

## 🧰 Tools Used  
- 🐍 Python 3.x  
- 🧪 [Scapy](https://scapy.net/)  
- 🖥️ Kali Linux (attacker machine)  
- 📡 Wireshark (for packet capture and inspection)

## 📌 Execution Workflow  
1. ⚙️ **Environment Setup**  
   - Installed Scapy using `pip install scapy`  
   - Enabled IP forwarding on Linux  
2. 📤 **Crafted Packets:**  
   - ICMP Echo (Ping)  
     ```python
     send(IP(dst="192.168.1.1")/ICMP())
     ```  
   - TCP SYN to port 80  
     ```python
     send(IP(dst="192.168.1.1")/TCP(dport=80, flags="S"))
     ```  
   - UDP Flood Example  
     ```python
     send(IP(dst="192.168.1.1")/UDP(dport=53)/Raw(load="A"*1000), loop=1)
     ```  
   - Spoofed IP Packet  
     ```python
     send(IP(src="10.0.0.5", dst="192.168.1.1")/ICMP())
     ```
3. 🧠 **Packet Analysis**  
   - Used Wireshark to verify structure and impact  
   - Observed TTL, flags, checksums, and headers  
   - Simulated black-box reconnaissance using stealthy SYN

## 📂 Lab Files  
- `Scapy Packet Crafting Lab.docx` – Detailed write-up  
- `/screenshots/` – Packet structures, Wireshark capture proofs  
- Sample `.py` scripts for ICMP, TCP, UDP, and spoofing tasks

## ⚠️ Legal & Ethical Note  
All activity was performed inside an isolated lab environment with no external traffic or unauthorized access. This lab is for educational purposes only.

## 👨‍💻 Author  
**Sameer Malik** – Cybersecurity student exploring packet-level red teaming  
GitHub: [mSameerMalik](https://github.com/mSameerMalik)  
LinkedIn: [linkedin.com/in/sameer-malik-18b52634b](https://www.linkedin.com/in/sameer-malik-18b52634b/)

## 🏷️ Tags  
#PacketCrafting #Scapy #RedTeam #PythonSecurity #NetworkSecurity #Spoofing #Infosec #Wireshark #CyberLabs #mSameerMalik
