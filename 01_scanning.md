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
```bash  sudo wireshark
# specific scan
ip.addr == 192.168.18.136 && tcp 
```
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
   
   
  ### [Nmap Cheat sheet](https://www.stationx.net/nmap-cheat-sheet/)
  
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
  #### Types of port scan
   - SYN Scan
   - TCP Scan
   - UDP Scan
   - SYN Scan vs TCP Scan 
   - Some other scans

 ### - SYN Scan (-sS)
       - Quick Scan
       - cant be stoped by firewalls
    ```bash
    nmap -sS 172.12.99.0/24 --top-ports 50
    # Scan port fast
      nmap -sS 192.168.18.6 -F
    # scan ports between
    nmap -sS -sU 192.32.34.32 -pT:80,443,U,139-150
    # top ports 
    nmap -sS 171.15.66.206 --top-ports 20
    # scall all ports 
    namp -sS 172.16.99.295 -p1-65535
    # or 
      nmap -sS 172.16.99.295 -p1- 
    ```
   
 ### Detecting hosts Port scan 
  - what if a host's Ping service is closed
  - Especially while scanning from out side and scanning serve blocks
   ```bash 
   nmap -sS --top-ports10 --open 172.20.1.9/24 -pn -n
  ```
  
  ### TCP Scan
  ```bash
  nmap -sT -n -Pn 172.33.33.206 --top-ports 10
  
  # scan a specific port
  sudo nmap -sT -n -Pn 192.168.18.116 -p80

  ```
  <img src="https://raw.githubusercontent.com/b-khan7276/CEH/main/syn%20scan%20vs%20TCP%20scan.png" height="235" >
  
  ### UDP Scan (-sU)
   
   - Takes long time (Timeouts)
   - some imp ports: DNS (53), TFTP(69), DHCP (67-68), NTP(124), SNMP (161-162)
   - Sends empty UDP packets in general.
   - Should run with version detection options for more accurate results
   
   ```bash
   nmap -sU -Pn 192.168.18.136 --top-ports 10 --reason -sV
```
 ## Nmap Script scanning
 
<img src="https://raw.githubusercontent.com/b-khan7276/CEH/main/nmap%20script%20scanning.png" height="235">

###  Nmap scrips
   <img src ="https://raw.githubusercontent.com/b-khan7276/CEH/main/script%20scanning%20nmap.png" height="400"/>
 
 ```bash 
 #scan all port with ssh script
 nmap 192.168.18.116 -p- --script ssh* -sV

 ```
 ### Helpful scrips

 <img src ="https://raw.githubusercontent.com/b-khan7276/CEH/main/helpful%20scrips.png" height="400"/>    
 
### ByPassing IPS/IDS Devices
  
 <img src ="https://raw.githubusercontent.com/b-khan7276/CEH/main/bypass%20IPS-IDS.png" height="400"/>




 
 
