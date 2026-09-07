[[Cloud Security]]
[[Cybersecurity Fundamentals]]
# Common Networking Devices

## Routers
- Physical or virtual devices that send data packets to destination network along a path
- A wireless router combines functionality of both a router and an Access Point (AP)
## Default Gateway
- It is a node in a computer network using IP suite that serves as a forwarding host (router) to other networks when no other route specification matches the destination IP of a packet
## Access Point
- It is a network device that connects to a router or wired network and transmits a WI-FI signal so that wireless devices can connect to a wireless network 
## Hub
- A hub (concentrator) is a network device that connects multiple devices on a LAN network
- Network traffic that is sent to a hub is transmitted to all of the ports on the hub (A bad behavior)
## Switch
- It is an intelligent hub that uses physical addresses to forward data packets 
- It forwards data packets only to the corresponding port to the destination device
- This method is known as micro segmentation, it creates separate network segments and increases the data transmission rate
---
# Routed and Routing protocols
## Routed protocols
- Routed protocols such as IP, manage packets with routing information that enables those packets to be transported across networks using routing protocols
## Routing protocols
- They are defined at the network layer of the OSI model and specify how routers communicate with one another on a network
- They can be classified into:-
  - Static routing
  - Dynamic routing
## Static routing
- It requires routes to be created and uploaded manually on a router
- Traffic can't be automatically rerouted if the specified route is down
- It has low bandwidth requirements and has built-in security
## Dynamic routing
- It can automatically learn new routes and determine the best route to a destination
- The routing table is updated periodically with current routing information
- It can be classified into:-
### Distance Vector
- It makes routing decisions based on the distance (hop count) and vector (the exit router interface)
- It periodically informs its peers of the topology changes
- Convergence( The time required for the routers in a network to update their routing tables with current information ) is bad in distance vector
- Example: RIP( Routing Information Protocol )
### Link State
- A link protocol requires every router to calculate and maintain a complete map, or a routing table of the entire network
- They are compute intensive but very efficient at calculating routes
- It considers factors such as link speed, delay, load, reliability and cost
- Rapid convergence
- Example: OSPF ( Open Shortest Path First )
### Path Vector
- Similar to distance vector but without scalability issues associated with limited hop counts 
- Each routing table entry contains path information that gets dynamically updated
- Example: BGP ( Border Gateway Protocol) is the core protocol used in ISPs ( Internet Service Providers) and NSPs ( Network Service Providers) and on very large private IP networks
---
# Networks and Topologies
## LANs
- Common networking devices used are hubs, switches, bridges, repeaters and wireless APs
- Most common topologies are star and mesh topology
## WANs
- Common networking devices used are access servers, firewalls, modems, routers, VPN gateways and WAN switches
- Traditional WANs rely on physical routers to connect remote or branch users to applications hosted on data centers
- Each router has a data plane to hold information and a control pane to control the flow of data 
### SD WAN
- A software defined WAN ( SD WAN) separates the control and management processes from the underlying networking hardware, making them available as software that can be easily configured and deployed 
- They are simple, have improved performance and reduced costs
---
# Domain Name System
- DNS is a distributed, hierarchical internet database that maps " Fully Qualified Domain Names ( FQDNs) " to IP addresses
## Root Name Server
- Thirteen root name servers ( 13 networks comprising of 100s of root name servers ) are configured worldwide names from a.root-servers.net to m.root-servers.net
## DNS record types
- A or AAAA:  A ( IPv4 ) or AAAA ( IPv6 ) address maps a domain or subdomain to an IP address or multiple IP addresses
- CNAME: Canonical name maps a domain or subdomain to another hostname
- MX: Mail Exchanger specifies the hostname(s) of email servers for a domain
- PTR: Pointer points to a CNAME and is commonly used for reverse DNS lookups that map an IP address to a host in a domain or subdomain
- SOA: Start of Authority specifies authoritative information about a DNS zone such as primary name server, name server, email address of the domain admin and domain serial number
- NS: The Name Server record specifies an authoritative name server for a given host
- TXT: Text stores text based information
## Internet of Things
### IOT Connectivity Technologies
#### Cellular
- 2G/2.5G
- 3G: These devices use either Wideband Cod Division Multiple Access ( WCDMA ) or Evolved High Speed Packet Access ( HSPA+ )
- 4G/Long Term Evolution ( LTE ): enable real time IoT use cases such as autonomous vehicles
- 5G: Better version of 4G with more scalability, less latency and higher speeds
#### Satellite
- C-Band: Operates in the 4 to 8 GHz range. Used in some wi-fi devices and cordless phones and weather radar systems and surveillance systems
- L-Band: Operates in the range of 1 to 2 GHz range. Used for radars, GPSs, radio and telecommunication applications
#### Short-Range Wireless
- Adaptive Network Technology + ( ANT + ) Proprietary multicast wireless sensor network technology primarily used in personal wearables
- IPv6 over Low Power Wireless Personal Area Networks ( 6LoWPANs ): Allows IPv6 traffic to be carried over low power wireless mesh networks. It is designed for nodes and applications requiring wireless internet connectivity at low data rates in small form factors such as smart light bulbs
- Bluetooth/ Bluetooth Low Energy ( BLE ): Low power short range communication technology designed for point to point communication between wireless devices in a hub and spoke technology 
- Wi-Fi/ 802.1: IEEE defines the 802 LAN protocol standards. 802.11 is the set of standards used for Wi-Fi network typically operating between 2.4GHz and 5GHz frequency bands. Examples: 802.11n (Wi-Fi 4), 802.11ac (Wi-Fi 5), 802.11ax (Wi-Fi 6)
- Z-Wave: A low energy wireless mesh network protocol used for home automation such as smart devices like windows, doors, locks, fans, bulbs, etcetera
- Zigbee/802.14: Low cost, low power wireless mesh network protocol based on IEEE 802.15.4 standard. Used in low power networking devices like smart home products
#### LP-WAN and WWAN
- Narrowband IoT ( NB-IoT ): Provides low cost, long battery life and high connection density for indoor applications
- LoRa: It is Long Range wireless technology used primarily in Low Power Wide Area (LPWA) connectivity 
#### IDoT
- It refers to identity and access management for IoT
--- 
# IP Addressing
- Data packets are routed over a TCP/IP network using IP addressing information
- IPv4 uses a 32 bit logical IP address
## Loopback address
- Loopback network addresses are used for testing and troubleshooting purposes
- The address range is 127.0.0.1 to 127.255.255.255
- Packets sent to a loopback (localhost) address such as 127.0.0.1 are immediately routed back to the source host without exiting the source host
## Private address
- Private addresses are reserved for use in private networks and are not routable on the internet
- The range is : 
  10.0.0.0 - 10.255.255.255 ( Class A )
  172.16.0.0 - 172.31.255.255 ( Class B )
  192.168.0.0 - 192.168.255.255 ( Class C )  
