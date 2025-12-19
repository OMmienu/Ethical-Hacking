# Website Cloning Lab (SEToolkit)

## Objective
To understand how attackers clone legitimate websites to harvest credentials and how such attacks can be prevented.

## Method
SEToolkit was used to clone a DVWA login page. Victims were redirected to the attacker’s IP where credentials were captured.

## HTML Redirect Payload
```html
<html>
<head>
<meta http-equiv="refresh" content="0; url=http://10.6.6.1/" />
</head>
</html>

Save as ladies.html on Desktop
Double click saved html file from desktop
Login with ladies@gmail.com, password: 1234
Return to your old terminal
Crtl + c
Type 99
Type 99
Type 99
Type 99
cat /root/.set/reports/”2025-12-14 13:34:09.326665.xml”
