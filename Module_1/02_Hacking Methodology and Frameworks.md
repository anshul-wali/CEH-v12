# CEH Hacking Methodology (CHM) 
It defines the step-by-step process to perform ethical hacking. The CHM follows the same process as that of an attacker, and the only  differences are in its hacking goals and strategies. 
## Footprinting
Footprinting and reconnaissance constitute the preparatory phase, in which an attacker 
gathers as much information as possible about the target prior to launching an attack. 

## Scanning 
It is used to identify active hosts, open ports, and unnecessary services enabled 
on particular hosts. In this phase, the attacker uses the details gathered during 
reconnaissance to scan the network for specific information. 

## Enumeration 
Enumeration involves making active connections to a target system or subjecting it to 
direct queries. It is a method of intrusive probing through which attackers gather 
information such as network user lists, routing tables, security flaws, shared users, 
groups, applications, and banners. 

## Vulnerability Analysis 
Vulnerability assessment is the examination of the ability of a system or application, 
including its current security procedures and controls, to withstand assault. It 
recognizes, measures, and classifies security vulnerabilities in computer systems, 
networks, and communication channels. 
## System Hacking
- Gaining Access:
	- Attacker obtains access to the  operating system (OS) or applications on a computer or network. 
	- Techniques used such as password cracking and the exploitation of vulnerabilities.
- Escalating Privileges 
- Maintaining access
    - Executing applications
    - Hiding files
- Covering tracks
    - Clearing logs
      
# Cyber Kill Chain
- Reconnaissance
    - Harvesting email addresses, conference information, etc.
- Weaponization
    - Coupling exploit with backdoor into deliverable payload.
- Delivery
    - Delivering weaponized bundle to the victim via email, web, USB, etc.
- Exploitation
    - Exploiting a vulnerability to execute code on victim's system
- Installation
    - Installing malware on the asset
- Command and control (C2)
    - Command channel for remote manipulation of victim
- Action on objectives
    - Intruders accomplish their goals
# Tactics, Techniques, and Procedures (TTPs) 
Adversary behavioral identification is all about predicting attacks. It involves identifying the typical attack tactics or techniques used by an adversary to launch cyber attacks on a target network. It helps security experts in developing secure network infrastructure and adopting a variety of security techniques to prevent cyber attacks.

## Internal Recon
Once an attacker gains a foothold inside the network, they may begin enumerating other systems, hosts, processes, and programs that are running, maybe in search of another system of interest. This behavior is alarming, and security professionals should look for strange batch files, unexpected commands executed in PowerShell and bash scripts, and by using packet capture tools like Wireshark and Tcpdump.

## PowerShell
Windows PowerShell enables IT professionals to manage and control the Windows operating system and apps. An attacker can use PowerShell as a tool for data exfiltration, system exploration, and connecting to external systems. Entire harmful frameworks have been built around PowerShell, due to its ability to configure and work with networks. To identify this behavior, security experts can check PowerShell transcript logs or Windows Event logs and look for PowerShell usage by someone other than administrators.
## CLI/Terminal
An adversary can use the command-line interface to interact with the target system, view files, edit file content, connect to a remote system, and download and install malicious malware. Security professionals should analyze log files of process IDs with strange names and malicious files to determine an adversary's actions. for example, a process started from PowerShell with the execution policy bypassed should be monitored.
## Command and control server
The attackers use command and control servers to maintain communication with compromised systems via encrypted network sessions. In many cases, Command and control server traffic indicates that the attacker has gained access to the network and is planning to install additional tools. The adversary can steal data, erase data, and launch new attacks using the C&C server encrypted channel. This behavior can be detected by monitoring network traffic for outbound connection attempts and unauthorized open ports. Finding IP addresses and domains that are known to be C&C server traffic and blacklisting them is one approach to guard against the C2 server.
## DNS tunneling
The domain name system (DNS) resolves domain names into IP addresses, which are then used by browsers to load web pages. An attacker can use DNS tunneling to obfuscate malicious traffic into the legitimate traffic through common protocols that would not necessarily cause alarm. using the DNS tunneling an adversary can also communicate with the command and control server and perform data exfiltration.

Link: [What Is DNS Tunneling? - Palo Alto Networks](https://www.paloaltonetworks.com/cyberpedia/what-is-dns-tunneling)

## Data staging
Data exfiltration is the unauthorized copying or transfer of data from a computer or network. If data exfiltration is the goal after successful network penetration, the attacker uses the data staging technique to collect and combine as much data as possible. The attacker can gather sensitive information about employees and customers, as well as financial data, business techniques, and network infrastructure data. This behavior can be detected by monitoring network traffic for any malicious file transfer, file integrity monitoring, and event logs.
# Indicator of compromise (IoC)
Indicator of compromise (IoC) in computer forensics is an artifact observed on a network or in an operating system that, with high confidence, indicates a computer intrusion. Typical IoCs are virus signatures and IP addresses, MD5 hashes of malware files, or URLs or domain names of botnet command and control servers. After IoCs have been identified via a process of incident response and computer forensics, they can be used for early detection of future attack attempts using intrusion detection systems and antivirus software. 

IoC's are divided into four categories:
- Email Indicators 
- Network IoCs
- Host-Based IoCs
- Behavioral IoCs
  
Link: [Types Explained](https://www.sentinelone.com/cybersecurity-101/what-are-indicators-of-compromise-iocs-a-comprehensive-guide/)

# MITRE ATT&CK
Adversarial Tactics, Techniques, and Common Knowledge or MITRE ATT&C is a globally-accessible knowledge base of adversary tactics and techniques based on real-world observations. The ATT&CK knowledge base is used as a foundation for the development of specific threat models and methodologies in the private sector, in government, and in the cybersecurity product and service community.

Link: [MITRE ATT&CK](https://attack.mitre.org/) 

# Diamond Model of Intrusion Analysis 
!(Module_1/Img/Diamond_Model.png)
The diamond model of intrusion analysis is a model used by information security professionals to authenticate and track cyber threats.

The Diamond event consists of four basic features: 
- Adversary 
- Victim
- Capability
- Infrastructure
