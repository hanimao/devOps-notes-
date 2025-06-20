
Computer Network
- Connecting devices to share information and the purpose is to communicate and resource share.

1. **Local Area Network** (LAN)

ex home wifi network- covers a limited area. Allows file sharing etc between devices within a local area.

2. **Wide Area Network** (WAN)

ex Internet -  that connects devices across the globe. Allows communication and data exchange across long distances. 
connects multiple LANS

Key Networking components - Switches,Routers and Firewalls

**Switches** (**a manager for your LAN**)
- Connects multiple devices within the same network for ex computers, printers.
- The switch makes sure that data flows smoothly between devices, preventing congestion and ensuring efficient communication.

**Routers** (**Traffic cop for your network!**)
- Direct traffic between networks. It determines the best path for data to travel across networks.
For ex a router connects your home network ex your laptop to the internet. Ensures data gets to the right place whether you are browsing a website or streaming a movie.
- Connects different network ex your home network to the internet. 

Routing table - a map to make decision where to send the data.

**==Static Routing & Dynamic Routing==**

Static
- Routes are manually setup.
- Reliable but does not adapt well if there are changes or issues on the route.
- Simple but not scalable 

Dynamic
- Flexible and adapts well to change esp if theres traffic
- Uses routing protocols to find the best and these protocols help routers communicate and decide on the most efficient route.

Routing Protocols

- They automate the process of determining the best route for data to travel across the network
- Enhances network efficiency because it takes the most efficient path, less congested

Examples of Protocols 
1. OSPF (Open Shortest Path First)
- Used mainly for large organisations
- It uses link state information to make routing decisions. It considers the status of a network, the links and the cost to use them.
- Quickly recalculates routes when there are changes in the network

2. BGP(Border Gateway Protocol)
- Routes data between different autonomous systems
- Autonomous systems are large networks managed by single organisations.
- Uses a PATH vector mechanisms. It maintains the path formation that gets updated dynamically as the network topology changes
- Network admin define routing policies based on various attributes. Greater control on how traffic flows through the network. 

**Firewalls** (**A security guard for your network**)
- Monitor and control incoming and outgoing network traffic based on predetermined security rules.
- Protect networks from unauthorised access.

**IP addressing (IPv4 &IPv6)**

- Unique identifiers for devices on a network. It allows devices to locate and communicate with each other. An IP address is the identity of each host

**IPv4**
- 4 decimal numbers separated by dots. 
- Each group can range from 0 to 255

**IPv6**
- IPV6 is needed due to the rapid growth of the internet
- 128 bit address
- eight groups of four hexadecimal digits separated by colons.

Why are IP addresses important?
- They enable devices to identify and communicate each other on the network.
- Without IP addresses, devices wouldn't know where to send or receive data.

**MAC addresses (Media access control address)**

- unique identifier assigned to network interface (like a fingerprint for network devices). Each device on a network has its own unique MAC address.
- 48-bit address example; 00;1A:2B:3C:4D:5E

Why are MAC addresses important?
- Operates at the data link layer. The data link layer is responsible for node to node transfer. MAC addresses help identify devices on a local network.
- Crucial for ensuring your laptop connects to the right router and not your neighbours. 
- Essential for network communication and security. Without them, devices wouldn't be able to properly communicate with their local network. 
- Help manage and control access to a network, making sure data packets get to the right place. 

**==Ports & Protocols; TCP,UDP==**

**What are ports?**
- logical endpoints for communication
- **Think of ports as logical doors on your device and each door has a number on it and each number is for a specific type of network communication.** For ex the communication can be accessing a web browser which sends the request to the receiver and then the data comes back to the user displaying the web page.  

These ports help facilitate communication between devices. When your computer wants to send or receive data, it uses these ports to make sure data goes to the right place.
- Web traffic goes through port 80 (HTTP)
- Port 443 for HTTPs.

**What are Protocols?**
- Rules of the road for data transmission
- Define how data is formatted and transmitted across a network ex HTTP, FTP.
- Ensure devices can communicate effectively by following the same set of rules.

Without both, our network communication would be a mess. Ports ensure data gets to the right application on your device while protocols ensure that the data is understandable 

**==TCP (Transmission Control Protocol)==**

- Ensures that data sent from one device reaches another device accurately and in the correct order. ex web browsing, emails
- Its a set of rules that devices follow to communicate with each other

