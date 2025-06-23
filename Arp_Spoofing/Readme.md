# ARP Spoofing Attack Demonstration
---

## 🚀 Overview

This project demonstrates a successful ARP Spoofing (Man-in-the-Middle) attack in a virtual lab. Using Kali Linux as the attacker and Windows as the victim, the attack intercepts and analyzes HTTP traffic, showcasing practical cybersecurity and network penetration testing skills.

---

## 🖥️ Lab Setup

| Component          | Details              |
|--------------------|---------------------|
| **Attacker**       | Kali Linux VM        |
| **Victim**         | Windows VM           |
| **Network**        | Same virtual network |
| **Gateway IP**     | 192.168.37.2         |
| **Kali IP**        | 192.168.37.130       |
| **Windows IP**     | 192.168.37.129       |

---

## 🛠️ Step-by-Step Execution

1. **Network Configuration Verification**
    - On Kali Linux:
      ```
      ifconfig
      ```
    - On Windows:
      ```
      ipconfig
      ```
    - *Verified both machines are on the same subnet.*

2. **Initial ARP Table Check (Windows)**
    - ```
      arp -a
      ```
    - *Confirmed normal gateway MAC mapping.*

3. **Enable IP Forwarding (Kali Linux)**
    - Check status:
      ```
      cat /proc/sys/net/ipv4/ip_forward
      ```
    - Enable if needed:
      ```
      echo 1 > /proc/sys/net/ipv4/ip_forward
      ```

4. **Launch Ettercap**
    - Open Ettercap on Kali Linux.
    - Use the Search button to list available hosts.

5. **Target Selection in Ettercap**
    - Set the gateway address as Target 1.
    - Set the Windows machine IP as Target 2.

6. **ARP Poisoning Attack**
    - Enable ARP Poisoning in Ettercap.
    - Start the attack.
    - *Victims are assigned to Group 1 and Group 2.*

7. **ARP Table Check (Windows)**
    - ```
      arp -a
      ```
    - *Verified the gateway MAC now matches Kali's MAC.*

8. **Packet Capture using Wireshark**
    - Start Wireshark on Kali Linux, listening on the "eth0" interface.

9. **HTTP Traffic Monitoring**
    - Open a browser on Windows and access an HTTP website.
    - *Observe HTTP data captured in Wireshark in real-time.*

---
## 📝 Results

- The ARP Spoofing attack was successful.
- The target machine's ARP table was manipulated to redirect traffic through Kali Linux.
- HTTP data from the target was intercepted and analyzed using Wireshark.

---

## 🛡️ Mitigation Tips

- Use static ARP entries on critical hosts.
- Prefer encrypted protocols (HTTPS, SSH).
- Segment networks and monitor ARP traffic.
- Deploy intrusion detection/prevention systems.

---

## 📥 Download

- [Download Full Assignment Report (PDF)](Sridhar_Arp_Spoofing.pdf)

---

**Disclaimer:**  
This project was conducted in a controlled lab environment for educational purposes only. Never attempt ARP spoofing on unauthorized networks.

---

