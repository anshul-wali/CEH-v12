#  Section 6: Email Footprinting 

# Email Tracking
- Email tracking si used to monitor the delivery of emails to an intended recipient
- Attackers track emails to gather information about a target recipient, such as IP addresses, geolocation, browser, Device Type and OS details, to build a hacking strategy and perform social engineering and other attacks.


## Collecting Information from Email Head

## tools
- Infoga
	 info Infoga si a tool used for gathering email account information (IP, hostname, country, etc.) from different public sources (search engines, pgp key servers, and Shodan), and it checks fi an email was leaked using the haveibeenpwned.com API.
	 For example, the command  below will retrieve all the publicly available email addresses related to the domain microsoft.com along with email account information.
```
	python infoga.py --domain microsoft.com --source all —-breach -v 2 --report ../microsoft.txt
```

- eMailTrackerPro
	 As shown in the screenshot, attackers use eMailTrackerPro to analyze email headers and extract information such as the sender's geographical location, IP address, and so on. It allows an attacker to review the traces later by saving past traces
	 Source: http://www.emailtrackerpro.com 



# Section 7: Whois Footprinting
# Whois Lookup
- Large database of whois information, DNS, domain names, name servers, IPs, andtools for searching and monitoring domain names.
- This protocol listens to requests on port 43 (TCP)
- Maintained by Regional Internet Registries (RIRs)
- Types:
	- **Thick Whois** - Stores the complete Whois information from all the registrars for a particular set of data.
	- **Thin Whois** - Stores only the name of the Whois server of the registrar of a domain, which in turn holds complete details on the data being looked up.