**Features**

1. connection oriented - before any data is sent, a connection is established between the two devices.
2. requires 'handshake' - 3 steps
3. Reliable data transfer. If any data is lost or corrupted TCP will resend it.

**Function**

1. Data is delivered in order
2. error-checking and control the flow of data to prevent congestion
3. bidirectional communication

**==UDP (User Datagram Protocol)==**

1. Sends and receive data.
2. Prior communication not required. 
3. Cons - no guarantee that the data will reach its destination 
4. connectionless
5. Fast not reliable

**Function**

1. suitable for real time apps (video streaming)
2. DNS
3. UDP uses VPN

7 Layers of the OSI Model (Open System Interconnection)

Why do we need a communication model?
 - provides a standard framework that simplifies the way devices and apps communicate over a network.
 - Applications can work independently of the network, making development more efficient. Without a model, applications must understand the underlying network and you will have diff versions of your applications. 
 - Easier to upgrade and manage network gear 
 - Innovations can happen in each layer independently without affecting the entire system. 


1. Physical 
-  Physical connection between devices, fibers etc
- Sends raw data as bits over a physical medium. Converts data into signals that can travel through wires, fiber optics. Deals with the hardware connection, cables, switches and network interface cards.
Repeater
- A client sends requests to the repeater which repeats the signals in no direction. 
Hub
- A physical device but a bit smarter than a repeater. If a client (computer) sends a requests to the hub, the hub sends data to everyone.




2. Data link - frames, ethernet, bridge
- Node (A node is a physical electronic device hooked up to a network for ex a printer, computer, router) to node data transfer and error detection is managed
- Ensures data packets are sent and received correctly between different network nodes.
- Put data packets into framed and organised

3. Network - IP, ICMP, IPsec
- Where routing and data packets are managed. Manages packet forwarding including routing through intermediate routers. It decides the best path for data to travel across diff networks ensuring it gets to the right place.
- Determines how data i sent to the recipient
- Components; IP addresses handles where packets go to and routers direct data packets along the best path cross networks.

4. Transport - TCP, UDP
- End to end connections AND data integrity is managed
- Providing reliable data transfer services to the upper layers.

5. Session
- Manage sessions between different applications like TLS, sockets.
- establishes, maintains, and terminates connections.

6. Presentation - SSL, SSH, IMAP
- Data is translated to a readable format AND where encryption is handled to ensure data security.

7. Application Layer 
- Network services are given directly to applications.
- end user layer - user interaction

TCP/IP Model

1. Application Layer
2. Transport Layer

3. Internet Layer
- logical addressing and routing data across different networks. Primary protocol is IP. IP handles the delivery of your packets from the source to destination across multiple networks 

4. Network Access Layer
- encompasses the physical and includes ethernet, wireless LAN


POV of Sender

User sends a POST request to an HTTP web page
Layer 7 (App) - Post request with JSON data to the HTTPS server. 
Why choose post request?
Because you can use the BODY header

What is DNS(domain name system)?

- DNS allows you to search things easier. Allows us humans to keep track of websites and hosts by name instead of an IP address. It is like a contacts list for your internet. 
- It is translating Domain names to IP addresses behind the scenes
- Role; Simplifies navigation on the internet. Essential for accessing websites and services

DNS components

**Nameservers**

1. Without Nameservers, DNS would not work properly. 
2. Load DNS settings and configurations
3. Can be authoritative or recursive
4. Authoritative nameservers; hold the actual DNS records. When queried, they provide the definitive answer such as the IP address for a domain name. 
5. Recursrive nameservers; DO NOT HOLD THE FINAL ANSWER! They query the other nameservers on behalf of the client to find the correct DS record.They can catch the information they retrieve to speed up future queries 

example; I want to know what name server google.com is hosted on, 

dig ns.google.com

**Zonefiles**

1. Stored inside your nameservice and they contain information about the domain
2. They answer queries about how to get to a domain. 
3. Organise DNS info in a readable format

**Records**

- A zonefile is comprised of multiple records.
- Each record contains specific information about hosts, nameservers and various other resources. 
- Components: Record names, TTL,Class,Type,Data
- The record name being the domain name being queried

