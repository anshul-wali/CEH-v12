# Section 4 : Sniffing Countermeasures
# Defend Against Sniffing
- Restrict Physical Access
- End-to-end encryption
- Use IPv6 instead of IPv4
- Add MAC address of gateway
- Use more Secure versions of protocols
- Switch instead of hub

# Detect Sniffing
- Check the devices running on Promiscuous Mode
- Run IDS
- Run Network tools

# Sniffer Detection Techniques
- Ping Method :
  
    Sends a ping request to the suspect machine with its IP address and an incorrect MAC address. The Ethernet adapter
    rejects it, as the MAC address does not match, whereas the Suspect machine running the sniffer responds to it as it does
    not reject packets with a different MAC address

- DNS Method :
  
  The reverse DNS lookup is the opposite of the DNS lookup method. Sniffers using
  reverse DNS lookup increase network traffic. This increase in network traffic can be an
  indication of the presence of a sniffer on the network. The computers on this network
  are in promiscuous mode.
 
- ARP Method

# Detection tools
- Nmap :
  
  NSE SCript allows to check if a system on alocal ethernet has its network card in promiscuous mode

- NetScan Tools Pro

  It includes a Promiscuous mode scanner tool to scan the subnet for network interfaces for all ethernet packets in the promiscuous mode.
