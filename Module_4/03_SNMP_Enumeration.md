# SNMP Enumeration
SNMP is an application-layer protocol that runs on UDP and maintains and manages routers, hubs, and switches on an IP network. SNMP agents run on Windows and Unix networks on networking devices.

SNMP enumeration is the process of creating a list of the user's accounts and devices on a target computer using SNMP. SNMP employs two types of software components for communication: the SNMP agent and SNMP management station. The SNMP agent is located on the networking device, and the SNMP management station communicates with the agent.

# Working
GetRequest: Used by the SNMP manager to request information from an SNMP agent
• GetNextRequest: Used by the SNMP manager continuously to retrieve all the data stored in an array or table
GetResponse: Used by an SNMP agent to satisfy a request made by the SNMP manager
• SetRequest: Used by the SNMP manager to modify the value of a parameter within an SNMP agent's management information base (MIB)
• Trap: Used by an SNMP agent to inform the pre-configured SNMP manager of a certain event

# Management Information Base (MIB)
MIB is a virtual database containing a formal description of all the network objects that SNMP
manages. It is a collection of hierarchically organized information. It provides a standard
representation of the SNMP agent's information and storage. MIB elements are recognized using
object identifiers (OIDs). An OID is the numeric name given to an object and begins with the root of the MIB tree. The OID can uniquely identify the object in the MIB hierarchy.
The SNMP manager converts the OlDs into a human-readable display using the MIB as a codebook.
The major MIBs are
.as follows:
• DHCP.MIB: Monitors network traffic between DHCP servers and remote hosts
• HOSTMIB.MIB: Monitors and manages host resources
• LNMIB2.MIB: Contains object types for workstation and server services
• MIB_II.MIB: Manages TCP/IP-based Internet using a simple architecture and system
• WINS.MIB: For the Windows Internet Name Service (WINS)

# SmpWalk 
is a command-line tool that allows attackers to scan numerous SNMP nodes instantly and identify a set of variables that are available for
accessing the target network. Using this tool, attackers target the root node so that information from all the sub-nodes such as routers and switches can be fetched.

snmpwalk -v1 -c public <Target IP Address>
The above command alows attackers to view al the OlDs, variables, and other associated information.

# Enumerating SNMP using Nmap
Attackers use the smp-processes Nmap Scripting Engine (NSE) script against an SNMP remote server to retrieve information related to the hosted SNMP services.
nmap -sU -p 161 --script=snmp-processes <Target IP Address>
The above Nmap command, when executed, retrieves a list of al the running SNMP processes along with the associated ports on the target host.


# SNMP enumeration tools
# smp-check 
smp-check allows the enumeration of SNMP devices and places the output in a human-readable and user-friendly format.Its goal is to automate the process of gathering information on any device with SNMP support (Windows, Unix-like, network appliances, printers, etc.)

Syntax - snmp-check 10.10.1.22
Source: https://www.nothink.org

# SoftPerfect Network Scanner
SNC discovers  shared folders and retrieves practically any information about network devices via  WMI, SNMP, HTTP, SSH, and PowerShell

Source: https://www.softperfect.com


























