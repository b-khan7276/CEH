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
  
  ### Port Scan
  
   - SYN Scan
   - TCP Scan
   - UDP Scan
    
 ### Services and version detection
 
 ### Os Detection
 
 ### Script Scan
 
 ### Timing
 
 ## IPS/IDS Evasion
 
 
