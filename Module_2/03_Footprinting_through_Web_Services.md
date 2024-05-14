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
  - **Business profile** sites such as opencorporates, Crunchbase, and corporationwiki to gather important information about the target organizations, such as their location, addresses, contact information (such as phone numbers, email addresses), employee database, department names, type of service provided, and type of industry.
  - Recon-ng to discover public source-code repositories.


--------------------------

# Section 4 : Footprinting through Social Networking Sites
- Attackers use social engineering tricks to gather sensitive information from social networking website
- Attackers create a fake profile and then use the false identity to lure employees into revealing their sensitive information
- Attackers collect information about the employees' interests and tricks them into revealing more information

# BuzzSumo
BuzzSumo's advanced social search engine finds the most shared content for a topic, author, or domain. It shows the shared activity across al the major social networks including Twitter, Facebook, Linkedin, Google Plus, and Pinterest.
Link:https://buzzsumo.com

# Followerwonk
Followerwonk helps you explore and grow your social graph: Dig deeper into Twitter analytics: Who are your followers? Where are they located? When do they tweet?
Link:https://followerwonk.com

# Gephi
Attackers use Gephi to explore and understand graphs, create hypotheses, and discover hidden patterns between social networking connection
Link:https://gephi.org](https://gephi.org/)

# Sherlock
This tool helps the attacker locate the target user on various social networking sites, along with the complete URL

# Social Searcher
Attackers use this tool to track a target user on various social
networking sites and obtain information such as complete URLs to their profiles, their postings, and other personal information
Source: https://www.social-searcher.com

---------------------------------------------------

# Section 5 : Website footprinting
# Burp Suite
Burp Suite is an integrated platform/graphical tool for performing security testing of web applications.
Website footprinting
- Examining HTML source code 
- Examining cookies.

Link: [https://portswigger.net/burp

# Web Spiders
A Web crawler, sometimes called a spider or spiderbot and often shortened to crawler, is an Internet bot that systematically browses the World Wide Web and that is typically operated by search engines for the purpose of Web indexing (web spidering).

Web spidering tools such as Web Data Extractor, ParseHub, and SpiderFoot can collect sensitive information from the target website.

Links: [https://en.wikipedia.org/wiki/Web_crawler](https://en.wikipedia.org/wiki/Web_crawler)

## User-Directed Spidering
User walks through the application and uses a spider to collect and analyze findings

Tools: Burp Suite and WebScarab

## Web Data Extractor 
 It extracts targeted contact data (email, phone, and fax) from the website, extracts the URL and meta tags (title, description, keyword) for website promotion, searches directory creation, performs web research, and so on.

# Mirroring Entire Website
Website mirroring is the process of creating a replica or clone of the original website. Tools used are HTTrack Web Site Copier and Cyotek WebCopy
## HTTrack Web Site Copier 
HTTrack is an offline browser utility. It downloads a website from the Internet to a local directory and recursively builds al the directories including HTML, images, and other files from the web server on another computer

# Extracting Information from archive.org
Archive is an Internet Archive Wayback Machine that explores archived versions of websites. Such exploration allows an attacker to gather information on an organization's web pages since
its creation. 
Website: https://archive.org

# Other Techniques
- Extracting Website Link
	- **Octoparse**
	 Octoparse offers automatic data extraction, as it quickly scrapes web data without coding and turns web pages into structured data.
	 Source: https://www.octoparse.com
- Gathering the Wordlist from the Target Websit
	- The words available on the target website may reveal critical information that helps attackers to perform further exploitation.
	- An attacker uses the CeWL tool to gather a list of words from the target website and perform a brute-force attack on the email addresses gathered earlier.
```
	cewl www.certifiedhacker.co
```
- Metadata Extraction Tool
	- **ExifTool** 
	 ExifTool is a free and open-source software program for reading, writing, and manipulating image, audio, video, and PDF metadata. It is platform independent, available as both a Perl library (Image::ExifTool) and command-line application.
	 Links: [https://exiftool.org](https://exiftool.org/).
- Web Updates Monitoring Tool
	- **WebSite-Watcher**
	 WebSite-Watcher helps to track websites for updates and automatic
	 changes. When an update or change occurs, WebSite-Watcher automatically detects and saves the last two versions onto your disk.
	 Source: https://www.aignes.com
- Monitoring Web Pages for Updates and Changes
- Monitoring Website Traffic of the Target Company
