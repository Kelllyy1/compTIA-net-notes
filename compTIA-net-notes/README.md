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
---

# Objective 1
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

---
# Objective 2

## 1 - Static Routing
    Statuic routing allows us network administrators to manually configure routing tables, or to manually configure routes between devices.
    This is best for small networks with few changes. This is not a scalable solution.

## 2 - Dynamic Routing
    This is better for larger networks and allows for scaling and dynamic routing, or automatic routing of network traffic with the use of a dynamic protocol.

    1. RIP (Routing Information Protocol)
    Type: Distance-Vector
    IGP: Yes
    Port: UDP 520
    Version: RIP v2 (supports CIDR and multicasting)

    - How It Works:
    Sends entire routing table every 30 seconds to neighbors.

    Chooses the route with the fewest hops (max = 15 hops).

    If a route has 16 hops, it’s considered unreachable.

    - Metric: Hop Count
    Each router between source and destination adds +1.

    Fewer hops = preferred.

    - Administrative Distance: 120
    (Least trustworthy of the major protocols)

    - Strengths:
    Simple to configure.

    Works in small networks.

    - Weaknesses:
    Slow convergence.

    No loop prevention, limited scalability.

    2. OSPF (Open Shortest Path First)
    Type: Link-State
    IGP: Yes
    Port: IP protocol 89

    - How It Works:
    Each router builds a complete map of the network (called an LSDB).

    Uses Dijkstra’s algorithm (Shortest Path First) to choose the best path.

    - Metric: Cost
    Cost = 100 Mbps / interface bandwidth

    So faster interfaces (like Gigabit) have lower cost.

    - Administrative Distance: 110
    - Strengths:
    Scalable, efficient, fast convergence.

    Loop prevention built-in.

    Supports areas for logical grouping (Area 0 = backbone).

    - Weaknesses:
    More complex to configure.

    Needs proper area design.

    3. EIGRP (Enhanced Interior Gateway Routing Protocol)
    Type: Advanced Distance-Vector (Hybrid)
    IGP: Yes
    Port: 88 (Cisco proprietary)

    - How It Works:
    Cisco’s hybrid protocol using DUAL algorithm.

    Supports equal-cost and unequal-cost load balancing.

    - Metric: Composite of:
    Bandwidth

    Delay

    Reliability

    Load

    (Default = bandwidth + delay only)

    - Administrative Distance:
    90 for internal EIGRP

    170 for external EIGRP

    - Strengths:
    Fast convergence

    Loop-free via Feasible Successors

    Summarization and VLSM support

    - Weaknesses:
    Cisco-only (unless using EIGRP over IP protocol 88 on newer multi-vendor networks)

    4. BGP (Border Gateway Protocol)
    Type: Path-Vector
    EGP: Yes
    Port: TCP 179

    - How It Works:
    Used to route between autonomous systems (ISPs, enterprises).

    Exchanges full routing policies (not just paths).

    Builds a path based on AS numbers (autonomous system numbers).

    - Metric: Path attributes, like:
    AS Path Length (shorter is better)

    Next-hop IP

    Origin type

    MED (Multi-exit discriminator)

    Local preference

    - Administrative Distance:
    20 (External BGP)

    200 (Internal BGP)

    - Strengths:
    Essential for internet routing.

    Customizable routing decisions (policies).

    Handles massive routing tables.

    - Weaknesses:
    Slow convergence

    Complex to configure

    Can be hijacked if not secured

    5. IS-IS (Intermediate System to Intermediate System)
    Type: Link-State
    IGP: Yes
    Port: None (runs directly over Layer 2, not IP-based)

    - How It Works:
    IS-IS is a link-state routing protocol, similar to OSPF, but uses CLNS (Connectionless Network Service) for communication rather than IP.

    Routers running IS-IS build a complete topological database (like OSPF’s LSDB).

    Uses Dijkstra’s Shortest Path First (SPF) algorithm to calculate routes.

    Divides the network into levels:

    Level 1: Intra-area routing (within a domain)

    Level 2: Inter-area routing (between domains)

    Supports hierarchical routing like OSPF (with Areas), but is more flexible in large, scalable environments (like carrier networks).

    - Metric: Cost
    Cost is assigned manually or automatically based on interface speed.

    Lower cost = preferred path (just like OSPF).

    - Administrative Distance:
    115 (default in Cisco)

    - Strengths:
    Highly scalable, used by ISPs and service providers.

    Protocol-independent: supports IPv4, IPv6, and non-IP protocols.

    Runs directly over Layer 2, so it doesn’t rely on IP to operate.

    Often preferred over OSPF in very large networks.

    - Weaknesses:
    Less familiar to enterprise engineers (OSPF more common in corporate settings).

    Slightly more complex syntax and terminology.

    Can be confusing due to CLNS background.
    [Courtesy of ChatGPT for the dynamic routing protocol explanations]
    