## Subnet Mask
- A subnet mask is a number that hides the network portion of an ipv4 address and only shows the host portion
- The network portion is represented with 1 and host portion is represented with 0
- Default subnet mask for :
   Class A: 255.0.0.0
   Class B: 255.255.0.0
   Class C: 255.255.255.0
## IPv6 structure
- They use a 128 bit hexadecimal address space providing about 3.4 x 10^38 ( 340 hundred undecillion) unique IP addresses
- They consist of 32 hexadecimal numbers grouped into 8 hextets of 4 hexadecimal digits ( each hexadecimal digit can be represented as 4 bits )
- Example: 2001:0db8:0000:0000:0008:0800:200c:417a
- The first half of an IPv6 address is called the upper part and it represents the network part of the address
- The last half is known as bottom part and represents the node or interface part of the address
### Rules for simplifying IPv6 addresses
- Leading zeroes in an individual hextet can be omitted but each hextet must have at least one hexadecimal digit. Example: ( 2001:0db8:0000:0000:0008:0800:200c:417a ) can be written as ( 2001:db8:0:0:8:800:200c:417a )
- Two colons can be used to represent one or more groups of 16 bits of zeroes and leading or trailing zeroes. The two colons ( :: ) can only appear once in an IP address. 
  Example: 2001:0db8:0000:0000:0008:0800:200c:417a can be written as 2001:db8::8:800:200c:417a
  In mixed IPv6 and IPv4 environments, the form x:x:x:x:x:x:d.d.d.d can be used in which x represents the six high order 16 bit hextets and d represents the 4 low order 8 bit octets of IPv4. Example: 0db8:0:0:0:0:FFFF:129.144.52.38
