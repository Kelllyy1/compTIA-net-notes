<!-- Page -->
<details>
<summary>Page 1</summary>

# OSI Model Notes – Objective 1 (5/22)

The OSI Model is an easy way to organize the network.

---

## L1: Physical
- Bits of 0s and 1s  
- We deal with signal across wires  
- Cables:  
  - Twisted-pair cables, fiber, and adapter ends  

---

## L2: Data Link
- Communicates with 2 devices on a network  
- MAC addresses over Ethernet  
- Traffic is forwarded based on destination MAC addresses  
- Switching layer  

---

## L3: Network
- Routers determine how to forward traffic  
- Routing layer, IP addresses  
- Fragmentation of data  

---

## L4: Transport
- Moves information from one side of the network to the next  
- Protocols used are TCP, UDP  

---

## L5: Session
- Communication management between devices  
- Control, tunneling protocols  

---

## L6: Presentation
- Translates message data encryption  
- Character encoding: ASCII from Application layer 
</details>


<!-- Page -->
<details>
<summary>Page 2</summary>

## L7: Application
- Humans interact with this OSI layer
- HTTP, DNS, FTP are services we interact with

---

## Recap Table: What occurs on the network

| Layer | Name         | What Happens                     |
|-------|--------------|----------------------------------|
| L7    | Application  | HTTPS                            |
| L6    | Presentation | SSL/TLS                          |
| L5    | Session      | control/tunnel protocol          |
| L4    | Transport    | TCP / UDP                        |
| L3    | Network      | IP, router, packet path          |
| L2    | Data Link    | MAC only, frame, switch          |
| L1    | Physical     | Cables                           |

---

## Switch vs. Router (based on traffic)

- **Switch**: L2 — Forwards traffic based on **MAC address**
- **Router**: L3 — Forwards traffic based on **IP address**

---

## Example: Different traffic types on port numbers
- **NGFW** vs **Traditional**:
  - NGFW = Next Gen Firewall  
  - Can look into different **functionalities** (e.g. Layer 7, app-layer inspection)
  - Possible (NAT, etc.)

---

## IDS vs IPS
- **IDS**: Looks for threats, sends alert, does **not** block attack  
- **IPS**: Prevents threats by actively blocking

---

## Notes
- Multiple devices: Just because you connect at L1 doesn't mean you connect at all other 2–3 levels  
- Routers connect different LANs (traffic)  
- L3 decides IP address  
- Determines the next hop for the data  
</details>


<!-- Page -->
<details>
<summary>Page 3</summary>

</details>