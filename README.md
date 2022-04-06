# nmap
various nmap commands that i use

# HOST DISCOVERY with nmap

* ARP Ping Scan
 nmap -sn -PR [target ip]   # -PR (PingArp) to perform ARP Ping scan   -sn to disable port scan (port scan is enabled by default)
 
* UDP Ping Scan
 nmap -sn -PU [target IP]   # -PU (PingUdp) to perform UDP Ping scan   -sn to disable port scan (port scan is enabled by default)
 
* ICMP Echo Ping Scan
 nmap -sn -PE [target IP]   # -PE (PingEcho) to perform ICMP Echo scan -sn to disable port scan (port scan is enabled by default)
    -L to increase number of pings  and  -T to tweak timeout value
  - ICMP Echo Ping Sweep
  nmap -sn -PE [IP RANGE]   # -PE (PingEcho) -sn disabpe port scan
  
# alternatives to ICMP ECHO ping scan when administrators block ICMP ECHO Pings
* ICMP Timestamp Ping Scan
 nmap -sn -PP [target IP]   # -PP to perform Ping Timestamp Scan  -sn to disable port scan
 
* ICMP Address Mask Ping Scan
 nmap -sn -PM [target IP]   # -PM (PingMask) to perform address mask ping scan
 
* TCP SYN Ping Scan - send empty TCP SYN packets and waits for ACK response from ALIVE hosts
 nmap -sn -PS [target IP]   # -PS (PingSyn) to perform Ping SYN scan  -sn to disable port scan
 
* TCP ACK Ping Scan - send empty TCP ACK packets and waits for RST response from ALIVE hosts
 nmap -sn -PA [target IP]   # -PA (PingAck) to perform Ping ACK scan  -sn to disable port scan
 
* IP Protocol Ping SCan - send various probe packets to target different IP protocols and waits for any response to indicate host ALIVE
 namp -sn -PO [target IP]   # -PO to perform probe scan  -sn to disable port scan
 
 ---------------------------------------------------------------------------------------------------------------------------------------
 
 # PORT SCANNING with nmap
 
 
 