## NAT ( Network Address Translation )
- It is a method of mapping an IP address space into another by modifying network address information in the IP header of packets while they are in transit 
---
# Subnetting
- A technique used to divide large network into smaller, multiple subnetworks by segmenting an IP address into two parts: network and host portion
- Class A use a default 8 bit subnet mask ( 255.0.0.0 ) which allow around 16 million nodes ( 2^24 -2 )
- Class B use 16 bit subnet mask ( 255.255.0.0 ) and can allow around 65000 nodes
- Class C network uses a 24 bit subnet mask ( 255.255.255.0 ) allowing only 254 nodes
## CIDR ( Classless Inter-Domain Routing )
- Method for allocating IP addresses and IP routing that replaces classful IP addressing ( Class A, B and C )
- CIDR allocates address space on any address bit boundary ( variable length subnet masking )
- Example: a 23 bit subnet mask instead of a fixed 24 bit
## Supernetting
- CIDR is used to reduce the size of routing tables on internet routers by aggregating multiple contiguous network prefixes and it also helps slow down the depletion of public IPv4 addresses
- Example: 192.168.2.0/25
---
# TCP/IP OSI Model
## TCP/IP protocol stack
- The TCP stack places the block of data into an output buffer on the server and determines the max segment size of each TCP block permitted by the server OS, then divides the data blocks into appropriately sized segments, adds a TCP header and sends them to the IP stack on the server
- The IP stacks adds source and destination address and notifies the server OS that it is ready to be sent
- The IP packet is then sent to network adapter which converts it into bits and sends it across the network
---
# Malware and Anti-Malware
## Approaches malware detection and response
### Signature based
- Oldest and most common approach for detecting and identifying malware on endpoints
- Malware samples are continuously collected and matching signature files are created and are used security updates
- Deployment requires installation of an engine that works at the kernel level
- It scans the hard drive and memory based on predefined schedule and in real time when a file is accessed
- If a known malware signature is found then it takes one of three actions:
   1) Quarantine: Isolating the infected file
   2) Alert: Alert the user or admin
   3) Delete: Removed the infected file
- It is ineffective against zero-day attacks, malware variations ( multiple types of malware variations, thousands every day ), advanced malware ( uses metamorphism and polymorphism to circumvent signature based detection )
### Container based endpoint protection
- It wraps a protective virtual barrier around vulnerable processes while they are running
- If an infected process is detected then it is shut down
- It requires high computing resources and knowledge about how protected software interacts with other software
### Application Allow Listing
- Maintaining a list of applications that are authorized and not allowing unknown applications to run
- Modern trends such as cloud computing, consumerization, Bring Your Own Device ( BYOD ), Bring your Own Access ( BYOA ) make it difficult to implement application allow listing method
- After an application is added in the list, it is permitted to run even if it is compromised ( So the lists can be exploited to have control over the system )
### Anomaly Based Detection
- Detecting patterns in datasets that do not conform to established normal behavior ( behavior based )
- Uses mathematical algorithms to detect unusual activity on endpoint known as Heuristic-based anomaly detection solution ( port scans and host sweeps )
---
# Golden Image
- It ensures consistent configuration of devices across the organization. It includes:
  1) Disabling or removing inessential OS features ( Hardening )
  2) Installing current security updates
  3) Installing core applications
- Organizations deploy several security products like firewalls, Host-Based Intrusion Prevention Systems ( HIPSs ), Mobile Device Management ( MDM ), Mobile Application Management ( MAM ), Data Loss Prevention ( DLP ) and antivirus software
---
# Firewalls and HIPS
## Firewall Types
### Network Firewalls
- Traditional port based
- Bad against threats originated from within the network
### Host Based/Personal Firewalls
- Common on laptops and desktops
- Operate on layer 7 ( Application layer ) of the OSI model
- Blocks traffic based on security policy
- Can control outbound traffic and prevent malware from spreading to other endpoints
### OS Firewalls
- Windows firewall, Netfilter or iptables ( on linux )
## HIPS
- It can be either signature or anomaly based
- Causes performance degradation on endpoints
---
# Mobile Device Management
- Provides centralized management and security for mobile devices
- Various features are:
  1) Data Loss Prevention: Restrict what type of data can be stored on or transmitted from the device
  2) Policy enforcement: Enforce security policies involving passcodes, encryption, lock-down security settings, jailbreaking ( removing s/w restrictions imposed by apple to install unauthorized applications or OS) or rooting ( removing s/w restrictions imposed by android to install unauthorized applications or OS )
  3) Malware Protection: Detect and prevent breaches from mobile malware
  4) Software Distribution: Remotely install software, including patches and updates over cellular or wi-fi network
  5) Remote erase/wipe: Securely and remotely delete the complete contents of a lost or stolen device
  6) Geofencing and location services: Restrict specific functionality in the device based on its location
---
# Server Management
- Server and system administration
- Identity and Access Management ( IAM )
- Directory Services: Database that contains information about users, resources and services in a network. It includes ...
  1) Active Directory: A centralized directory developed by windows networks to provide authentication and authorization of users and network resources. It uses Lightweight Directory Access Protocol ( LDAP ), kerberos and DNS
  2) Open LDAP: Open source, IP based client-server protocol that provides access and manages directory information in TCP/IP networks
