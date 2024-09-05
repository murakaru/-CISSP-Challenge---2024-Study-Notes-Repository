# Communication and Network Securtiy 


Chapter 11: Secure Network Architecture and components 
Chapter 12: 

## Chapter 11

What is a protocol? Set of rules that define communication and how data is transmitted over a medium
What is OSI model?
It is an abstract or theoretical model that establishes a communication standard for all computer systems.
What are the layers of the OSI model? Application, presentation, session, transport, network,data link, physical

Explain the encapsulation and deencapsulation process
Encapsulation is addirtion of header and footers to the data received from the top layer( application to physical)
Deencapsulation : The stripping away of the headers and footers frm the data (from physical to application) 


Explaination: Application layer receives data from the SW, It encapsulates this data by adding a header.This continues until the 
physcial layer. The physical layer converts the mesasage into a stream of bits 0 and 1s for transmission over the physical medium.
The receiving computer captures the bits from the physical medium and restructures the message. 
It sends this to data the link layer...and up the layers - This is the deencapsulation process,.When it reaches the app layer, it is sent to the intended SW recepient 

PDU : Protocol Data unit - the data sent across the layers

Data units across the various layers of the OSI model

Transport layer - segment 
Network layer - Packet 
DL layer - Frame 
Physcical - Bits 

Application layer 
The interface between the SW and the Stack. The SW application is not located here..we have the protocols and services required to interface 
with the application.

Presentation layer 
Responsible for encyption and decryption

Where can encryption occurr in network communication? 
1. Pre network encryption - where the SW encrpts prior to sending the data to the application layer 
2. Transport layer encryption - performed by TLS 
VPN encryption- Occurs at layer 2, layer 3 and 4 , depending on the VPN technology in use. L2TP, IPSEC, openVPN
3. Wireless encryption and the data link layer 
4. Bulk encryption and the physical layer (Occurs at the NIC)


Session layer 
Established, maintains and terminates the sessions betworrn 2 computers- Simplex, half duplex, full duplex 
Simplex - one way communication 
Half dublex - 2 way communication, one at a time, \
Full duplex - 2 way communication, simultaneous sending 

Transport Layer 
Manages integrity of connection 
Controls the session. This layer establishes the rules of communication. e.g how much data can each segment contain, how to verify the message integrity
How to determine whether data has been lost. Session rules are implemented through the handshake process
Segmantation, sequencing, error checking, adat flow, error correction, multiplexing 

Protocols: TCP, UDP, TLS 

Network layer
responsible for logocal addressing and routing 
Source and destination ip addresses added to the segment
Routers operate at this layer - Routers determine the bets path for a packet based on speed, hops, preference e.t.c 

Routing protocols - IGPs and ERPS 
IGPs are myopic while ERPs are far sighted 

IGP: DV and LS 
DV - Number of hops to detrmine the best path...RIP, IGRP
LS - router characteristivs to determine the best path. - Jitter, latency, error rate e.t.c - OSPF, IS-IS, EIGRP 


ERPs - Path Vector - BGP 

Ip header: Source and destination IP, destination Mac address, protocol 
Format of IPV4 packet 
Header size: 20 to 60 bytes
The first 20 bytes: Fixed set of information contraining data such as source and destination adress. 
The last set of 1 to 40 bytes consits of the options field 
Data section
Max size is 65,535 bytes




Data Link Protocol
IEEE 802.3
Adding source and destination hardware addresses. (Mac addresses)
Mac address: 48 bits - 24 bits (OIU), 24 bits(manufacturer)
Protocols : ARP , RARP, Ethernet 
Devices that function here are switches 

physical layer 
Converts frames into bits and transmits over the physcial medium. 
Devices that function at Layer 1: NICs, Hubs, repeaters, concentrators and amplifiers 

TCP/IP Model 
Also called the Darpa or DOD
Consuits of 4 layers : Applicatipon, Transport, Internet, Network access 

Some of the TCP/IP vulnerabilities 
:Buffer overflow , SYN flood attacks, DOS attacks, Fragment attacks, Oversized packet attacks, Spoofing attacks, man in the middle 
hijack attacks, coding error attacks . 


