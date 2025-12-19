# 📁 beef-attacks/

## 📄 beef-attacks/fake-notification.md

```md
# BeEF Fake Notification Attack

## Objective
To demonstrate how attackers use fake browser notifications to trick users into installing malicious software.

## Steps
1. Start BeEF:
   sudo beef-xss
2. Login with username `beef`
3. Open:
   http://127.0.0.1:3000/demos/butcher/index.html
4. Victim browser gets hooked via hook.js

## Attack Execution
- Navigate to:
  Command → Social Engineering → Fake Notification Bar (Firefox)
- Plugin URL:
  http://10.6.6.13/
- Notification Text:
  Adblocker Security Extension is out of date. Install new version now

## Result
Victim is redirected to a malicious/DVWA site after clicking "Install Now".

## Lesson Learned
Browser-based social engineering attacks can bypass technical defenses if users are unaware.

