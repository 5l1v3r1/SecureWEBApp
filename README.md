# SecureWEBApp
Coded a secure web application for learning purpose.. 

Removing all the vulnerabilities present in https://github.com/mohdhaji87/VulnerableWEBApp .

This application has eliminated vulnerabilities making secure php application 

Try all the attacks of vulnerable application you will not able to exploit it...


--> SQLI (Select , Update , Insert, Delete)
[select SQLI in login bypass mysqli_real_escape_string() is used]
[Insert SQLI in Register process parameterized queries are used] 
[Update SQLI in profile update , changing password  mysqli_real_escape_string() is used] 
[Delete SQLI in Deleting account  mysqli_real_escape_string() is used] 
[Blind SQLI in Forgot password prevented using mysqli_real_escape_string()]

--> Clickjacking (Framebursting technique, X-frame options missing)
[Framebursting is used in all vulnerable application pages which can be exploited using sandbox="allow-forms" ] 
[X-frame options : DENY is added as defence for clickjacking in all secure app pages]

-->Insecure Direct Object reference
[Account deletion (User can't delete other users account)]
[Password change (User can't change other users password)]  

-->Command Injection 
[ping functionality is secured from  command injection using escapeshellcmd()]  

-->CSRF 
[ csrf tokens added ]  

-->XSS
[ user input enconding/sanitizaion . output also encoded with htmlentities() which is not prone to xss ]
[Update htmlentities() function when passed in javascript as sanitization can be bypassed using either unicode or hexadecimal escape sequence such as \x3c for < and \x3e for >  \x3d for = symbol so payload can be \x3c img src\x3dx onerror\x3dalert("T")\x3e  ]

-->Local File Inclusion (LFI) : (While including TOS file)
(Null byte may be used as bypass . We need to use whitelisting for complete elimination of vulnerability)
