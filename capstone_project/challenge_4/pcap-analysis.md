# Challenge 4: PCAP Analysis and Clear-Text Data Exposure

## Objective
The objective of this challenge is to analyze a captured network traffic file (**PCAP**) to identify sensitive information transmitted in clear text, enumerate exposed resources, and retrieve the Challenge 4 flag.

---

## Artifact Analyzed
- File: `SA.pcap`
- Tool Used: Wireshark
- Vulnerability Type: Clear-Text Data Transmission

---

## Step 1: PCAP Analysis

### Traffic Inspection
The provided PCAP file was opened and analyzed using **Wireshark**. HTTP traffic was filtered and inspected to identify exposed paths and sensitive information.

### Key Observations
- The target system was identified by examining HTTP requests and responses.
- Multiple directory paths were revealed within clear-text HTTP packets.

#### Target IP Address
- **10.5.5.11**

#### Exposed Directories
- `http://10.5.5.11/data`
- `http://10.5.5.11/database-offline.php`
- `http://10.5.5.11/test`

The presence of these paths in network traffic indicates information disclosure due to unencrypted communication.

---

## Step 2: Flag Discovery

1. Accessed the discovered URLs using a web browser.
2. Navigated to the following file:
http://10.5.5.11/data/user_accounts.xml
3. Opened the file and reviewed its contents.

### File Contents
- Usernames
- Passwords
- Digital signatures

### Challenge 4 Flag
- **21z-1478K**

Successful retrieval of the flag confirms exposure of sensitive data through clear-text transmission.

---

## Key Findings
- Sensitive application data was transmitted over HTTP in clear text.
- Network traffic revealed internal directory structures and file paths.
- Confidential user information was accessible without authentication.
- Lack of encryption enabled passive network reconnaissance.

---

## Remediation Recommendations

### 1. Encrypt Data in Transit
Implement secure communication protocols such as HTTPS (TLS), SFTP, FTPS, or encrypted SMB. Encryption prevents attackers from reading or modifying intercepted traffic.

### 2. Disable Insecure Protocols
Disable or replace protocols that transmit data in clear text, including HTTP, FTP, Telnet, and legacy SMB versions. Enforcing encrypted alternatives significantly reduces the risk of data exposure.

---

## Ethical Disclaimer
This challenge was completed **only in a controlled lab environment** for educational purposes. Intercepting or analyzing network traffic without authorization is illegal and unethical.


