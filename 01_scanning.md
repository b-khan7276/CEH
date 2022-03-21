# Scanning
## There are two types of scanning
  - Passive Scanning
  - Active Scanning

## Passive Scan : Smelling
  - Listen to the Network Traffic
      - Tcpdump
      - Wireshark
   - ARP tables
 
## Active scan: Testing
  - Nmap
  - Hping
  - Scapy
  - Ping, Teacert, Etc

### Passive scan Wireshark
```bash  sudo wireshark ```
### [HPing `Active Scan` ](https://github.com/antirez/hping)
 - Command-line
 - TCP/IP packet analyser
 - Inspired to the 'Ping' command

    - Firewall testing
    - Advanced port scanning
    - Network testing, using different protocols, TOS, fragmentation
    - Manual path MTU discovery
    - Advanced traceroute, under all the supported protocols
    - Remote OS fingerprinting
    - Remote uptime guessing
    - TCP/IP stacks auditing
    - hping can also be useful to students that are learning TCP/IP.
```bash
sudo apt install hping3
```
```bash 
hping3 --scan 0-500 -S 172.16.99.139
```
  - where --scan is scan 
  -  0-500 is rang of ports
  -   -S is syn flag
  -   and the ip
 #### Dos Attack usign Hping
 ```bash
 hping3 --flood -S -V --rand-source ww.owaspbwa.com
 ```

### [Nmap](https://nmap.org/)

  - Nmap useful tools
    - Zenmap
    - ncat
    - ndiff
    - nping
   
  <h4> Nmap uses Raw Ip packets </h4>
    
   - What host are avalible
   -  Which Ports are accesible
   -  Service and version detection
   -  What OS is running
   -  FireWall detection
   -  Vulnerability assessment
   -  Brute forece attacks
   -  Exploitation
   
  ### Ping Scan
  <b>Find out host in a network</b>
  
  <b> Nmap Ping scan = Np Port scan (-sn | -sp) </b>
  
   - Detection Live hosts
       - Only print out the avaiable hosts that responded  to the host discovery probes
   - (nmap -sn ) > Default behaviour for Pivileged User
          
       - ICMP echo request
       - SYN => TCP 442 port
       - ACK => TCP 80 Port
       - ICMP timestamo request
   - (nmap -sn ) > Default behaviour for unprivileged User
       - SYN ==> TCP 80, 443 ports
    
  #### Ping scan 
   ```bash
   # Scan the host
   nmap -sn 132.158.34.1/24
   
   # To get the ip addresses only
   sudo nmap -sn 172.16.99.0/24 -n | grep "Nmap scan" | cut -d" " -f5
  
   ```
   #### [TCP/Ip basics](https://www.techtarget.com/searchnetworking/definition/OSI)
      
   - 7: Appicaton Layer
        - Apps with user intercation 
            - HTTP, SMTP
   - 6: Presentation Layer
        - Meeting differnt formats || It is a part of OS
            - ACSII, MP3, JSG
   - 5: Session Layer
        - Sessions and sockets
            - SQL, RPC
   - 4: Transport Layerr 
        - Flow and error control
            - TCP, UDP
   - 3: Network Layer
        - END TO END communication, virtual addresses
            - IP
   - 2: Data Link Layer
       - Assessing media
          - Ethernet, Wireless
   - 1: Physcial Layer
        - Bitwise transportaton 
            - Coaxial cables, fiber cables etc
   <img src="https://raw.githubusercontent.com/b-khan7276/CEH/main/layer%20and%20protocols.png" height="350" width="750" />
   
            
  
  ### Port Scan
  
   - SYN Scan
   - TCP Scan
   - UDP Scan
    
 ### Services and version detection
 
 ### Os Detection
 
 ### Script Scan
 
 ### Timing
 
 ## IPS/IDS Evasion
 
 
