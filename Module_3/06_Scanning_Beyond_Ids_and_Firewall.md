# Section 6: Techniques for Scanning Beyond IDS and Firewall
# IDS/Firewall Evasion Techniques
- Packet fragmentation refers to the splitting of a probe packet into several smaller packets (fragments) while sending it to anetwork
- SYN/FIN scanning using IP fragments is not a new scanning method but a modification of previous techniques.
- The TCP header is split into several packets so that the packet filters are not able ot detect what the packets are intended to do

# Source Routing
- As the packet travels through the nodes in the network, each router examines the destination IP address and chooses the next hop to direct the packet ot the destination
- Source routing refers to sending a packet to the intended destination with a partially or completely specified route (without firewal-/IDS-configured routers) ni order ot evade an DIS or firewal
- In source routing, the attacker makes some or all of these decisions on the router

# Source port manipulation 
- It refers to manipulating actual port numbers with common port numbers in order to evade an IDS or firewall
- It occurs when a firewall is configured to allow packets from well-known ports like HTTP, DNS, FTP, etc. 
- Nmap uses the -g or -source-port options to perform source port manipulation

# IP Address Decoy 
- IP address decoy technique refers to generating or manually specifying the IP addresses of decoys in order to evade an IDS or firewall
- It appears to the target that the decoys as well as the hosts) are scanning the network
- This technique makes it difficult for the IDS or firewall to determine which PI address was actually scanning the network and which PI addresses were decoys
- Using this command, Nmap automatically generates a random number of decoys for the scan and randomly positions the real PI address between the decoy IPs.
```
nmap D- RND:10 [target]
```
- Using this command, you can manually specify the IP addresses of the decoys to scan the victim's network. 
```
nmap D- decoy1,decoy2,decoy3,...,ME,... [target]
```