- Vulnerabilities and patch management
- Configuration Management
---
# Legacy Firewalls
- a firewall is a hardware or software platform that controls the flow of traffic between a trusted network and an untrusted network ( internet )
## Packet Filtering Firewalls
- First generation packet filtering firewalls
- Also called port based firewalls
- Operate up to layer 4 ( transport layer ) of the OSI model and inspect individual packet headers to determine source and destination IP, protocol and port number
- It matches the information with the pre assigned rules
- They have no information about the context or session of the packet that are inspected
## Stateful Packet Inspection Firewall
- Second generation
- Also known as dynamic packet filtering firewall
- Operate up to layer 4
- Same as port based firewalls except it maintains state information about the sessions established between the hosts on the two networks
## Application Firewalls
- Third generation
- Also known as application based gateways, proxy based firewalls and reverse proxy firewalls
- Operate up to layer 7 ( Application layer )
- Requests are sent from the originating host to a proxy server which analyzes contents of the data packet, if permitted it sends a copy of the original data to the destination host
- Can block specified content, malware, exploits, websites, etcetera
# Intrusion Detection and Prevention
## Knowledge Based Systems
- Uses a database of known vulnerabilities and attack profiles to identify intrusion attempts
- Lower false alarm rates
- Must be continually updated
## Behavior Based Systems
- Uses a baseline of normal network activity to identify unusual patterns or levels of network activity that might indicate an intrusion attempt
- Better at detecting new attacks against unknown vulnerabilities
- Higher false positive rates
## IDS
- Considered a passive system
- Monitors and analyzes network activity
- Sends alerts about potential attacks on the network
- Doesn't perform any preventive actions to stop an attack
## IPS
- Considered an active system
- Performs all functions of an IDS
- Automatically blocks or drops suspicious pattern matching activity on the network in real time
- Must be placed inline along a network boundary ( susceptible to attacks )
- Can trigger false alarms
- Can be used to deploy DOS attack by flooding the IPS
# VPN ( Virtual Private Network)
- A VPN creates a secure, encrypted connection/tunnel across the internet between two endpoints
## Composition of VPNs
- Layer 2 Tunneling protocol ( L2TP ): It is supported by most OS ( including mobile devices ). It provides no encryption by itself but it is considered secure when paired with IPsec
- Secure Socket Tunneling Protocol ( SSTP ): Created by Microsoft for transporting PPP or L2TP traffic through an SSL 3.0 channel 
- OpenVPN: Highly secure open source VPN implementation that uses SSL/TLS encryption for key exchange. It uses up to 256 bit encryption and can run over TCP or UDP
- Microsoft Point to Point Encryption ( MPPE ): It encrypts data in PPP based dial up connections and PPTP VPN connections. It uses RSA RC4 encryption algorithm to provide data confidentiality and supports 40 bit and 128 bit session keys
## Point-to-Point Tunneling Protocol ( PPTP )
- PPTP is a basic VPN protocol that uses TCP port 1723 to establish communication with VPN peer. 
- It then creates a Generic Routing Encapsulation ( GRE ) tunnel that transports encapsulated Point-to-Point Protocol ( PPP ) packets between the VPN peers
- It is easy to set up and fast but it is the least secure VPN protocol so it's not much used
- It is commonly used with Password Authentication Protocol ( PAP ), Challenge Handshake Authentication Protocol ( CHAP )
- Extensible Authentication Protocol Transport Layer Security ( EAP - TLS ) is a more secure authentication protocol for PPTP however it requires a public key infrastructure ( PKI ) and hence is difficult to set up
## Internet Protocol Security ( IPsec )
- A secure communications protocol that authenticates and encrypts IP packets in a communication session
- It requires a compatible VPN client software to be installed on the endpoint device
- A group password or key is required for configuration
- An IPsec VPN can be used to force all of the user's internet traffic back through an organization's firewall, it provides optimal protection with enterprise grade security
### Security Association ( SA )
- It defines how two or more entities use IPsec to securely communicate over the network
- A single Internet Key Exchange ( IKE ) SA is established between communicating entities to initiate the IPsec VPN tunnel
## Secure Sockets Layer ( SSL )
- It is an asymmetric/symmetric protocol that secures communication sessions
- It has now been superseded by TLS
- SSL VPN technology is the standard method of connecting remote endpoint devices back to the enterprise network
---
# Data Loss Prevention ( DLP )
- DLP solutions inspect data that is leaving or egressing a network such as data that is sent via email and/or file transfer
- It prevents sensitive data ( based on policies ) from leaving the network
- It prevents sensitive data from being transmitted outside the network like Personal Identifiable Information ( PII ), classified materials ( military or national security ), intellectual property, trade secrets, etcetera
- A robust DLP solution can detect data patterns even if the data is encrypted
---
# Unified Threat Management ( UTM )
- UTM combines multiple cybersecurity functions into one appliance
- It sequentially executes these cybersecurity functions to examine traffic which adds to network traffic latency