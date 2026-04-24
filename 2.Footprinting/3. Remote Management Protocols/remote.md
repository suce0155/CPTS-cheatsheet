## SSH-Audit
./ssh-audit.py 10.129.14.132

## Change Authentication Method
ssh -v cry0l1t3@10.129.14.132

## Enumerating Open rsync
nc -nv 127.0.0.1 873
rsync -av --list-only rsync://127.0.0.1/dev

## R-Services Config Files
/etc/hosts.equiv
cat .rhosts

## Initiate RDP Session
xfreerdp /u:cry0l1t3 /p:"P455w0rd!" /v:10.129.201.248

## Initiate Winrm Session
evil-winrm -i 10.129.201.248 -u Cry0l1t3 -p P455w0rD!

## Initiate WMI Session
wmiexec.py Cry0l1t3:"P455w0rD!"@10.129.201.248 "hostname"