A protocol analyser is used to examine the content of network traffic. Also called sniffer, network evaluator, network analyser or packet capturing utility 
Can be a dedicated SW of HW device
Captures the frame or packet and uses complex tools to analyse. 
It places the NIC into promiscous mode to see and capture all the ethernet frames on the LAN. In this mode, the NIC ignotes the dectination address of the frames and collects all the frames that reach the interface
Exampines to the binary level
The payload is displayed in hexa or ASCII 
Protocol analysers offer capture filter and display filter
Capture filter: Decides which frames are captured and saved. 
Dispay filter: Show only frames from  the packet file that match your requirements 

Exmaples - Wireshark (Opne source) , Onmipeek, netwitness(commercial) 

Application layer Protocols 

|protocol  |  port          |     function 
--------------------------------------------
|Telnet    |    23          |  Terminal Emulation network application - remote connectivity between hosts for communication - USE SSH  instead
|FTP       |    20/21       |  File Transfer Protocol - Exchange of files that requires authentication - Should FTPS instead
|TFTP      |    UDP 69      |  Trivial File transfer - Does not require authentication - Can host netwoek device config files - Should not be used
|SMTP      |    25          |  Sends email messages from client to server and between email servers - Only use if encrypted with TLS to crearte SMTPS
|POP3      |    110         |  Post Office protocol- Used to pull emails from inbox in the email server to email client(client archiving) - Use if enctrpted with TLS to create POPS
|IMAP4     |    143         |  Intrnet Message Access Protocol - Used to pull emails from inbox in the email server to email client(client archiving)Has ability to retrieve only headers from the email server and delete messages directly on the server
|DHCP      |    UDP 67/68   |  Dynamic Host Control Protocol - Centralised control of TCP/IP configs 
|HTTP      |    80          |  HyperText Transfer protocol - Transmits web pages from web server to web browser in clear text 
|HTTPS     |    443         |  HyperTect Transfer Protocol - Transmits web pages from web server to web browser securely - TLS encrypted version of HTTP
|LDP       |    515         |  Used to send pribt jobs to a printer
|NFS       |    2049        |  Supports file sharing across dissimilar systems
|SNMP      |    UDP 161/162 |  Collects network helath and status information from a central monitoring station. 
|SSH       |  TCP 22        |


Transport layer protocols 
Connections are established using ports 
Ports are 16 digit binary numbers 
The total number of ports are 2^16 = 65536 
Ports are numbered 0 to 65,535
Socket: Combination of a port and IP 
0-1023 - well known ports or service ports - to be used by servers
1024 - 49151 - registered software ports - For IANA registered softwares 
49,152 - 65,535 - Random or dynamic ports used randomly by clients as source ports 

Protocols at transport layer : TCP and UDP 
TCP : Transmission Control Protocol - Full duplex connection oriented protocol , because of three way handshake 
UDP : User Datagram protocol - Simplex conectionless protocol - Best effort - low overhead, fast data transmission- Audio and video communications 

Three way handshake 

SYN - Syncronise sent form client to server 
SYN ACK - From Server to client - Syncronised and acknowledged
ACK - Client to server 

How do you disconnect a communication session when it is complete? 
1. FIN (finish)
2. RST (reset) 

Categories of network protocols 
1. Communication protocols - TCP, UDP, HTTP, DNS 
2. Management protocols - SNMP, ICMP 
3. Security protocols - HTTPS, SFTP 

Private Ip addresses 
10.0.0.0 - 10.255.255.255
172.16.0.0 - 172.31.255.255
192.168.0.0 - 192.168.255.255 

Public Ip Address 
1.0.0.0 - 9.255.255.255
11.0.0.0-126.255.255.255
128.0.0.0-172.15.255.255
172.32.0.0-192.167.255.255
192.169.0.0-233.255.255.255


IEEE802.11 - Wireless protocls 
Evolution of Wifi 
WEP - Wireless Equivalent privacy - The oldest wireless standard 
WPA - Wifi protected Access - Improvement on WEP however, vulnerable to KRACK, issues with authentication
WPA2 and WPA3 - WPA2 uses AES for authentication. This ensures message authentication and integrity. WPA3 has increase encyption, addresses vulnerabilities such as KRACK and uses simultaneous Autgentication of Equals 

Domain Name System 
What is DNS? Resolves human friendly domain name to an IP address 
Then ARP which resolves the IP address into the MAC address
DNS reverse kookup: resolves the IP address into the domain name

DNS is hierachical naming system 
DNS links IP addresses and human friendly FQDN 
FQDN consists of 
1. Top level Domain (TLD) - .com
2. Registered domain name: 
3. Subdomain 

