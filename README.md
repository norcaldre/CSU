# CSU
CyberSecurity University Assignments

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


