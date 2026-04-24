## FTP Anonymous Login
ftp 10.129.14.136

## Download All Files from FTP
wget -m --no-passive ftp://anonymous:anonymous@10.129.14.136

## FTP Enum using nmap
sudo nmap -sV -p21 -sC -A 10.129.14.136

## Listing SMB Shares
smbclient -N -L //10.129.14.128
smbmap -H 10.129.14.128
crackmapexec smb 10.129.14.128 --shares -u '' -p ''
nxc smb 10.129.14.128 --shares -u '' -p ''

## Connecting to SMB Share
smbclient //10.129.14.128/notes

## Connecting RPCClient
rpcclient -U "" 10.129.14.128

## Show Available NFS Shares
showmount -e 10.129.14.128

## Mounting NFS Shares
sudo mount -t nfs 10.129.14.128:/ ./target-NFS/ -o nolock

## Unmounting NFS Shares
sudo umount ./target-NFS

## DIG - NS Query
dig ns inlanefreight.htb @10.129.14.128

## DIG - Version Query
dig CH TXT version.bind 10.129.120.85

## DIG - ANY Query
dig any inlanefreight.htb @10.129.14.128

## DIG - AXFR Zone Transfer
dig axfr inlanefreight.htb @10.129.14.128

## Subdomain Brute Forcing
dnsenum --dnsserver 10.129.14.128 --enum -p 0 -s 0 -o subdomains.txt -f /opt/useful/seclists/Discovery/DNS/subdomains-top1million-110000.txt inlanefreight.htb

## SNMPwalk
snmpwalk -v2c -c public 10.129.14.128

## Brute-forcing SNMP Community Names
onesixtyone -c /opt/useful/seclists/Discovery/SNMP/snmp.txt 10.129.14.128

## Connecting to MySQL
mysql -u root -pP4SSw0rd -h 10.129.14.128

## Connecting to MSSQL
python3 mssqlclient.py Administrator@10.129.201.248 -windows-auth

## Enum Oracle Databases
./odat.py all -s 10.129.204.235

## Connecting to Oracle DB using sqlplus
sqlplus scott/tiger@10.129.204.235/XE