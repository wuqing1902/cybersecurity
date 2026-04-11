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
```
URL: http://natas0.natas.labs.overthewire.org
Username: natas0
Password: natas0
```
After login, the following note is displayed: 
```
You can find the password for the next level on this page.
```

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
```
URL: http://natas1.natas.labs.overthewire.org
Username: natas1
Password: 0nzCigAq7t2iALyvU9xcHlYN4MlkIwlq
```
After login, the following note is displayed: 
```
You can find the password for the next level on this page, but rightclicking has been blocked!
```

### Approach 
Upon accessing the webpage, it was observed that right-click functionality was disabled, preventing the use of standard options such as **“View Page Source”** or **“Inspect”**.
To bypass this restriction, alternative methods were used:
- Press **F12** to open Developer Tools  
- Press **CTRL + U** to directly view the page source  
These shortcuts are browser-level features and cannot be disabled by client-side scripts.

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
<script>var wechallinfo = { "level": "natas1", "pass": "0nzCigAq7t2iALyvU9xcHlYN4MlkIwlq" };</script></head>
<body oncontextmenu="javascript:alert('right clicking has been blocked!');return false;">
<h1>natas1</h1>
<div id="content">
You can find the password for the
next level on this page, but rightclicking has been blocked!

<!--The password for natas2 is TguMNxKo1DSa1tujBLuZJnDUlCcUAPlI -->
</div>
</body>
</html>
```

### Finding 
After viewing the page source, a similar pattern to the previous level was identified. The password for the next level was found embedded within an HTML comment inside the `<div>` element, which is `<!--The password for natas2 is TguMNxKo1DSa1tujBLuZJnDUlCcUAPlI -->`

### Analysis
This level demonstrates that client-side restrictions, such as disabling right-click, do not provide real security. Such controls can be easily bypassed using built-in browser shortcuts or developer tools. Additionally, the application continues to expose sensitive information through HTML comments, reinforcing the concept of **information disclosure vulnerabilities** in client-side code. It is important to understand that restricting user interactions via JavaScript does not prevent access to underlying source code. Sensitive data should never be stored on the client side, regardless of any interface restrictions imposed.

---

## Natas 2
```
URL: http://natas2.natas.labs.overthewire.org
Username: natas2
Password: TguMNxKo1DSa1tujBLuZJnDUlCcUAPlI
```
After login, the following note is displayed: 

### Approach 

### Finding 

### Analysis

---

## Natas 3
```
URL: http://natas3.natas.labs.overthewire.org
Username: natas3
Password: 
```
After login, the following note is displayed: 

### Approach 

### Finding 

### Analysis

---

## Natas 4
```
URL: http://natas4.natas.labs.overthewire.org
Username: natas4
Password: 
```
After login, the following note is displayed: 

### Approach 

### Finding 

### Analysis

---


## Natas 5
```
URL: http://natas5.natas.labs.overthewire.org
Username: natas5
Password: 
```
After login, the following note is displayed: 

### Approach 

### Finding 

### Analysis

---


## Natas 6
```
URL: http://natas6.natas.labs.overthewire.org
Username: natas6
Password: 
```
After login, the following note is displayed: 

### Approach 

### Finding 

### Analysis

---


## Natas 7
```
URL: http://natas7.natas.labs.overthewire.org
Username: natas7
Password: 
```
After login, the following note is displayed: 

### Approach 

### Finding 

### Analysis

---


## Natas 8
```
URL: http://natas8.natas.labs.overthewire.org
Username: natas8
Password: 
```
After login, the following note is displayed: 

### Approach 

### Finding 

### Analysis

---


## Natas 9
```
URL: http://natas9.natas.labs.overthewire.org
Username: natas9
Password: 
```
After login, the following note is displayed: 

### Approach 

### Finding 

### Analysis

---


## Natas 10
```
URL: http://natas10.natas.labs.overthewire.org
Username: natas10
Password: 
```
After login, the following note is displayed: 

### Approach 

### Finding 

### Analysis

---


## Natas 11
```
URL: http://natas11.natas.labs.overthewire.org
Username: natas11
Password: 
```
After login, the following note is displayed: 

### Approach 

### Finding 

### Analysis

---


## Natas 12
```
URL: http://natas12.natas.labs.overthewire.org
Username: natas12
Password: 
```
After login, the following note is displayed: 

### Approach 

### Finding 

### Analysis

---


## Natas 13
```
URL: http://natas13.natas.labs.overthewire.org
Username: natas13
Password: 
```
After login, the following note is displayed: 

### Approach 

### Finding 

### Analysis

---


## Natas 14
```
URL: http://natas14.natas.labs.overthewire.org
Username: natas14
Password: 
```
After login, the following note is displayed: 

### Approach 

### Finding 

### Analysis

---


## Natas 15
```
URL: http://natas15.natas.labs.overthewire.org
Username: natas15
Password: 
```
After login, the following note is displayed: 

### Approach 

### Finding 

### Analysis

---


## Natas 16
```
URL: http://natas16.natas.labs.overthewire.org
Username: natas16
Password: 
```
After login, the following note is displayed: 

### Approach 

### Finding 

### Analysis

---


## Natas 17
```
URL: http://natas17.natas.labs.overthewire.org
Username: natas17
Password: 
```
After login, the following note is displayed: 

### Approach 

### Finding 

### Analysis

---


## Natas 2
```
URL: http://natas2.natas.labs.overthewire.org
Username: natas2
Password: 
```
After login, the following note is displayed: 

### Approach 

### Finding 

### Analysis

---
