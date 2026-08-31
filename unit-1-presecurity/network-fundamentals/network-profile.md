Q1 192.168.xx.x   ,   0A-00-27-00-00-xx
Q2 =Public IP are unique globally while private ip is unique in a local network. router conserves limited public Ipv4 adresses and hides devices from external thteats.
 Q3 - IP adresses identifies devices network but MAC identifies the physical hardware  address , IP adresses can change when switching networks but MAC cant. IP operates at osi layer 3  MAC operates at OSI layer 2. 
 Q4: 254 adresses the remaining 2 are for the broadcast adress and 1 for network adress.     my IP is 192.168.1.37/24  , network adress is 192.168.1.0 and the broadcast is 192.168.1.255
 Q5: =10.11.4.1, it is on the same subnet as my device. my  ip is 10.11.4.21 with a subnet mask of 255.255.254.0 the network includes all addresses from 10.11.4.0 to 10.11.5.255 
 Q6: gateway is is around 1 to 5 ms but the public DNS is 29 ms round trip. the gateway is faster because it is local but the 1.1.1.1 is a remote server so the the data will take long to travel to that public dns
 Q7:    =The service is DNS. 
Q8:  =it is my DNS 62.241.198.xxx. it belongs to my internet service provider.
 Q9: =172.66.147.243 and 104.21.23.154 . large websites use mulitple IPs to help manage heavy traffic.
 Q10: =they can see the exact domain names of every website i go to, but HTTPS  hides my passwords and the pages you click inside the website 
 Q11:  =it took 8 hops to succefully reach the destination , First hop is 10.11.4.1 which is my default gateway.
Q12: = the connection did not break beacuse it reached the end at 8 hops. the routers just blocks ICMP time exceeded requests so it shows * * * 
Q13: ==Network-facing (0.0.0.0 / [::] / Local IP)       Port 135 (0.0.0.0:135, [::]:135)       Port 445 (0.0.0.0:445, [::]:445)           Port 5040 (0.0.0.0:5040)           Port 7680 (0.0.0.0:7680, [::]:7680)      Ports 49664, 49665, 49666, 49667, 49669, 49684 (0.0.0.0 and [::])     Port 139 (Bound specifically to network-facing interfaces 10.11.4.21:139 and 192.168.56.1:139)     Localhost only (127.0.0.1 / [::1]):      Port 5354 (127.0.0.1:5354)      Port 6800 (127.0.0.1:6800)       Ports 12025, 12110, 12119, 12143, 12423, 12465, 12563, 12993, 12995 (127.0.0.1 and [::1])     Ports 27015, 27275 (127.0.0.1 and [::1])     Ports 44566 (127.0.0.1)Ports 42050, 49681 ([::1])
Q14: =port 135 (RPC Endpoint Mapper): Used by windows for remote procedure calls to locate services on the systems, Port 445 (SMD) used for windows file sharing and printing over network.  localhost ( 127.0.0.1) : completely safe from external attacks , all interfaces (0.0.0.0) Anyone on your local wi-fi network can attempt to connect to this port
Q15: =My machine is exposing more network-facing services than expected.

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
|Port | Protocol | Interface (localhost / all) | Common use |
|-----|-----------|----------------------------|------------|
|135   |TCP       | all (0.0.0.0)               |Microsoft RPC (Remote Procedure Call)|
|445   |TCP       |all (0.0.0.0)                |SMB (Server Message Block)/ File Sharing |
| 5357 |TCP       | all (0.0.0.0)               | eb Services Dynamic Discovery (WS-Discovery)  |
|6800  |TCP       | localhost (127.0.0.1)       |Often used by BitTorrent clients / Aria2 download manager   |




#


# What surprised me most about my network profile was the routing path during the trace route command. Even though example.com is a standard website, my traffic skipped directly from my default gateway out into external systems , I also noticed that port 445 (SMB) is currently listening on all interfaces (0.0.0.0). Since SMB is frequently targeted by network exploits and malware for  movement, this is a port I would want to restrict to ensure it is not exposed to public or untrusted networks



