
## Objective
The objective of this challenge is to exploit a **SQL injection vulnerability** to enumerate user credentials, crack a password hash, and use the compromised credentials to access a remote system and retrieve a flag file.

---

## Target Information
- Web Application: DVWA
- Web Server IP: `10.5.5.12`
- Remote Host: `192.168.0.10`
- Target User: Bob Smith


## Step 1: Environment Setup

1. Open a web browser and navigate to:
http://10.5.5.12

2. Log in using the default DVWA credentials:
- **Username:** admin
- **Password:** password
3. Navigate to **DVWA Security**.
4. Set the security level to **Low** and submit the changes.

---

## Step 2: SQL Injection to Retrieve User Credentials

### Identify Vulnerable Input
- Locate a form vulnerable to SQL injection (e.g., user ID or login field).
- Confirm input is unsanitized by testing basic injection payloads.

---

### Enumerate Database Columns
The following payload was used to identify column names in the `users` table:

```sql
1' OR 1=1 UNION SELECT 1, column_name 
FROM information_schema.columns 
WHERE table_name='users'#

This revealed columns containing usernames and password hashes.

Extract Credentials

To retrieve user credentials, the following payload was used:

1' OR 1=1 UNION SELECT user, password FROM users#


This returned multiple user accounts, including Bob Smith, along with the associated password hash.

Password Cracking

The extracted password hash was submitted to CrackStation.

The plaintext password for Bob Smith’s account was successfully recovered.

Tool used: https://crackstation.net

Remote Access Using Compromised Credentials

Establish an SSH connection to the target host:

ssh bob@192.168.0.10


Authenticate using the cracked password.

Navigate to the user’s home directory.

Locate and open the flag file.
