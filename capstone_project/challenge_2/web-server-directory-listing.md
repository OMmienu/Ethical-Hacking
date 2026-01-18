# Challenge 2: Web Server Vulnerabilities (Directory Listing)

## Objective
The objective of this challenge is to identify **web server misconfigurations** that allow directory listing, enumerate exposed directories, and locate a flag file stored within a publicly accessible directory.

---

## Target Information
- Web Application Server IP: `10.5.5.12`
- Application: DVWA
- Vulnerability Type: Directory Listing / Web Server Misconfiguration

---

## Step 1: Environment Setup

1. Log into the web application at:
http://10.5.5.12

2. Authenticate using the default credentials:
- **Username:** admin  
- **Password:** password
3. Navigate to **DVWA Security**.
4. Set the security level to **Low** and apply the changes.

---

## Step 2: Reconnaissance and Directory Enumeration

### Web Server Scanning
Reconnaissance was performed to identify exposed directories and misconfigurations using **Nikto**:

```bash
nikto -h 10.5.5.12

The scan revealed directories with directory indexing enabled, allowing file and subdirectory enumeration through a web browser.

Identifying Viewable Directories

Discovered directories were accessed directly via browser URL manipulation.

Directory contents were visible due to missing index files and improper configuration.

Files and subdirectories were manually reviewed for sensitive content.

Step 3: Flag Discovery

Accessed exposed directories using the browser.

Located the file:
db_form.html

Navigated through multiple viewable subdirectories.

Identified the file containing the Challenge 2 flag code.

Flag Details

Subdirectories containing the file: (documented during exploitation)

Flag filename: (documented during exploitation)

Flag contents: (documented during exploitation)

Successful retrieval of the flag confirms exploitation of the directory listing vulnerability.

Key Findings

Directory indexing was enabled on sensitive paths.

Web server misconfiguration exposed internal application files.

Lack of access control allowed unauthenticated users to browse directories.

Sensitive files were accessible through simple URL manipulation.

Remediation Recommendations
1. Disable Directory Listing

Configure the web server to disable directory indexing. This prevents attackers from viewing directory contents when an index file is not present, reducing exposure of sensitive files, backups, and application logic.

2. Enforce Proper Access Controls

Apply strict file permissions and access controls at both the operating system and web server levels. Only authorized users should be able to access sensitive directories and files, even if directory browsing is accidentally enabled.
