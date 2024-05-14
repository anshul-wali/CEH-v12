# Section 5 : Website footprinting
# Burp Suite
Burp Suite is an integrated platform/graphical tool for performing security testing of web applications.
Website footprinting
- Examining HTML source code 
- Examining cookies.

Link: [](https://portswigger.net/burp)

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
