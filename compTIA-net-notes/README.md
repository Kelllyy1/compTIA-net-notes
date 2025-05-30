This repo will be dedicated to provide a summary of all of my notes that I have gathered in my preparation for my CompTIA Network+ Certification Study & Attempt.

## How I learn best -- My System --
- Skim the textbook chapter
- Read through the textbook chapter, as I do this I:
    - add kaywords from each section to my iPad in my note-taking app
        - form a map to connect the terms (after finishing the chapter)
    - take summarized notes in my physical notebook with pens after reading each section (or a few sub-sections)
    - practice the example questions at the end of the chapter and cross-reference the answers in the Appendix
    - brain dump on GitHub after one or a few chapters
    - take a practice test every other day to track progress

## Network Types
Defining the types of networks that exist, these include LAN, MAN, WAN, PAN, CAN, SAN, SDWAN, mGRE, MLPS

- LAN: Local Area Network. Small network that spans across a building, network for a single department.
- MAN: Metropolitan Area Network. Bigger network that spans across a few departments or buildings.
- WAN: Wide Area Network. Spans across geographical areas, or connects networks in different separate locations, connects several LANS.
- PAN: Personal Area Network. Is within a home lab or office. Spans a few meters and connects devices within a very small scope such as connecting a pair of headphones to a phone, or a computer to a print. Can use wired or wireless connection, bluetooth or USB.
- CAN: Campus Area Network. Connects a university campus or corporate environment. Not bigger than a WAN.
- SAN: Storage Area Network. Allows servers to connect to storage devices across the network.
- SDWAN: Software-Defined WAN.


## Network Topologies
Defining the topologies that exist, these include bus, star, ring, mesh, hybrid.
- bus: most basic top.
    - Every device is connected to a single wire.
    - Lowesst fault tolerance. if the wire fails, the network fails
    - Not that scalable
    - Very inexpensive (because only one wire is needed lol)
- star: better, I like this one.
    - every device is connected to a centralized device (switch, hub)
    - very easy to scale
    - a little bit on the costly side, every new added device requires more wires to scale
    - if one device fails, the entire network does not fail so the fault tolerance is decent
    - single point of failure, central point goes down, then network goes down
- ring: not the best design, not really used today
    - every device is connected to another device in a ring/circular structure
    - fault tolerance is not so great, if one device fails, similar to the bus, then the entire network fails
    - it's hard to scale this structure
    - not very costly due to few wires needed
- mesh:
    - every device is connected to every other device
    - complicated design to manage and configure
    - easy to scale
    - most costly because of the multiple connections between devices
    - best fault tolerance because of multiple connections; if a single device fails, the network survives



## OSI Model
This is a framework that gives an overview of how the network works in terms of data flow, networking devices, services, protocols, etc.

<br>All People Seem To Need Data Processing or  Please Do Not Throw Sausage Pizza Away
<br>Layer 7   Application       what we see as humans; user interface                                       data
<br>Layer 6   Presentation      encapsulation                                                               data
<br>Layer 5   Session           connecting devices together & communicating; control protocol; TLS/SSL      data
<br>Layer 4   Transport         moving data from one side of the network to the next; TCP/UDP               segments/datagrams
<br>Layer 3   Network           everything to do with IPs, routing                                          packets
<br>Layer 2   Data Link         everything to do with MAC Addresses, MAC addressing, switching              frames
<br>Layer 1   Physical          everything to do with cabling                                               bits

## Networking Devices
### Router
    connects multiple networks (LANs) together,sometimes connects LANs to WANs. Layer 3

### Switch
    forwards traffic based on the destination MAC addresses. Layer 2

### Hubs
    sends data to all connected ports. Layer 1

### Firewall
    filters packets based on port numbers

### IDS
    Intrusion Detection System - detects and alerts for vulnerabilities and attacks, but doesn't fix or prevent them.

### IPS
    Intrusion Prevention System - blocks attacks from happening

### Load Balancer
    Spreads the load from various services across different servers to improve speed, functionality.

### Proxy
    sits in the middle of an end user and the Internet. Acts on behalf of the end user to execute services,applications. Adds an extra layer of security.

