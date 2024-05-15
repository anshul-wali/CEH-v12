# Section 8: DNS Footprinting

# Extracting DNS Information
DNS footprinting reveals information about DNS zone data. DNS zone data include DNS domain names, computer names, IP addresses, and much more information about a network. An attacker uses DNS information to determine key hosts in the network and then performs social
engineering attacks to gather even more information

## SecurityTrails
SecurityTrails is an advanced DNS enumeration tool capable of creating a DNS map of the target domain network. It can enumerate both current and historical DNS records such as A, AAAA, NS, MX, SOA, and TXT, which helps in building the DNS structure. It also enumerates all the existing subdomains of the target domain using brute-force
techniques.

Link: https://securitytrails.com

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
