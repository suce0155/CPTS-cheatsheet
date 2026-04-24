## Scan Network Range
sudo nmap 10.129.2.0/24 -sn -oA output | grep for | cut -d" " -f5

## Scan IP List
sudo nmap -sn -oA tnet -iL hosts.lst | grep for | cut -d" " -f5

## Scan Multiple IPs
sudo nmap -sn -oA tnet 10.129.2.18 10.129.2.19 10.129.2.20| grep for | cut -d" " -f5

## Scan Single IP with reason, packet-trace, without arp-ping
sudo nmap 10.129.2.18 -sn -oA host -PE --reason 
sudo nmap 10.129.2.18 -sn -oA host -PE --packet-trace --disable-arp-ping

## Scanning Top 10 TCP Ports
sudo nmap 10.129.2.28 --top-ports=10 

## Trace Packets
sudo nmap 10.129.2.28 -p 21 --packet-trace -Pn -n --disable-arp-ping

## Connect Scan on TCP Port 
sudo nmap 10.129.2.28 -p 443 --packet-trace --disable-arp-ping -Pn -n --reason -sT 

## More info on Filtered Ports
sudo nmap 10.129.2.28 -p 445 --packet-trace -n --disable-arp-ping -Pn

## Discovering Open UDP Ports
sudo nmap 10.129.2.28 -F -sU

## Version Scan
sudo nmap 10.129.2.28 -Pn -n --disable-arp-ping --packet-trace -p 445 --reason  -sV

## Version Scan All TCP Ports
sudo nmap 10.129.2.28 -p- -sV
sudo nmap 10.129.2.28 -p- -sV -Pn -n --disable-arp-ping --packet-trace

## Adjusting Packet Rate Scan
sudo nmap 10.129.2.0/24 -F -oN tnet.minrate300 --min-rate 1000

## Adjusting Timing Template 
sudo nmap 10.129.2.0/24 -F -T 4