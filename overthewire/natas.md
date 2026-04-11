# Natas
## Introduction 
The OverTheWire Natas wargame focuses on introducing the fundamentals of server-side web security. It is designed to help learners understand common web vulnerabilities and how they can be exploited through practical, hands-on challenges.

## Structure and Access
Each level in Natas is presented as a standalone web application, accessible via a unique URL following the format:
http://natasX.natas.labs.overthewire.org, where X represents the level number.
Unlike other wargames, Natas does not require SSH access. Instead, users log in through the web interface using the designated username (e.g., natas0 for Level 0) along with the corresponding password.

## Objective
The main objective of each level is to retrieve the password for the next level. This typically involves analyzing the web application, identifying vulnerabilities, and exploiting them to gain access to restricted information.
- Passwords for each level are stored on the server in the directory: `/etc/natas_webpass/`
- For example, the password for natas5 is stored in: `/etc/natas_webpass/natas5`, and can only be accessed by specific permission levels (e.g., natas4 and natas5). This reinforces the concept of access control and privilege separation.

## Getting Started
To begin the challenge:
- Username: natas0
- Password: natas0
- URL: http://natas0.natas.labs.overthewire.org

Learners are encouraged to explore each level carefully, inspect web elements, and apply logical thinking to uncover hidden information. Each challenge builds upon previous knowledge, gradually strengthening understanding of web security concepts.

---

## Natas 0
URL: http://natas0.natas.labs.overthewire.org
Username: natas0
Password: natas0

### Approach
After logging into the web application, the page does not visibly display any useful information.  
To investigate further, the page source code was examined using:
- Right-click → **View Page Source**, or  
- Browser Developer Tools (**Inspect**)

```html
<html>
<head>
<!-- This stuff in the header has nothing to do with the level -->
<link rel="stylesheet" type="text/css" href="http://natas.labs.overthewire.org/css/level.css">
<link rel="stylesheet" href="http://natas.labs.overthewire.org/css/jquery-ui.css" />
<link rel="stylesheet" href="http://natas.labs.overthewire.org/css/wechall.css" />
<script src="http://natas.labs.overthewire.org/js/jquery-1.9.1.js"></script>
<script src="http://natas.labs.overthewire.org/js/jquery-ui.js"></script>
<script src=http://natas.labs.overthewire.org/js/wechall-data.js></script><script src="http://natas.labs.overthewire.org/js/wechall.js"></script>
<script>var wechallinfo = { "level": "natas0", "pass": "natas0" };</script></head>
<body>
<h1>natas0</h1>
<div id="content">
You can find the password for the next level on this page.

<!--The password for natas1 is 0nzCigAq7t2iALyvU9xcHlYN4MlkIwlq -->
</div>
</body>
</html>
```

### Finding 
In the `<div></div>` content, the password is discovered, which is `<!--The password for natas1 is 0nzCigAq7t2iALyvU9xcHlYN4MlkIwlq -->`

### Analysis
This level demonstrates a basic information disclosure vulnerability, where sensitive data is exposed within the client-side source code.
Although comments are not rendered in the browser, they are still accessible to users who inspect the page. Storing credentials in HTML comments is considered a poor security practice, as it allows attackers to easily retrieve hidden information.

Thus, it is important to note that HTML comments are not secure and should not be used to hide critical data. Always inspect page source when analyzing web applications and never store sensitive information (e.g., passwords) in client-side code.


---

## Natas 1
