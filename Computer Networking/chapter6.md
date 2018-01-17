Chapter6
=============
##goals
- understand principles behind link layer services
    - error detection, correction
    - sharing a broadcast channel: multiple access
    - link layer addressing
    - local area networks: Ethernet, VLAN
- instantiation, implementation of various link layer technologies
-------------------------------
##6.1 introduction, services
link layer transfer datagram from one node to **physically adjacent** noe over link
datagram transferred by different link protocols over different links
### link protocols
    ethernet, ppp, 802.ii
### link layer services
    + framing, link access
        encapsulate datagram into frame
        mac addresses used in frame header to identify source, destination
    + reliable delivery between adjacent nodes
        seldom used on low bit-error link(fiber, twisted pair)
        **why both link-level and end-end reliability**
    + flow control
    + error detection
        error caused by signal attenuation, noise
    + error correction
        receiver identifies and corrects bit errors(s)
    + full-duplex / half-duplex
### link layer implemented
    + in each and every host
    + implemented in adaptor(network interface card NIC)
### adaptor communicating
    sending side
        + encapsulates datagram in frame
        + adds error checking bits, rdt, flow control
    recieving side
        + looks for errors, rdt, control
        + extracts datagram, passes to upper layer
-------------------------------
## 6.2 error detection/correction
### error detection
    EDC
### parity checking 
    single bit parity
    two-dimensional bit parity
### internet checksum
    used at transport layer only
### cyclic redundancy check
    D:data G: r+1 bit pattern 
    D: data to be sent R:CRC bits
    D*2^r XOR R
    example
---------------------------------
## 6.3 multiple access protocols
two types of links
    + point-to-point
        ppp for dial-up access
    + broadcast(shared wire or medium)
        upstream HFC
        802.II wireless LAN
**collision** if node reveives two or more signals at the same time
**multiple access protocol**
    desired properties
### MAC protocols: taxonomy
**channel partitioning**
    divide channel into pieces
**random access**
    channel not divided, allow collisions
**taking turns**
    nodes with more to sent can take longer turns
### channel partitioning MAC protocols
**TDMA** time division multiple access
access to channel in rounds, each station get fixed slot
**FDMA** frequency division multiple access
### random access MAC protocol
**slotted ALOHA**
efficiency
max efficiency = 1/e = 3.7
**ALOHA**
max efficiency = 1/2e = 2.8
**CSMA**
**CSMA/CD**
binary(exponential)backoff
CSMA + CD(collision detection)
easy in wire LANs: measure signal strength, compare transmitted, received signals
difficult in wireless LANs: received signal strenth overwhelmed by local transmission strength
, CSMA/CA**
carrier sense multiple access
CSMA listen before transmit
if channel sesed idle,transmit entire frame
if channel sensed busy, defer transmission
transmit at full channel data rate R
two or more transmitting nodes->collision
- **how to detect collisions**
- **how to recover from collisions**
### taking turns protocols
FDDI, bluetooth, token ring
**polling**
**token passing**
-----------------------
## 6.4 LANs
### MAC addresses and ARP
ip address MAC(LAN or physical or Ethernet) address
MAC flat address -> protability
    can move LAN card from one LAN to another
IP hierarchical address - > unprotable
    address depends on IP subnet to which node is attached
**ARP:address resolution protocol**
ARP table <ip address; MAC address; TTL>
### Ethernet
wired  LAN  technology
#### physical topology
    - **bus** coaxial cable
    - **star** switch
#### frame structure
    sending adapter encapsulates IP datagram in Ethernet frame
    - preamble
    - addresses
    - type
#### Ethernet is unreliable, connectionless
    - connectionless: no handshaking between sending  and receiving NICs
    - unreliable: receiving NIC doesn't send acks or nacks
    - ethernet's mac protocol
        - unslotted CSMA/CD with binary backoff
#### 802.3 Ethernet standards: link & physical layers
    common MAC protocol and frame format
    different speeds: 2 Mbps, 10Mbps, 100Mbps
    different physical layer media: fiber, cable
### Ethernet switch
#### switch
    - link-layer device: takes an active role
    - **transparent**
        hosts are unaware of presence of switches
    - **plug-and-play self-learning**
        switches do not need to be configured
    - **switching can transmit simultaneously**
#### switch forwarding table
each switch has a switch table
switch **learns** which hosts can be reached through which interfaces
#### properties of link-layer switching
- elimination of collisions
- heterogeneous links
- management
#### different between switches and routers
- routers
    network-layer devices
    compute tables using routing algorithms, IP addresses
- switches(no network layer)
    link-layer devices
    learn forwarding table using flooding, learning, MAC addresses
### VLANs
virtual local area network
define multiple virtual LANs over single physical LAN infrastructure
#### port-based VLAN
    - traffic isolation
    - dynamic membership
        ports can be dynamically assigned among VLANs
    - forwarding between VLANS
        done via routing(just as with separate switches)
#### VLANs spanning multiple switches
**trunk port**
carries frames between VLANS defined over multiple physical switches
    802.I q protocol adds/removed additional header fields for frames forwarded between trunk ports
### wireless LANs
#### 802.II LAN architecture
**AP(base station=access point)**
**BSS(basic service set)**
#### 802.II channels, association

----------------------
## 6.7 a day in the life of a web request
- **DHCP**
dhcp request encapsulated
    -**UDP**
    -**IP**
    -**802.3 Ethernet**
    -broadcast(dest:全F)
    -ethernet demuxed to ip demuxed to udp demuxed to dhcp
client now has ip address, name & address of DNS server, ip address of its first-hop router
- **DNS**
DNS encapsulated
    -**UDP**
    -**IP**
    -**ARP**
client now knows MAC address of first hop router
- **TCP**
- **HTTP**