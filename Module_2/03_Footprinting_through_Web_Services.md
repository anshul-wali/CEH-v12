# Section 3: Footprinting through Web Services

# Finding Company Domains

## Top Level Domain:
A company's top-level domains (TLDs) and sub-domains can provide a large amount of 
useful information to an attacker. It may contain information such as organizational history,
services and products, and contact information. The target organization's external URL can be 
located with the help of search engines such as Google and Bing.

# Tools to Search Company's Sub-domains
- netcraft: attackers can use Netcraft to obtain al the sub- domains related to the target domain.
   Link:(https://www.netcraft.com/)
- sublister: Sublist3r is a Python script designed to enumerate the subdomains of websites using OSINT. It enables you to enumerate subdomains across multiple sources at once.
- Pentest-Tools Find Subdomains:Pentest-Tools Find Subdomains is an online tool used for discovering subdomains and their IP addresses, including network information and their HTTP servers..

# people search 
## spokeo
Attackers can use the Spokeo people search online service to search for people belonging to the target organization. Using this service, attackers obtain information such as phone numbers, email addresses, address history, age, date of birth, family members, social profiles, and court records.

## theHarvester
Attackers use this tool to perform enumeration on the Linkedin social networking site to find employees of the target company along with their job titles.

```
theHarvester -d microsoft -1 200 -b linkedin
```
-d specifies the domain or company name to search, - 1 specifies the number of results to be retrieved, and b- specifies the data source as Linkedin

# the dark web
- At tackers use de ep and dark web searching tools, such as Tor Browser and ExoneraTor, to gather confidential information
about the target, including credit card details, passport information, identification card details, medical records, social media accounts, Social Security Numbers (SSNs), etc.

## Tor Browser
Tor, short for The Onion Router, is free and open-source software for enabling anonymous communication. It directs Internet traffic through a free, worldwide,
volunteer overlay network, consisting of more than seven thousand relays, to conceal a user's location and usage from anyone performing network surveillance or
traffic analysis.
Links: [](https://en.wikipedia.org/wiki/Tor_(network))

# Determining the Operating System
The technique of obtaining information about the target network operating system is called OS fingerprinting.

- Netcraft
- shodan
- censys 

# Competitive Intelligence Gathering

Competitive intelligence gathering is the process of identifying, gathering, analyzing, verifying, and using information about your competitors from resources, such as the Internet

# Other Techniques
- Geographical Location
  - Google Earth for location.
  - Google finance for market value of a company's shares, company profile, competitor details, stock exchange rates
  - **Business profile** sites such as opencorporates, Crunchbase, and corporationwiki to gather important information about the target organizations,
    such as their location, addresses, contact information (such as phone numbers, email addresses), employee database, department names, type of service provided, and type of industry.
  - Recon-ng to discover public source-code repositories.