## 3 - Routing Technologies
    Building a routing table with RIPv2 & EIGRP
    RIPv2

    EIGRP


## 4 - Network Address Translation


## 5 - VLANs and Trunking
    Normal frame vs. Frame v/ VLAN header added
    Trunking & its affects

## 6 - Interface Configuration
    Ethernet
    Switches
    Packet Transmission


## 7 - Spanning Tree Protocol
    Root Port
    Designated Port
    Blocked Port
    RSTP


## 8 - Wireless Technologies
    Common Frequencies
    Band steering
    DFS
    TPC


## 9 - Wireless Networking
    IBSS
    SSID
    BSSID
    ESSID
    Captive portal
    Security modes
        Open System
        PSK
        Enterprise
        Personal
        CAPWAP


## 10 - Network Types
    Wireless Mesh
    Point-to-point
    Ad-hoc


## 11 - Wireless Encryption
    WEP
    WPA
    WPA2
    WPA3
    WPA-CCIE (or something lke that from Dion's practice exam)


## 12 - Installing Networks
    Distribution frame
    MDF
    IDF
    Equipment Racks
    Patch panel
    Cooling (of the data center)


## 13 - Power
    UPS
    PDU


## 14 - Environmental Factors (Things to consider)
    Humidity
    Equipment temperatures
    Fire suppression
    

TODO: Put this in the right place, after reviwing
## Wireless Networking Ethernet Protocols
802.11a, 802.11b,
802.11g,
802.11n,
802.11ar,
802.11ax,
802.11be

---
# Objective 3

## Network Documentation

---
# Objective 5

## Network Troubleshooting
When troubleshooting an issue with the network, the following steps can be taken to ge to the bottom of it and solve the issue at hand. Here is the guideline:
1. Identify the problem - try to duplicate the problem, ask the user questions, identify changes that ocurred recently, break the problem down.
2. Establish a theory - Occam's razor; consider everything, follow a top down approach to pinppoint the possible problem.
3. Test the theory - create steps based on the theory and execute them.
4. Evaluate the results -  if the desired result isn't achieved, redo step 2 and establish a new theory. Else, move on to the next step.
5. Establish a plan - we want to prevent the issue from happening again, so it's imortant to design a plan to integrate the change into our system.
6. Implement the plan - carry out the plan like a boss.
7. Verify full system functionality - ensure the system works as expected and that the issue is gone.
8. Document the findings - document the initial problem, the process followed and changes made for future reference.

## Cable Issues
- Fiber mismatching: different cables server different purposes and offer different metrics, so it's important to use the right cablefor the right situation to avoid underperformance or unexpected behavior.
- Use a cable tester to troubleshoot cabling issues.
- Crosstalk is a common issue - this is when signals from one cable interfere with signals in another cable.
    - NEXT measured at the transmitted end
    - FEXT - measured at the opposite end of transmission
    - AXT - alient, when other cables interfere
    - ACR - attenuation to crosstalk ratio - a comparison of signal loss over distance to crosstalk. SNR (signal to noise ratio)

    Troubleshooting for crosstalk:
    - issue could be at the crimp
    - adding twists could help
    - wire separation could help
    - use careful cable handling
    - test the SNR after installation

- Cable termination - ensure that the connection is correct.

## Interface Issues
SNPM - Simple Network Management Protocol - used to look at statistics for networking devices.

## Hardware Issues
Transcievers sometimes have issues. We should make sure that it matches with the correct cable and wavelength to avoid attenuation, and also supply the right power.

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