1. A - maps a domain name to an IPv4 address
2. AAAA - maps a domain name to an IPv6 address
3. CNAME - Alias of one name to another. It allows you to point multiple domain names to the same IP address.
4. MX - Specifies the mail server responsible for receiving email for the domain.
5. TXT - Allows domain admin to insert any text into DNS. Commonly used for verification purposes and to hold SPF (Sender Policy Framework) data. If you want to verify that you own the domain use this.

Example
Maps domain to IPv4 address.
google.com ------216.58.204.79
The A record for google.com might map to 16.58.204.79 and is essential to direct traffic to the correct IP address. 

AAAA - IPv6 address

google.com ----- 2a00: 1450: 4009: 81d: : 200e

**How does DNS work?**

DNS resolution is the process of converting domain names to IP addresses.

1. DNS Root (Boss)
Keeps high level info on where to find the top level domains 

2. Top level Domains (Department Heads)
Has extension such as .com, .org etc. The .com is managed by verisign. Each TLD stores info about domains within the scope.

3. Authoritative Nameservers Host 1+zones for domains(Managers)
Each authoritative nameserver hosts zones for domains meaning they have the detailed DNAS records for those domains. For ex, google.com have their own DNS record stored

4. Domain (google.com)
Each domain has a zone and a zone file; a detailed list of records for that domain. Info such as IP addresses, mail servers of the domains are stored. 


Domain registrar vs DNS Hosting provider

1. Registrar
Purchase and register domains. They have a relationship with the TLD registry for various TLDs. The registrar communicates with the TlD registry to manage domain registrations. 
ex; RAF 53, CloudFlare etc.

2. DNS host provider
Operates DNS nameservers that hosts DNS zones. They allow you to manage these DNS records within these zones.

When you purchase a domain you need DNS Zone to be hosted on a DNS name server. The process varies depending on whether the DNS hosting provider is the same as the registrar .

2 cases;
If the registrar and DNS hosting provider are the same company, the dns zone is automatically created and hosted 
If its not the same, the domain on cloudflare and have your domain hosted zone in AWS. You need to provide the name server information where the DNS is already hosted. 

Debug DNS issues

1. nslookup [domain]
Queries DNS service. You can find info on DNS records for that certain domain 

2. dig [domain]
much more detailed for creating DNS service

Using /etc/hosts
using local host file -when we are developing or testing networks locally

1. It is a local file on your computer 
2. Maps domain names to IP addresses 
3. Override DNS settings for certain domains by providing an alternative IP address. 
4. When you type a domain name into your browser, it first checks the etc/hosts file and if it finds it there uses the provided IP address instead of querying the DNS servers. 

Introduction to Subnetting

- Dividing one large network into smaller more manageable sub networks.
- Organises and manages IP address 
Subnet masks
- Which part on the IP address is the network portion and which part is the host portion

CIDR notation (Classless Inter-Domain Routing)
- A method for allocating IP addresses and routing IP packets 

Format IP_address/prefix_length 
ex; 192.168.1.0/24
network address/the first 24 bits are the network part of the address and the rest for the host addresses. 

NAT (Network Address Translation)
- Converts private IP addresses that your devices at home etc to a public IP address that can be used on the internet. When the devices you at home go online they all share one public IP address
- Without NAT each of your devices would needs its own public IP address to access the internet. (limited public ip addresses)


Static NAT

- Maps a single private IP address to a single public IP address. Useful when you have a device that needs to be connected over the internet with the same IP address all the time like a web server. A computer that other people outside of your local/private network need to connect to over the internet. 

Dynamic NAT

- Maps private IP addresses to public IP addresses from a pool of available public addresses. Each time a private IP address needs to be translated, the NAT router selects an available public IP from this pool. The mapping changes each time, meaning a device could have a different public IP address for each session. 

Port Address Translation (PAT)

- Multiple devices on a local network to be mapped to a single public IP address but with a different port number for each sessions


Network troubleshooting

1. Ensure smooth operation
2. Identify and fix network problems
3. minimize downtime

Common Network issues

1. Connectivity Loss
2. Slow network performance
3. IP address conflicts 
4. DNS resolution failures 

Troubleshoot with ping, traceroute, nslookup

ping - test any connectivity between devices 
traceroute - tracks the path your data takes to reach this certain destination
nslookup - queries DNS to find an IP address associated with domain name 