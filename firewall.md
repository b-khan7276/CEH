# Fire Wall 

##  Domain
 - Domain is logical   group 
 - you can define your own policies || Like Share drive will share with the user 
 - software like microsoft active directory 
 - 

## Linux firewire
 
<p>
 Iptables  and  ip6tables  are  used to set up, maintain, and inspect the tables of IPv4 and IPv6 packet filter rules in the Linux kernel.  Several
       different tables may be defined.  Each table contains a number of built-in chains and may also contain user-defined chains.


 </p>

 - Linux firewall is called Ip tables
 - It will monitor traffic from server
 - Ip rules are called chains
 - Chains will filtes out going or in comming requests
 - There are three types of filters
		- Input : Applies on input traffic
		- Farword : For packets being routed through the box 
		- Output : For locally-generated packets
```bash
# Append mode

sudo iptables -A <chain> -i <interface> -p <protocol (tcp/udp) > -s <source> --dport <port no.>  -j <target>

# Enabling trffic on localhost
sudo  iptables -A INPUT -i lo -j ACCEPT

``` 
#### Enabling connections on HTTP,SSH AND SSL Port

```bash
sudo iptables -A INPUT -p tcp --dport 22 -j ACCEPT
sudo iptables -A INPUT -p tcp --dport 80 -j ACCEPT
sudo iptables -A INPUT -p tcp --dport 443 -j ACCEPT

```
### It’s time to check if the rules have been appended in iptables:

```bash
sudo iptables -L -v
```
### Filtering Packets Based on Source

<p>  

Iptables allows you to filter packets based on an IP address or a range of IP addresses. You need to specify it after the -s option. For example, to accept packets from 192.168.1.3, the command would be:
</p>
```bash
sudo iptables -A INPUT -s 192.168.1.3 -j ACCEPT
```
<p>
You can also reject packets from a specific IP address by replacing the ACCEPT target with DROP.
</p>
```bash
sudo iptables -A INPUT -s 192.168.1.3 -j DROP
```

<p>
If you want to drop packets from a range of IP addresses, you have to use the -m option and iprange module. Then, specify the IP address range with –src-range. Remember, a hyphen should separate the range of ip addresses without space, like this:
</p>
```bash

sudo iptables -A INPUT -m iprange --src-range 192.168.1.100-192.168.1.200 -j DROP
```

<p>Dropping all Other Traffic </p>

```bash
sudo iptables -A INPUT -j DROP
```
<p>

Deleting Rules
 </p>
```bash
sudo iptables -F
```

<p> 
This command erases all current rules. However, to delete a specific rule, you must use the -D option. First, you need to see all the available rules by entering the following command:
</p>
```bash
sudo iptables -L --line-numbers
sudo iptables -D INPUT 3
```
### Persisting Changes

```bash

sudo /sbin/iptables-save

```
<p>
It will save the current rules on the system configuration file, which will be used to reconfigure the tables every time the server reboots.

Note that you should always run this command every time you make changes to the rules. For example, if you want to disable iptables, you need to execute these two lines:
 </p>
```bash

sudo iptables -F
sudo /sbin/iptables-save
```
