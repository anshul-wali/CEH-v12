# Section 5: OS Discovery
# OS Discovery/Banner Grabbing
- Banner grabbing or OS fingerprinting is the method used to determine the operating system running on a remote target system. 
- Identifying the OS used on the target host allows an attacker to figure out the vulnerabilities possessed by the system and the exploits that might work on a system to further carry out additional attacks
- There are two types of banner grabbing: active and passive

## Active Banner Grabbing
Active banner grabbing applies the principle that an OS's IP stack has a unique way of responding to specially crafted TCP packets. In active banner grabbing, the attacker sends a variety of malformed packets to the remote host, and the responses are compared with a database. Responses from different OS vary because of differences in TCP/IP stack implementation.

## Passive Banner Grabbing
Like active banner grabbing, passive banner grabbing also depends on the differential implementation of the stack and the various ways in which an OS responds to packets. However, instead of relying on scanning the target host, passive fingerprinting captures packets from the target host via sniffing to study telltale signs that can reveal an OS.

## Commonly Targeted Ports and Services
- Port 80 (HTTP)
- Port 21 (FTP)
- Port 25 (SMTP)
- Port 22 (SSH)
- Port 443 (HTTPS)
- Port 3306 (MySQL)

# How to Identify Target System OS
- Attackers can identify the OS running on the target machine by looking at the Time To Live (TTL) and TCP window size in the IP header of the first packet in a TCP session
- Sniff/capture the response generated from the target machine using packet-sniffing tools like Wireshark and observe the TTL and TCP window size fields
Link: [https://github.com/Samsar4/Ethical-Hacking-Labs/blob/master/2-Scanning-Networks/2-TTL.md](https://github.com/Samsar4/Ethical-Hacking-Labs/blob/master/2-Scanning-Networks/2-TTL.md)

# OS Discovery using Nmap and Unicornscan
- In Nmap, the O- option is used to perform OS discovery, providing OS details of the target machine
- In Unicornscan, the OS of the target machine can be identified by observing the TL values ni the acquired scan result

# OS Discovery using Nmap Script Engine
- Nmap script engine (NSE) can be used to automate awide variety of networking tasks by alowing the users ot write and share scripts
- Attackers use various scripts in the Nmap Script Engine to perform OS discovery on the target machine
- in Nmap, smb-os- discovery is an inbuilt script used for collecting OS information on the target machine throughthe SMB protocol.
- In Zenmap, the -sC option or -script option is used to activate the NSE scripts

# OS Discovery using IPv6 Fingerprinting
- IPv6 Fingerprinting can be used to identify the OS running on the target machine
- IPv6 fingerprinting has the same functionality as that of IPv4 but the difeerence is that the IPv6 uses several additional advanced probes specific ot IPv6 along with a separate OS detection engine that is specialized for IPv6
- In Zenmap, the 6- option and O- option are used to perform OS discovery using the IPv6 fingerprinting method
```
 nmap -6 -O <target>
```

