# Section 9: Network Footprinting

# Finding Network Range
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
