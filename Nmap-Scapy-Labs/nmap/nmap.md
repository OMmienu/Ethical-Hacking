# Nmap Penetration Testing Lab

This document contains all Nmap scans reproduced from the cybersecurity laboratory work.  
Each command includes a short explanation so the documentation is clean and professional for GitHub.


## 1. Host Discovery Scan

**Command**
```bash
nmap -sn 10.6.6.0/24

OS Fingerprinting

Command

sudo nmap -O 10.6.6.23


Purpose
Detects the operating system of the host.

Uses TCP/IP stack fingerprinting.
Service & Version Detection (FTP Example – Port 21)

Command
nmap -p21 -sV -A -T4 10.6.6.23


Purpose
Checks if FTP is running.
Extracts software version.

-A includes OS detection, scripts, and traceroute.
SMB Scan (Ports 139 and 445)

Command
nmap -A -p139,445 10.6.6.23


Purpose
Detects SMB services.

SMB Share Enumeration
Command
nmap --script smb-enum-shares.nse -p445 10.6.6.23


Purpose
Lists SMB shares accessible to the public.

Testing SMB Share Access
Command
smbclient //10.6.6.23/print$ -N

Exit:
exit

Purpose
Checks whether shares can be accessed anonymously


Capturing Traffic With tcpdump (Before Wireshark Analysis)
Command
sudo tcpdump -i eth0 -s 0 -w ladies.pcap


Stop capture with:
CTRL + C

Verify:
ls ladies.pcap

Open in Wireshark:
wireshark ladies.pcap

Basic Network Information Commands (for Documentation)
ifconfig
ip route
cat /etc/resolv.conf

