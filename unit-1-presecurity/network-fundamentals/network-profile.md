# Q1: What is your machine's IPv4 address and MAC address? (You can mask the last group of each if you prefer — e.g. 192.168.1.xxx — for privacy in your repo.)  ----192.168.xx.x   ,   0A-00-27-00-00-xx
Q2: Your IP address is a private address (it starts with 192.168, 10., or 172.16–172.31). In one sentence, what is the difference between a private IP address and a public one? Why does your home router use private addresses inside your network?              ==Public IP are unique globally while private ip is unique in a local network to limit the adresses. router conserves limited public Ipv4 adresses and hides devices from external thteats.
 # Q3: What is the difference between your IP address and your MAC address? Which one can change, and which one is (mostly) fixed to your hardware? Which one operates at which OSI layer?                                     == - IP adresses identifies devices logical network but MAC identifies the physical hardware  address uniquelly, IP adresses can change when switching networks but MAC cant. IP operates at osi layer 3  MAc operates at OSI layer 2. 
 Q4: Your subnet mask is most likely 255.255.255.0, which is written as /24 in CIDR notation.                            == 254 adresses the remaining 2 are for the broadcast adress and 1 for network adress.    If my IP is 192.168.1.37/24  , network adress is 192.168.1.0 and the broadcast is 192.168.1.255
#   Q5: What is your default gateway's IP address? Is it on the same subnet as your machine? (It should be — explain how you can tell.)                                                                            ==10.11.4.1, it is on the same subnet as my device. how can i tell? = my device's ip is 10.11.4.21 with a subnet mask of 255.255.254.0 this means the network includes all addresses from 10.11.4.0 to 10.11.5.255 because both my ip and gateway ip fall within range, they share the same local network block.
  Q6: What was the average round-trip time to your gateway versus to 1.1.1.1? Why is one much faster than the other?                                                   == gateway is is around 1 to 5 ms but the public DNS is 29 ms round trip. the gateway is faster because it is local but the 1.1.1.1 is a remote server so the the data will take long to travel to that public dns
# Q7: Now try ping -c 4 example.com (or -n 4 on Windows). It worked using a name instead of an IP address. What service made that possible?                           ==The service is DNS. 
Q8: What DNS server(s) is your machine configured to use? Is it your gateway, a public resolver (like 1.1.1.1 or 8.8.8.8), or something else?                                     ==it is my DNS 62.241.198.xxx. it belongs to my internet service provider ISP.
# Q9: What IP address(es) did example.com resolve to? Run the lookup for two more sites you use. Do any of them return multiple IP addresses? Why might a large website have more than one?                             ==172.66.147.243 and 104.21.23.154 and other IPv6 addresses. large websites use mulitple IPs to distribute heavy incoming user traffic across multiple physical servers so o single server gets overwhelmed, if one server goes offline the traffic automatically routes to the working ip addresses so the site stays up.
 Q10: A security thought: DNS lookups are usually sent in cleartext. If someone could watch your network traffic, what could they learn about you just from your DNS queries — even if all the websites you visit use HTTPS?                                    ==they can see the exact domain names of every website i attempt to visit, but HTTPS completely hides my passwords and the specific pages you click inside the website but plain text DNS requests still leak your complete browsing history, web activities habits and intrests to anyone sniffing the network path.
# Q11: How many hops did it take to reach example.com? What is the first hop (hint: you've seen it already in this exercise)?                                           ==it took 8 hops to succefully reach the destination , First hop is 10.11.4.1 which is my default gateway.
Q12: Some hops show * * * with no response. Does that mean the connection is broken? Explain what's most likely happening.                 == the connection did not break beacuse it reached the destination at 8 hops. Intermediate routers on the internet which are configured which like prioritize routing regular data traffic, these spescific routers are configured to block ICMP time exceeded requests which result into * * *
# Q13: List the ports your machine is listening on. For each, note whether it's listening on 127.0.0.1/localhost (only reachable from your own machine) or on 0.0.0.0/* (reachable from the network).                                                                                                                            ====Network-facing (0.0.0.0 / [::] / Local IP)       Port 135 (0.0.0.0:135, [::]:135)       Port 445 (0.0.0.0:445, [::]:445)           Port 5040 (0.0.0.0:5040)           Port 7680 (0.0.0.0:7680, [::]:7680)      Ports 49664, 49665, 49666, 49667, 49669, 49684 (0.0.0.0 and [::])     Port 139 (Bound specifically to network-facing interfaces 10.11.4.21:139 and 192.168.56.1:139)     Localhost only (127.0.0.1 / [::1]):      Port 5354 (127.0.0.1:5354)      Port 6800 (127.0.0.1:6800)       Ports 12025, 12110, 12119, 12143, 12423, 12465, 12563, 12993, 12995 (127.0.0.1 and [::1])     Ports 27015, 27275 (127.0.0.1 and [::1])     Ports 44566 (127.0.0.1)Ports 42050, 49681 ([::1])
Q14: Look up what two of these ports are commonly used for (a quick web search for "port 22" or "port 445" is fine). Why does it matter, from a security standpoint, whether a port is listening on localhost only versus on all interfaces?                                                                                   ==port 135 (RPC Endpoint Mapper): Used by windows for remote procedure calls to locate services on the systems, Port 445 (SMD) used for windows file sharing and printing over network. why interface matters? localhost ( 127.0.0.1) : completely safe from external attacks , all interfaces (0.0.0.0): Anyone on your local wi-fi network can attempt to connect to this port
# Q15: A security thought: an attacker scanning your machine sees only the ports listening on 0.0.0.0 (network-facing), not the localhost-only ones. Based on your output, is your machine exposing more or fewer network-facing services than you expected?                                                                                       ==My machine is exposing more network-facing services than expected.

# 
# Network Profile - Macaanow  
## Identity
- IPv4 address: 172.22.197.27 
- Subnet mask / CIDR: 255.255.255.0 (/24)
- MAC address: D4-D8-53-CE-F6-58
- Network address: 172.22.197.0
- Broadcast address: 172.22.197.255
- ## Gateway and reachability
- Default gateway: 172.22.197.194
- Ping to gateway (avg): 2 ms
-  )Ping to 1.1.1.1 (avg): 87 ms
-  ## DNS
-  Configured DNS server(s): 172.22.197.194
-  example.com resolves to: 104.20.23.154
-  ## Path to the internet
-  Hops to example.com: 8 hops
-  First hop: 172.22.197.194
-  ## Listening ports
| Port | Protocol | Interface (localhost / all) | Common use |
|135   |TCP       | all (0.0.0.0)               |Microsoft RPC (Remote Procedure Call)|
|445   |TCP       |all (0.0.0.0)                |SMB (Server Message Block)/ File Sharing |
| 5357 |TCP       | all (0.0.0.0)               | eb Services Dynamic Discovery (WS-Discovery)  |
|6800  |TCP       | localhost (127.0.0.1)       |Often used by BitTorrent clients / Aria2 download manager   |




# 


# What surprised me most about my network profile was the routing path during the trace route command. Even though example.com is a standard website, my traffic skipped directly from my default gateway out into external systems like twelve99.net within just a few hops, maintaining a stable latency until it hit Cloudflare's server.Looking closely at my open listening ports, I noticed that port 445 (SMB) is currently listening on all interfaces (0.0.0.0). Since SMB is frequently targeted by network exploits and malware for lateral movement, this is a port I would want to closely investigate or restrict to ensure it is not exposed to public or untrusted networks



