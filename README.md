# nmap
various nmap commands that i use

# HOST DISCOVERY with nmap

# ARP Ping Scan
 nmap -sn -PR [target ip]   # -PR (PingArp) to perform ARP Ping scan   -sn to disable port scan (port scan is enabled by default)
 
# UDP Pling Scan
 nmap -sn -PU [target IP]   # -PU (PingUdp) to perform UDP Ping scan   -sn to disable port scan (port scan is enabled by default)
 
# ICMP Echo Ping Scan
 nmap -sn -PE [target IP]   # -PE (PingEcho) to perform ICMP Echo scan -sn to disable port scan (port scan is enabled by default)
 #   -L to increase number of pings  and  -T to tweak timeout value
  #- ICMP Echo Ping Sweep
  nmap -sn -PE [IP RANGE]   # -PE (PingEcho) -sn disabpe port scan
  
# alternatives to ICMP ECHO ping scan when administrators block ICMP ECHO Pings
# ICMP Timestamp Ping Scan
 nmap -sn -PP [target IP]   # -PP to perform Ping Timestamp Scan  -sn to disable port scan
 
# ICMP Address Mask Ping Scan
 nmap -sn -PM [target IP]   # -PM (PingMask) to perform address mask ping scan
 
# TCP SYN Ping Scan - send empty TCP SYN packets and waits for ACK response from ALIVE hosts
 nmap -sn -PS [target IP]   # -PS (PingSyn) to perform Ping SYN scan  -sn to disable port scan
 
# TCP ACK Ping Scan - send empty TCP ACK packets and waits for RST response from ALIVE hosts
 nmap -sn -PA [target IP]   # -PA (PingAck) to perform Ping ACK scan  -sn to disable port scan
 
# IP Protocol Ping SCan - send various probe packets to target different IP protocols and waits for any response to indicate host ALIVE
 namp -sn -PO [target IP]   # -PO to perform probe scan  -sn to disable port scan
 
 ---------------------------------------------------------------------------------------------------------------------------------------
 
 # PORT SCANNING with nmap
 
 # TCP Connect/Full Open Scan - detects open port after three-way handshage - establishes a FULL connection and then closes with RST packet (SYN/port, SYNACK, ACK, RST)
  nmap -sT -v [target IP]   # -sT (scanTcp_connect) to perform SYN TCP CONNECT on most used ports -v verbose
  
 # STEALTH / Half-Open Scan - detects open port by abruptly terminating connection (SYN/port, SYNACK, RST)
  nmap -sS -v [target IP]   # -sS (scanStealth) to perform SYN STEALTH port scan
  
 # STEALTH -  Inverse TCP Flag Scan - detects open port by sending TCP probe packets with TCP flag (FIN, URG, PSH) set or NO flags (NULL) and if no response then port is OPEN (else will receive RST/ACK)
   # Xmas Scan - send FIN, URG and PUSH flags set (FIN - for OSes with RFC 793) - WILL NOT WORK on current versions of WINDOWS
   nmap -sX -v [target IP]  # -sX (scanXmas) -v verbose
   # Maimon Scan - send FIN/ACK probes and if no response port is Open|Filtered and if RST received then port is closed
   nmap -sM -v [target IP]  # -sM (scanMarimon) -v verbose
   # ACK Flag Probe Scan  - send prove with ACK flag set and analyze the header info (TTL and WINDOW field) of received RST packets
   nmap -sA -v [target IP]  # -sA (scanAck)  -v verbose
   # IDLE/IPID Header Scan or ZOMBIE Scan - used to send a spoofed source address
   namp -sI -v [zombie IP] [target IP]   # -sI (scanIdle or scanIpid) -v verbose
   
 # UDP scan
  nmap -sU -v [target IP]  # -sU (scanUdp) -v verbose
  
 # SCTP INIT Scanning - send an INIT chunk to the target and a reply with INIT+ACK implies port is open
  nmap -sY -v [target IP]  # -sY (scanYnit) -v verbose
  
 # SCTP COOKIE ECHO scanning - send a COOKIE ECHO chunk and NO response implies port is OPEN
  nmap -sZ -v [target IP]  # -sZ (scanZctp) -v verboes
  
 # List scanning - a reverse DNS resolution is performed to identify host names
  nmap -sL -v [target IP]  # -sL (scanList) -v verbose
  
  # IPv6 scanning
   nmap -6 -v [target IP]  # -6 ipv6 scan -v verbose
   
  # Service VERSION discovery
   nmap -sV -v [target IP]  # -sV (scanVersion) -v verbose
   
  # OS discovery
   nmap -O [target IP]  # -O (OSdiscovery)
   nmap --script smb-os-discovery.nse [target IP]  # --script samba  os discovery
  
  
   
 
