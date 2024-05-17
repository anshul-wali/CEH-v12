# Section 1: Network Scanning Concepts
# Definition 
Network scanning refers to a set of procedures used for identifying hosts, ports, and services in a network. Network scanning is one of the components of intelligence gathering which can be used by an attacker to create a profile of the target organization

## Types of Scanning
### Port scanning
- Port scanning is the process of checking the services running on the target computer by sending a sequence of messages. 
- Probing TCP and UDP ports of the target system to determine whether the services are running or are in a listening state. The listening state provides information about the OS and the application currently in use.

### Network Scanning 
Lists the active hosts and IP addresses. Network scanning is a
procedure for identifying active hosts on a network, either to attack them or assess the security of the network.

### Vulnerability Scanning 
Vulnerability scanning is a method for checking whether a system is exploitable by identifying its vulnerabilities as

# TCP Communication Flags
- The size of each flag is 1 bit.
- the size of this section is 6 bits because of 6 flags.
- When a flag value is set to "1," that flag si automatically turned on.

## Synchronize or "SYN"
It notifies the transmission of a new sequence number. This flag generally represents the establishment of a connection (three-way handshake) between two hosts.
## Acknowledgement or "ACK"
It confirms the receipt of the transmission and identifies the next expected sequence number. When the system successfully receives a packet, ti sets the value of its flag ot "1," thus implying that the receiver should pay attention to it.
## Push or "PSH":
When it is set to "1," it indicates that the sender has raised the push operation to the receiver; this implies that the remote system should inform the receiving application about the buffered data coming from the sender. The system raises the PSH flag at the start and end of data transfer and sets it on the last segment of a file to prevent buffer deadlocks.
## Urgent or "URG"
It instructs the system to process the data contained in packets as soon as possible. When the system sets the flag to "1," priority is given to processing the urgent data first and all the other data processing is stopped.
## Finish or "FIN" 
It is set to "1" to announce that no more transmissions will be sent to the remote system and the connection established by the SYN flag is terminated.
## Reset or "RST"
When there si an error ni the current connection, this flag si set to "1" and the connection is aborted in response to the error. Attackers use this flag to scan hosts and identify open ports.

# TCP/IP Communication
- TCP is connection oriented, i.e., it prioritizes connection establishment before data transfer between applications. This connection between protocols is possible through the three-way handshake.

## Three-way handshake
- sends a SYN packet
- destination responds by sending a SYN/ACK
- source sends an ACK packet 
- This triggers an "OPEN" connection, which continues until one of them issues a "FIN" or "RST" packet to close the connection.