Maximum length of FQDN - 253 characters 

The process of DNS 
Historically, the mapping used to be stored on a hosts file. However, this caused a security concern as hackers would be able to alter this file. 
When client software points to an FQDN, the resolver first checks the local DNS cache
Local DNS cache has the local hosts files and alny query results that havent timed out. 
If not in the DNS cache, the request is forwarded to the DNS server

DNS runs on TCP and UDP 53 
TCP 53 - zone transfers 
UDP 53 - for typical requests 

DNSSEC - provides mutual cert authentication and encrypted sessions between devices during DNS operations.. Applies to DNS servers only.

Non-DNS servers should use DoH. This creates an encrypted session with a DNS server of TLS protected HTTP and uses that session as a form of VPN to protect the DNS query and response
In 2020, we had, the ODOH (oblivious DNS over HTTPs) - this adds a DNS proxy between the client and DNS resolver so that the identity of requesting client is isolated from the DNS reslover. 
This provides anonymity and privacy to DNS queries.


DNS Poisoning 
The process of falsifying the DNS information used by client to reach a destination.

1. Rogue DNS server - The client sends a request to the DNS server. A rogue DNS server listens to the network traffic and responds to the client with falsified information.
Once client received the false information, the DNS quesry session is closed and hence the response form the reasl server id dropped and ignored. 

2. DNS Cache Poisoning 
This is a direct attack on the DNS servers by altering the primary record. There are 2 ways adverseries achieve this 
    - Attacking the authoritative DNS servers - this are the primary servers. Easily monitored by community hence not impactful on clients 
    - Attacking the DNS caching servers - These cache information from other DNS servers and might take long to be discoverd. 

3. DNS pharming 
Melicious redirection of valid websites URL or IP addresses to a fake website. Can be achieved by modifying the Local hosts file or poisonong or spoofing DNS resolution. 

4. Host file alteration 
An attacker plants false information into the hosts file. This affects specific clients 

5. DNS query spoofing 
Attacker intercepty the DNS session and eavedroping on the query. Attacker sends back a reply with false info. 

6. Use proxy falsification 

Defenses against DNS poisoning 

1. Limit zone transfers from internal DNS servers to external DNS servers - Blocking inbound TCP and UDP 53 
2. Require resolution through internal DNS. This requires blocking outbound UDP port 53 while keeping outbound TCP 53 open. 
3. Limit external DNS servers form which internal DNS servers pull zone transfers 
4. deploy Network IDS(NIDS) and Host IDS (HIDS) to monitor abnormal DNS traffic 
5. Harden DNS, servers, clients 
6. Use DNSSEC to secure DNS infra
7. Use DoH or ODOH 

Another - orgs can use split DNS 

