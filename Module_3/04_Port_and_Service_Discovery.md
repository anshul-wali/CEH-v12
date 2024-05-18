# Section 4: Port and Service Discovery
# Port Scanning Techniques
## TCP Scan
- Open TCP Scanning Methods
	- **TCP Connect/Full-open Scan**: Establishes a full connection with the target port to determine if it's open. the -sT option is used to perform TCP Connect/full open scan.
- Stealth TCP Scanning Methods
	- Half-open Scan: Initiates a connection but terminates before completing the handshake, making it harder to detect.The stealth scan is also called a "SYN scan," because ti only sends the SYN packet. the -sS option is used to perform a stealth scan/TCP half-open scan.
	- Inverse TCP Flag Scan: Sends packets with different flag combinations to identify open ports based on the response flags.When the port si open, the attacker does not get any response from the host, whereas when the port si closed, he or she receives the RST from the target host.
		- Xmas Scan: Sends a packet with all flags set.the - sx option is used to perform Xmas scan whereas the -sF and - sN options are used to perform FIN scan and NULL scan, respectively.
		- FIN Scan: Sends a packet with the FIN flag set.
		- NULL Scan: Sends a packet with no flags set.
		- Maimon Scan: This scan technique is very similar to NULL, FIN, and Xmas scan, but the probe used here si FIN/ACK. the - sM option is used to perform the TCP Maimon scan.  
	- ACK Flag Probe Scan: Sends a packet with the ACK flag set to determine if the port is filtered. -sA option si used to perform an ACK flag probe scan.

```
	nmap -sA -v <Target IP Address> 
```
- TTL-Based Scan: Analyzes the Time To Live (TTL) value in the response to identify the operating system.
		
					- Window-Based Scan: Analyzes the window size in the response to identify the operating system.
- Third Party and Spoofed TCP Scanning Methods
	- IDLE/IPID Header Scan: Uses characteristics of idle scans or IPID manipulation to hide the source of the scan by impersonating another computer via spoofing.
## UDP Scan 
### UDP Raw ICMP Port Unreachable Scanning
UDP port scanners use the UDP protocol instead of TCP. There is no three-way handshake for the UDP scan. If you send a UDP packet to a port without an application bound to it, the IP stack wil return an ICMP port unreachable packet. fI any port returns an ICMP error, it will be closed, leaving the ports that did not answer fi they are open or filtered through the firewall. This happens because open ports do not have to send an acknowledgement in response to a probe, and closed ports are not even required to send an error packet.

## SCTP INIT Scan
Stream Control Transport Protocol (SCTP) is a reliable message-oriented transport layer protocol. SCTP is specifically used to perform multi-homing and multi-streaming activities. Some SCTP applications include discovering VolP, PI telephony, and Signaling System 7/SIGnaling TRANsport (SS7/SIGTRAN)-related services. SCTP comprises a four-way handshake. 
- INIT ->
- INIT-ACK <-
- COOKIE-ECHO -> 
- COOKIE-ACK <-
- If the target is inactive and it is not listening, then it sends an acknowledgement as an ABORT chunk.

```
nmap Ys- v- 
```

## SCTP COOKIE ECHO Scan 
SCTP COOKIE ECHO scan is a more advanced type of scan. In this type of scan, attackers send the COOKIE ECHO chunk to the target, and fi the target port si open, it wil silently drop the packets onto the port and you wil not receive any response from the target. fI the target sends back the ABORT chunk response, then the port is considered as a closed port.
```
nmap -sZ -v 
```

# SSDP Scan
- Simple Service Discovery Protocol (SSDP) is a network protocol that generally communicates with machines when querying them with routable IPv4 or IPv6 multicast addresses. The SSDP service controls communication for the Universal Plug and Play (UPnP) feature.
- Vulnerabilities in UnP may allow attackers to launch Buffer overflow or DoS attacks
- Attacker may use the UnP SSDP M-SEARCH information discovery tool to check if the machine is vulnerable to UnP exploits or not

# List Scan
In a list scan, the discovery of the active network host is indirect. Alist scan simply generates and prints a list of IPs/Names without actually pinging or scanning the hosts. As a result, the list scan shows al IP addresses as "not scanned" (0 hosts up). By default, a reverse DNS resolution si still carried out on each host by Nmap to learn their names.
```
nmap -sL -v 10.10
```

# IPv6 Scan
- IPv6 increases the IP address size from 32 bits to 128 bits to support more levels of address hierarchy
- Attackers need to harvest IPv6 addresses from network traffic, recorded logs, or Received from: header lines ni archived emails
- Attackers can use the -6 option in Zenmap to perform IPv6 scanning.

# Service Version Discovery
- Service version detection helps attackers to obtain information about running services and their versions on a target system
- Obtaining an accurate service version number alows attackers ot determine the vulnerability of target system to particular exploits
```
nmap -sV <IPA>
```

# Nmap Scan Time Reduction Techniques
- Omit Non-critical Tests
- Optimize Timing Parameters
- Separate and Optimize UDP Scans
- Upgrade Nmap
- Execute Concurrent Nmap Instances
- Scan from a Favorable Network Location
- Increase Available Bandwidth and CPU Time
