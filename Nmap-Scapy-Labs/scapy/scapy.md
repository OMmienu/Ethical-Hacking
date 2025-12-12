# ✅ **Scapy_Lab.md**

```md
# Scapy Penetration Testing Lab

This document contains the Scapy exercises demonstrated in class and reproduced manually.  
It focuses on packet sniffing, packet analysis, traffic generation, and filtering.


## 1. Start Scapy as Root

**Command**
```bash
sudo su
scapy


Sniff All Traffic
sniff()


Stop with:
CTRL + C

Trigger traffic from another terminal
ping google.com
This command creates ICMP packets Scapy will capture.

Sniff on a Specific Neywork Interface
sniff(iface="br-internal")

Generate traffic to capture
ping 10.6.6.1/24

Save results as 
paro2 = _
paro2.summary()

Sniff Only ICMP Packets (Filtered Capture)
Command
sniff(iface="br-internal", filter="icmp", count=5)

Generate ICMP packets:
ping 10.6.6.23

Save:
paro3 = _
paro3.summary()
paro3[3]    # view packet detail

Generate HTTP Traffic for Analysis

Open in a browser:
http://10.6.6.23


Stop sniffing with:
CTRL + C