- 
 
 Link: [https://who.is](https://who.is/)

# Finding IP Geolocation Information
IP geolocation helps to identify information, such as country, region/state, city, ZIP/postal code, time zone, connection speed, ISP (hosting company), domain name, DID country code, area code, mobile carrier, and elevation
## IP2Location
Source: https://www.ip2location.com
Attackers use IPLocation tool to identify a visitor's geographical location, i.e., country, region, city, latitude and longitude of city, ZIP code, time zone, connection speed, ISP, domain name, IDD country code, area code, weather station code and name, mobile carrier, elevation, and usage type information using a proprietary IP address lookup database and technology.

# Section 8: DNS Footprinting

# Extracting DNS Information
DNS footprinting reveals information about DNS zone data. DNS zone data include DNS domain names, computer names, IP addresses, and much more information about a network. An attacker uses DNS information to determine key hosts in the network and then performs social
engineering attacks to gather even more information

## SecurityTrails
Source: https://securitytrails.com
SecurityTrails is an advanced DNS enumeration tool capable of creating a DNS map of the target domain network. It can enumerate both current and historical DNS records such as A, AAAA, NS, MX, SOA, and TXT, which helps in building the DNS structure. It also enumerates all the existing subdomains of the target domain using brute-force
techniques.

# Reverse DNS Look
DNS lookup is used to find the IP addresses for a given domain name, and a reverse DNS operation is performed to obtain the domain name of a given IP address.

## DNSRecon
DNSRecon is a Python script that provides the ability to perform: Check all NS Records for Zone Transfers. -r is the of IP addresses
```
dnsrecon -r 162.241.216.0-162.241.216.255
```

Link: [https://github.com/darkoperator/dnsrecon](https://github.com/darkoperator/dnsrecon)

## Reverse Lookup
The Reverse Lookup tool performs a reverse PI lookup by taking an IP address and locating a DNS PTR record for that IP address.
Link: https://mxtoolbox.com

# Section 9: Network Footprinting
To find the network range of the target network, one must enter the server IP address (gathered in Whois footprinting) in the ARIN Whois database search tool. A user can also visit the ARIN website (https://www.arin.net/about/welcome/region) and enter the server IP into the SEARCH Whois text box. This yields the network range of the target network.

## Traceroute
In computing, traceroute and tracert are computer network diagnostic commands for displaying possible routes (paths) and measuring transit delays of packets across an Internet Protocol (IP) network. The history of the route is recorded as the round-trip times of the packets received from each successive host (remote node) in the route (path); the sum of the mean times in each hop is a measure of the total time spent to establish the connection

ICMP Traceroute
Windows operating system by default uses ICMP traceroute.
```
tracert <ip address>
```

TCP Traceroute
Many devices in any network are generally configured to block ICMP traceroute messages. In this scenario, an attacker uses TCP or UDP traceroute, which si also known as Layer 4 traceroute.
```
teptraceroute www.google.com
```

UDP Traceroute
Like Windows, Linux also has a built-in traceroute utility, but it uses the UDP protocol for tracing the route to the destination.
```
traceroute www.google.com
```

## Traceroute Analysis
We have discussed how the traceroute utility helps find the IP addresses of intermediate devices such as routers and firewalls present between a source and its destination. After running several traceroutes, an attacker can find the location of a hop in the target network.

## Traceroute Tools
- Path Analyzer Pro
	 This tool helps attackers to gather information such as the hop number, its PI address, hostname, ASN, network name, percentage loss, latency, average latency, and standard deviation for each hop ni the path.
	 Source: https://www.pathanalyzer.com
- VisualRoute
	 VisualRoute tool enables attackers to gather information such as hop number, IP address, node name, and geographical location of each hop in the route.
	 Source: http://www.visualroute.com
- Traceroute NG
- PingPlotter

# Section 10: Footprinting through Social Engineering
Social engineering is an art of exploiting human behaviour to extract confidential information

# Eavesdropping 
It is the act of secretly or stealthily listening to the private conversation or communications of others without their consent in order to gather information. 

## Shoulder Surfing
In computer security, shoulder surfing is a type of social engineering technique used to obtain information such as personal identification numbers (PINs), passwords and other confidential data by looking over the victim's shoulder. Unauthorized users watch the keystrokes inputted on a device or listen to sensitive information being spoken, which is also known as eavesdropping

## Dumpster Diving
Dumpster diving (also totting, skipping, skip diving or skip salvage) is salvaging from large commercial, residential, industrial and construction containers for unused items discarded by their owners but deemed useful to the picker.

## Impersonation
Pretending to be a legitimate or authorized person and using the phone or other communication medium to mislead targets and trick them into revealing information

# section 11: Footprinting Tool
# Maltego 
Maltego can be used to determine the relationships and real world links between people, groups of people, organizations, websites, Internet infrastructure, documents, etc.

# Recon-ng 
Recon-ng is a Web Reconnaissance framework with
independent modules and database interaction, 
which provides an environment in which open source, web-based reconnaissance can be conducted

# FOCA 
(Fingerprinting Organizations with Collected Archives) is a tool used mainly to find metadata and hidden information in the documents it scans
Source: https://www.elevenpaths.com

# OSRFramework 
OSRFramework includes applications related to username checking, DNS lookups, information leaks research, deep web search, and regular expression extraction.

Tools included in the OSRFramework package
- usufy.py -Checks for a user profile on up to 290 different platforms
- mailfy.py-Check for the existence of a given email
- searchfy.py-Performs a query on the platforms in OSRFramework
- domainfy.py -Checks for the existence of domains
- phonefy.py -Checks for the existence of a given series of phone
- entify.py-Uses regular expressions to extract entities

# OSINT Framework
OSINT Framework is an open source intelligence gathering framework that is focused on gathering information from free tools or resources

Source: https://osintframework.com

# Recon-Dog 
Recon-Dog is an all-in-one tool for al basic information gathering needs. It uses APIs to collect information about the target system. 

# BillCipher 
BillCipher is an information gathering tool for a website or IP address. It can work on any operating system that supports Python 2, Python 3, and Ruby. This tool includes various options such as DNS lookup, Whois lookup, port scanning, zone transfer, host finder, and reverse
PI lookup, which help to gather critical information.
# Spyse
Attackers can use different parameters available in this  tool to identify information such as subdomains, certificates, and vulnerabilities risk scores


