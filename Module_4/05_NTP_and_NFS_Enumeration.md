# Section 5:
# NTP Enumeration
- NTP is designed to synchronize clocks of networked computers.
- It uses UDP port 123 as its primary means of communication. 
- NTP can maintain time within an error of 10 ms over the public Internet.
- Furthermore, it can achieve an accuracy of 200 us or better in LANs under ideal conditions.
## Information an attacker can obtain by querying an NTP server:
- List of hosts connected to the NTP server
- Clients IP addresses in the network, their system names, and OSs
- Internal IPs, fi the NTP server is in the demilitarized zone (DMZ)

# NTP Enumeration Commands
## ntpdate
This command collects the number of time samples from several time sources. 
```
ntpdate [-46bBdgsuv]  I-p samples]
[-a key] [-e authdelay] [-k keyfile] [-o version] [-t timeout] [ -U user_name] server [. . . ]
```

## ntptrace
This command determines where the NTP server obtains the time from and follows the chain of NTP servers back to its primary time source. Attackers use this command to trace the list of NTP servers connected to the network. 
```
ntptrace [-n] I-m maxhosts] [servername/IP_address]
```

## ntpdc
This command queries the ntpd daemon regarding its current state and requests changes in that state. Attackers use this command to retrieve the state and statistics of each NTP server connected to the target network. 
```
ntpdc [ -46dilnps ] [ -c command] [hostname/IP_address]
```

## ntpq
This command monitors the operations of the NTP daemon ntpd and determines its performance. 
```
ntpq [-46dinp] I-c command] [host/IP_address]
```

# NTP Enumeration Tools
# PRTG Network Monitor
PRTG monitors al systems, devices, traffic, and applications of TI infrastructure by using various technologies such as SNMP, WMI, and SH. Attackers use PRTG Network Monitor ot retrieve SNTP server details such as the response time from the server, active sensors with the server, and synchronization time.

Source: https://www.paessler.com

## More Tools
- Nmap (https://nmap.org)
- Wireshark (https://www.wireshark.org)
- udp-proto-scanner (https://labs.portcullis.co.uk)
- NTP Server Scanner (http://www.bytefusion.com)

# NFS Enumeration
- An NFS system is generally implemented on a computer network in which the centralization of data is required for critical resources. The remote procedure call (RPC) is used to route and process the request between clients and servers.
- NFS enumeration enables attackers to identify the exported directories, list of clients connected to the NFS server along with their PI addresses, and the shared data associated with the IP addresses

Command to scan the target IP address for an open NFS port (port 2049) and the NFS services running on it:
```
rpcinfo -p <Target IP Address>
```

Command to view the list of shared files and directories:
```
showmount - e <Target IP Address>
```

# NFS Enumeration Tools
# RPCScan
RPCScan communicates with RPC services and checks misconfigurations on NFS shares. An attacker runs the following command to enumerate a target IP address for active NFS services:
```
python3 rpc-scan.py <Target IP Address> --rpc
```

# SuperEnum
SuperEnum includes a script that performs the basic enumeration of any open port. As shown ni the screenshot, an attacker uses the ./ superenum script and then enters a text file name "Target. txt" having a target IP address or a list of IP addresses for enumeration.
