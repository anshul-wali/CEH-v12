
# IPsec Enumeration
- IPsec uses Encapsulation Security Payload (ESP), Authentication Header (AH), and Internet Key Exchange (IKE) to secure communication between virtual private network (VPN) end points
- Most IPsec based VPNs use Internet Security Association and Key Management Protocol
(ISAKMP), a part of IKE, to establish, negotiate, modify, and delete Security Associations (SA) and
cryptographic keys in a VPN environment
• Asimple scanning for ISAKMP at UDP port 500 can indicate the presence of a VPN gateway
• Attackers can probe further using a tool, such as ike-scan, to enumerate sensitive information, includingencryption and hashingalgorithm, authentication type, key distribution algorithm, and SA LifeDuration

# VoIP
- VoIP uses Session Initiation Protocol (SIP) protocol to enable voice and video calls over an IP network
- SIP service generally uses UDP/TCP ports 2000, 2001, 5060, and 5061
- VolP enumeration provides sensitive information, such as VolP gateway/servers, IP-PBX systems, client software (softphones)/VolP phones, User-agent IP addresses, and user extensions
- This information can be used to launch various Volp attacks, such as Denial-of-Service (DoS), Session Hijacking, Caller ID spoofing, Eavesdropping, Spamming over Internet Telephony (SPIT), and VolP phishing (Vishing)

- RPC allows clients and servers to communicate in distributed client/server programs.
- The portmapper service listens on TCP and UDP port 111 to detect the endpoints and present clients, along with details of listening RPC services.
- Enumerating RPC endpoints enables attackers to identify any vulnerable services on these service ports.

# Unix/Linux User Enumeration
- Unix/Linux user enumeration provides a list of users along with details such as the username, host name, and start date and time of each session.
- rusers
	 rusers displays a list of users who are logged in to remote machines or machines on the local network.
- rwho
	 Displays a list of users who are logged on to hosts on the local network
- finger
	 finger displays information about system users such as the user's login name, real name, terminal name, idle time, login time, office location, and office phone number

# Telnet Enumeration
- If the Telnet port 23 is found open, attackers can access shared information, including the hardware and software information of the target
- Telnet enumeration enables attackers to exploit identified vulnerabilities and perform brute-force attacks to gain unauthorized access to the target and launch further attacks
```
nmap -p 23 ‹target domain/IP Address>
```

# SMB Enumeration
- Attackers use SMB enumeration tools, such as Nmap, SMBMap, enum4linux, and nullinux, to perform a directed scan on the SMB service running on port 445
- SMB enumeration helps attackers to perform OS banner grabbing on the target
```
nmap -p 445 -A <target IP>
```

# FTP Enumeration 
- In FTP, data are transferred between a sender and receiver in plaintext, exposing critical information such as usernames and passwords to attackers.
- Attackers use Nmap to scan and enumerate open port 21 by running FTP services and further use the information to launch various attacks, such asTP bounce, FTP brute force, and packet sniffing

# TFTP Enumeration
- The Trivial File Transfer Protocol (TFTP) is a simplified version of FTP and is used for transferring files between network devices
- Attackers perform TFTP enumeration using tools, such as PortQry and Nmap, to extract information, such as running TFTP services and files stored on the remote server
- Using this information, attackers can gain unauthorized access to the target system, steal important files, and upload malicious script to launch further attacks

# IPv6 Enumeration
- Internet Protocol version 6 (IPv6) is an addressing protocol that identifies computer systems, including location information, and assists in routing traffic from one system to another system across a network.
- Attackers perform IPv6 enumeration on target hosts to obtain their IPv6 addresses and further scan the enumerated IP addresses to detect various security problems such as access to routing structure, exposure of sensitive content, and users' access control lists.

# BGP Enumeration
- The Border Gateway Protocol (BGP) is a routing protocol used to exchange routing and reachability information between different autonomous systems (AS) on the Internet. 
- Attackers perform BGP enumeration using tools, such as Nmap and BGP Tool kit , to discover the IPv4 prefix esannounced by the AS number and routing path folowed by the target
- Attackers use this information to launch various attacks, such as man-in-the- middle attack, BGP hijacking attack, and Dos attack against the target