### NAS & SAN
    Network Attached Storage - retrieves whole files, allows for local modifications and then re-stores the entire file.
    SAN - Storage Area Network - retrieves files in block, allows for modification, and stores those blocks; gives servers access to storage devices on the network.

### Access Point
    connects wireless devices to a wired network. Layer 2. Connects 802.11 (wireless) to 802.3 (ethernet)

### LAN Controller
    manages all access points on the network.

## Network Functions
### CDN Content Delivery Network
    connects users to different geographical locations quicker

### VPN Virtual Private Network
    encrypts data as it travels across the network

### QoS Quality of Service
    allows for prioritization of applications and services

### TTL time to Live
- IP addressing
    - measured in hops (number of routes a packet travels through before reaching the destination)
    - failsafe for if a packet is stuck in a loop, after the ttl counts down to 0, the packet is dropped
    - default TTL for MAC/Linux is 64 hops, default for Windows is 128 hops

- DNS resolution
    - measured in seconds
    - determines how long data is cached for, after the ttl expires, cache is cleared

## Designing the Cloud
    some components important for desinging cloud networks. Physical devices can be hosted virtually on the cloud and utilized there

### Virtual Private Cloud
    this environment allows for access to virtual devices in the cloud in order to configure networks.

### VPC Transmit Gateway
    serves as a clod router, connects multiple VPCs together.

### VPC NAT Gateway
    allows VPCs private resources to access the Internet.

### VPC Endpoint
    allows private subnets in VPCs to connect to external services (like AWS).

### Network Security List
    we can create rules that will apply to all devices on te subnet. There is not much room for granularity.

### Network Security Group
    we have more granularity here. We can customize different vNICs with different rules.

## Different Cloud Models

### SaaS Software as a Service
    rent the entire application and add your data to it. Third party manages the hardware and application for you, you just log in.

### IaaS Infrastructure as a Service
    rent the equipment/hardware, configure it and create your application and manage your data. You build and manage.

### PaaS Platform as a Service
    rent the tools to build your application, not necessarily the hardware, but preconfigured services that can be combined to build an application. Sits between SaaS and IaaS.


## Internet Protocol
    Layer 3 focuses on this protocol. If we look at the analogy of a truck delivering items we can further understand IP addressing.
        Driving                 transfer of data
        Road                    cable, data flows through this
        Truck                   IP
        Boxes inside truck      TCP/UDP
        Stuff in box            Data

## **Some Common Ports**

Common Ports
| Port      | Service   | Name              | Additional Information             |
| ----      | -------   | ----              | ---------------------             |
| tcp/22    | SSH       | Secure Shell      |                                  |
| tcp/20-21 | FTP | | | port 20 is for file transfers, port 21 is for control|
| tcp/22 | SFTP |
| tcp/23| Telnet |
| tcp/25 | SMTP |
| udp/53 | DNS |
| udp/67 | DHCP |
| tcp/69 | TFTP |
| tcp/80 | HTTP |
| tcp/443 | HTTPS |
| udp/123 | NTP |
| udp/161 | SNMP |
| udp/162 | SNMP trap |
| tcp/389 | LDAP(S) |
| tcp/445 | SMB |
| udp/514 | Syslog |
| tcp/1433 | Databases |
| tcp/3389 | RDP |
| tcp/ 5061 | SIP |

Other Common Protocols
| Service      | Purpose   |
| ----      | -------   |
| ICMP | ping |
| GRE | |
| VPN | |
| IPSEC | |
| IKE | |

## Network Communication Types

Unicast - peer to peer, 1:1
Multicast - simultaneous, 1:M,
Anycast - send signals to IP addresses with multipe endpoints
Broadcast - send to all connected devices, 1:A  

## Wireless Networking Ethernet Protocols
802.11a, 802.11b,
802.11g,
802.11n,
802.11ar,
802.11ax,
802.11be



<!--
| First Header  | Second Header |
| ------------- | ------------- |
| Content Cell Expanded too | Content Cell  |
| Content Cell  | Content Cell With a lot of information  |
-->
<!--
# Ethernet at A Glance

## Ethernet Basics

## Ethernet at the Data Link Layer

## Ethernet at the Physical Layer

## Ethernet Standards
-->

# Resources Used