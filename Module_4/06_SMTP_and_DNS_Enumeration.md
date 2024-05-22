

# Section 6: SMTP and DNS Enumeration
# SMTP Enumeration
- Mail systems commonly use SMTP with POP3 and IMAP, which enable users to save messages in the server mailbox and download them from the server when necessary. SMTP uses mail exchange (MX) servers to direct mail via DNS. It runs on TCP port 25, 2525, or 587.
- SMTP provides 3 built-in-commands: 
	- VRFY - Validates users
	- EXPN - Shows the actual delivery addresses of aliases and mailing lists.
	- RCPT TO - Defines the recipients of a message
- SMTP servers respond differently to VRFY, EXPN, and RCPT TO commands for valid and invalid users, based on which we can determine valid users on the SMTP server
- Attackers can directly interact with SMTP via the telnet prompt and collect a list of valid users on the SMTP server.

# SMTP Enumeration using Nmap and Metasploit
## nmap
Attackers use Nmap to enumerate information from the target SMTP server.
- The following command, when executed, lists all the SMTP commands available in the Nmap directory:
```
 nmap p- 25, 365, 587 -script=smtp-commands <Target IP Address ›
```
- Run the following command to identify SMTP open relays:
```
 nmap -p 25 -script=smtp-open-relay <Target IP Address 
```
- Run the following command to enumerate all the mail users on the SMTP server:
```
 nmap -p 25 -script=smtp-enum-users <Target IP Address>
```

## Metasploit 
The framework contains an SMTP enumeration module that allows attackers to connect to the target SMTP server and enumerate usernames using predefined wordlists.

# SMTP Enumeration Tools
# NetScanTools Pro
NetScanTools Pro's SMTP Email Generator tool tests the process of sending an email message through an SMTP server. Attackers use NetScanTools Pro for SMTP enumeration and extract al the email header parameters, including confirm/urgent flags. Attackers can also record the email session in a log file and then view the communications between
NetScanTools Pro and the SMTP server in the log file.

# smtp-user-enum
- smtp-user-enum is a tool for enumerating OS-level user accounts on Solaris via the SMTP service (sendmail).
- Enumeration si performed by inspecting the responses to VRFY, EXPN, and RCPT TO commands.

# DNS Enumeration Using Zone Transfer
- DNS zone transfer is the process of transferring a copy of the DNS zone file from the primary DNS server to a secondary DNS server.
- In DNS enumeration using zone transfer, an attacker attempts to retrieve a copy of the entire zone file for a domain from the DNS server. 
- DNS zone transfer can be performed using dig and nslookup
### dig Command
- this command retrieves al the DNS name servers of the target domain
```
	dig ns ‹target domain>
```
- Next, attackers use one of the name servers from the output of the above command to test whether the target DNS alows zone transfers.
```
	dig @<domain of name server> <target domain> axfr
```

### nslookup
nslookup command is used on Windows-based systems to query the DNS name servers and retrieve information about the target host addresses, name servers, mail exchanges, etc.
```
nslookup
set querytype=soa
certifiedhacker.com
```
The above command sets the query type to the Start of Authority (SOA) record to retrieve administrative information about the DNS zone of the target domain certifiedhacker.com. The following command is used to attempt to transfer the zone of the specified name server:
```
/ls -d <domain of nameserver>
```

### DNSRecon
Attackers use DNSRecon to check al NS records of the target domain for zone transfers. As shown in the screenshot, attackers use the following command for DNS zone transfer:
```
dnsrecon -t axfr -d ‹target domain>
```
In the above command, the - t option specifies the type of enumeration to be performed, axfr si the type of enumeration in which al NS servers are tested for a zone transfer, and the d- option specifies the target domain.

# DNS cache snooping 
DNS cache snooping is a DNS enumeration technique whereby an attacker queries the DNS server for a specific cached DNS record

 Following are the DNS cache snooping methods to snoop on a target domain
 - Non-recursive Method
```
	 dig @<IP of DNS server> <Target domain> A +norecurs
```

- Recursive Metho
```
	dig @<IP of DNS server› <Target domain> A +recurse
```
Read more: [DNS Snooping](https://www.proteansec.com/hacking/dns-cache-snooping/#:~:text=To%20snoop%20a%20DNS%20server%20we%20can%20use,in%20the%20DNS%20cache%2C%20it%20will%20be%20returned)
# DNSSEC Zone Walking
- DNSSEC zone walking is a DNS enumeration technique where an attacker attempts to obtain internal records of the DNS server if the DNS zone is not properly configured
- Attackers use tools, such as LDNS and DNSRecon, to exploit this vulnerability and obtain the network information of a target domain and further launch Internet-based attacks



