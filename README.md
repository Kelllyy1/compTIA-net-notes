This repo will be dedicated to provide a summary of all of my notes that I have gathered in my preparation for my CompTIA Network+ Certification Study & Attempt.

# How I learn best
- Skim the textbook chapter
- Read through the textbook chapter, as I do this I:
    - add kaywords from each section to my iPad in my note-taking app
        - form a map to connect the terms (after finishing the chapter)
    - take summarized notes in my physical notebook with pens after reading each section (or a few sub-sections)
    - practice the example questions at the end of the chapter and cross-reference the answers in the Appendix
    - brain dump on GitHub after one or a few chapters
    - take a practice test every other day to track progress

# Network Types
Defining the types of networks that exist, these include LAN, MAN, WAN, PAN, CAN, SAN, SDWAN, mGRE, MLPS

- LAN: Local Area Network. Small network that spans across a building, network for a single department.
- MAN: Metropolitan Area Network. Bigger network that spans across a few departments or buildings.
- WAN: Wide Area Network. Spans across geographical areas, or connects networks in different separate locations, connects several LANS.
- PAN: Personal Area Network. Is within a home lab or office. Spans a few meters and connects devices within a very small scope such as connecting a pair of headphones to a phone, or a computer to a print. Can use wired or wireless connection, bluetooth or USB.
- CAN: Campus Area Network. Connects a university campus or corporate environment. Not bigger than a WAN.
- SAN: Storage Area Network. Allows servers to connect to storage devices across the network.
- SDWAN: Software-Defined WAN.


# Network Topologies
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



# OSI Model

<br>All People Seem To Need Data Processing or  Please Do Not Throw Sausage Pizza Away
<br>Layer 7   Application
<br>Layer 6   Presentation
<br>Layer 5   Session
<br>Layer 4   Transport
<br>Layer 3   Network
<br>Layer 2   Data Link
<br>Layer 1    Physical



# Resurces Used