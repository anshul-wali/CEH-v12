#  Section 6: Email Footprinting 

# Email Tracking
- Email tracking si used to monitor the delivery of emails to an intended recipient
- Attackers track emails to gather information about a target recipient, such as IP addresses,
   geolocation, browser, Device Type and OS details, to build a hacking strategy and perform social engineering and other attacks.


## Collecting Information from Email Head
- Sender's mail server
- Date and time of receipt by the originator's email servers
- Authentication system used by the sender's mail server
- Data and time of sending the message
- A unique number assigned by mx.google.com to identify the message
- Sender's full name
- Sender's IP address and address from which the message was sent


## Infoga
 Info Infoga is a tool used for gathering email account information (IP, hostname, country, etc.)
 from different public sources (search engines, pgp key servers, and Shodan), and it checks fi an
 email was leaked using the haveibeenpwned.com API. For example, the command  below will retrieve 
 all the publicly available email addresses related to the domain microsoft.com along with email account information.
```
	python infoga.py --domain microsoft.com --source all —-breach -v 2 --report ../microsoft.txt
```

## eMailTrackerPro
 As shown in the screenshot, attackers use eMailTrackerPro to analyze email headers and extract information
 such as the sender's geographical location, IP address, and so on. It allows an attacker to review the traces later by saving past traces
  
	 Source: http://www.emailtrackerpro.com 