What is Split DNS?
2 DNs servers - One public, one internal 
For the public, all data in the zone file should be accessible by the public via probing or querying 
For the internal DNS - this is only accessible to the internal systems 
ousiders cannot access the internal DNs as TCP and UDP 53 inbound is blocked 
Internal systems can be configured to only interact with the internal DNS server or send quesries to an external DNS server(for which a FDW in stateful 
mode is configured to allow the responses from approved outbound queries. 

Another  DNS Sinkhole
These provide false responses for DNS queries from Malware e.g bots so as to prevent access to cnc . 
It also protects users from visitinh lknown malicious websites .



Domain Hijacking 

Whn an attacker intententionally hijacks your domain name. 
How? 
1. Registering the domain immediately after you have registerd, 
2. carries out an on-path attack or 
3. exploits a flaws on the domain registrars end. 

What is the impact of domain hijacking? 
Customer redirection 
Reputation loss

Defence against domain hijacking? Strong authenticating e.g MFA 

Typosquatting
When an attacker takes advantage of when a user mistypes a domain mane or IP addresses. 
The attacker predictd the typos and registers those domains. when a user misytpes, they are redirected to the attacker domain

URL hijacking 


displaying a link or product that looks like a well known product in order to mislead the users.

Click jacking 
Redirect a users clicks or selection on a web page to a maliciuos target instead of the intended destination. 
This is achieved by adding an invisible or hidden overlay frame or image on the web pages 


IP networking 

What is IP 
It is a protocl 
Used to provide route addressing for data packets 
IP is connectionless and unreliable, just like UDP  - It does not guarantee delivery of the packets, or the order in which p[ackets are delivered.


IPV4 vs IPV6

IPV4 
most widely used in the world
Uses 32 bit addressing scheme


IPV6 
Uses 128bit addressing scheme
New features:Scped addresses, autoconfiguration and QOS
IPSEC is native 

Cocerns about migrating to IPV6 
1. WIth the larger addressing scheme od 128 bits, there are many more addresses that attackers can use as the source address - Ip filtering an d block lists will not be effective 
2. IPV6 secure deployment requires that all the systems adopt IPV6 
3. Lack of NAT - this reduces security and privacy. A systems locally assigned IP is npt masked by NAT to a public IP

How can IPV4 and IPV6 coexist on a network?
1. Dual stack - having systems run both IPV4 and OPV^ and use the appropriate protocol for eacjh conversation 
2. Tunnelling - Allows operation of a single stack of either IPV4 or IPV6 and use encapsulation to access systems of the other protocols.
3. NAT -PT : Network address Translation - Protocol Translation (RFC 2766) - used to convert betworrnn ipV4 and IPV6 network segments betwen internal and external addresses.


Differences between IPV4 and IPv6 
Length and dormat of addresses
IPV4: 4 octets, decimal separation, upto 4.3billion addresses. 
IPV6: 8 octets, colon sepator, hexadecimal , upto 340undecillion addresses 
Header: IPv6 is simpler than IPv4 

IPV6 header components: destination, source, payload length, next header, hop limit, Flow label, traffic class, version 
IPV4 header components: Version, ToS, total leengty, flags, identifocation, protocol, TTL, souce, destination, padding..


IP calsses 

A  0    1-126    /8
B  10    128-191    /16
C  110    192-223     /24
D  1110    223-239
E  1111    240-255


127.0.0.0 to 127.255.255.255 is used as the loopback address. 
Class A network of 0 is blackhole - traffic is routed inorder to be thrown away. 
IPV6 loopback - ::1/128 - not an address, it is a notation. 

ICMP 
Used to determine the health of a link. Used by Ping, traceroute, pathping 
ICMP uses echo packets and bounces them off remote systems. 
Use ping to detemine is a remote system is online or not. 

How can ICMP be exploited? Bandwidth DoS attacks e.g ping of death, smurf attacks and ping floods 

IGMP 
What is IGMP? 
Internet Group management protocol 
Allows systems to support multicasting i.e transmission of packets to multiple specific recipients 


ARP concerns 
What is ARP 
Address Rsolution protocol. A layer 2 protocol.
Resolves an IP address to a MAC address. 
ARP is carried as the payload of an ethernet frame
ARP uses caching and broadcasting 

Steps of ARP 
1. check the local cache - If available, use
2. If not available, broadcast s transmitted - If the destination is in the local network, the recpient will respond..if not
3. Us ethe default gw to transmit the communication

How can ARP be abused?
1. ARP cache poisonng - where attacker inserts bogus information into the ARP cache. 
Time in which information remains in the cache = 10 mins 

2. Create static ARP entries 

How can we defend against agaist ARP based attacks? 
1. Port security to prohibit communication with unknown, unauthorised rogue devices. 













DOS attack types 
1. SYN flooding 
2. ICMP flloding 
3. Ping of death - an oversized ICMP packet that is larger than 64KB
Reading TCP dump logs 

Common network protocol analysers 
1. Solarwinds Netflow Traffic analyser 
2. ManageEngine OPmanager
3. Wireshark 
4. tcpdump

What is tcpdump? a command-line network protocol analyzer. 
It is popular, lightweight–meaning it uses little memory and has a low CPU usage–and uses the open-source libpcap library. 
tcpdump is text based, meaning all commands in tcpdump are executed in the terminal. 
It can also be installed on other Unix-based operating systems, such as macOS®. 
It is preinstalled on many Linux distributions.

tcpdump provides a brief packet analysis and converts key information about network traffic into formats easily read by humans.
tcpdump also displays the source IP address, destination IP addresses, and the port numbers being used in the communications. 

https://github.com/murakaru/-CISSP-Challenge---2024-Study-Notes-Repository/issues/19#issue-2222613439


Timestamp: The output begins with the timestamp, formatted as hours, minutes, seconds, and fractions of a second.  

Source IP: The packet’s origin is provided by its source IP address.
Source port: This port number is where the packet originated.
Destination IP: The destination IP address is where the packet is being transmitted to.
Destination port: This port number is where the packet is being transmitted to.






















