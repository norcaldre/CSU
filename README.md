# CSU
CyberSecurity University Assignments

# Project 8 - Pentesting Live Targets

Time spent: 5 hours spent in total

> Objective: Identify vulnerabilities in three different versions of the Globitek website: blue, green, and red.

The six possible exploits are:
* Username Enumeration
* Insecure Direct Object Reference (IDOR)
* SQL Injection (SQLi)
* Cross-Site Scripting (XSS)
* Cross-Site Request Forgery (CSRF)
* Session Hijacking/Fixation

Each version of the site has been given two of the six vulnerabilities. (In other words, all six of the exploits should be assignable to one of the sites.)

## Blue

Vulnerability #1: _SQLI_____________

<img src="https://github.com/norcaldre/CSU/blob/master/blue_sqli.gif?raw=true" width="800">

Vulnerability #2: ___Session Hijacking/Fixation__

<img src="https://github.com/norcaldre/CSU/blob/master/blue_session.gif?raw=true" width="800">

## Green

Vulnerability #1: __User Enumeration___

<img src="https://github.com/norcaldre/CSU/blob/master/green_user.gif?raw=true" width="800">

Vulnerability #2: _____XSS__________

<img src="https://github.com/norcaldre/CSU/blob/master/green_xss.gif?raw=true" width="800">


## Red

Vulnerability #1: ____CSRF_________

<img src="https://github.com/norcaldre/CSU/blob/master/red_csrf.gif?raw=true" width="800">

Vulnerability #2: ___IDOR___________

<img src="https://github.com/norcaldre/CSU/blob/master/red_idor.gif?raw=true" width="800">


## Notes

The IDOR challenge took a little while to figure out as the difference between the errors with a valid username and a non-valid username was very subtle.  The rest of the challenges were pretty straight forward.















Exploit 1

Wordpress version: 4.2

Time: 2 hours

Issue

If the text entered into the comment field exceeds 64kb, the input gets truncated in the MySQL database.  This enables XSS capability.

1.  Use commnad with over 64kb worth of chartacters attached:  <a title='x onmouseover=alert(unescape(/hello%20world/.source)) style=position:absolute;left:0;top:0;width:5000px;height:5000px  AAAAAAAAAAAA...[64 kb]..AAA'></a>

2.  Entered data into comments field on WordPress page

3.  Command executed, in this case, a 'Hello World' pop up alert.

<img src="https://github.com/norcaldre/CSU/blob/master/Exploit1.gif?raw=true" width="800">


Exploit 2

WordPress version 4.2

Time: 1 hour

Issue 

Contributers can embed a YouTube link with code in the link to execute an XSS attack.

1.  Grab embeded video link from YouTube

2.  Created embeded link for WordPress site with link for YouTube video and XXS code for an alert.

[embed src='https://www.youtube.com/embed/7uf7Qn1uFJs\x3csvg onload=alert(document.cookie)\x3e'][/embed]

3.  Place code on vulbnerable page. 

<img src="https://github.com/norcaldre/CSU/blob/master/Exploit2.gif?raw=true" width="800">


Exploit 3

WordPress version 3.9

Time: 1 hour

Issue

Session does not terminate when user logs out of admin console.

1.  Logged into admin console as 'admin'

2.  Captured HTTP traffic through Burp, sent GET request for /wp-admin/profile.php to repeater

3.  Logged out of admin console

4.  Resent captured GET request, session was still active. 

<img src="https://github.com/norcaldre/CSU/blob/master/Exploit3.gif?raw=true" width="800">


