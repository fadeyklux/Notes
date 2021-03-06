Chapter4: The Network Layer:Data Plane
======================================pre_
network layer can be decomposed into two interactiing parts,the **data plane** and the **control plane**
what will be coverd?
+ *per_router* functions
+ traditional IP forwarding
+ generalized forwarding
+ IPv4 IPv6 addressing

4.1 Overview of Network Layer
------------------------------
### 4.1.1 Forwarding and Routing: The Data and Control Planes
+ two important network-layer functions:
    + *Forwarding* in data plane of the network layer
    + *Routing* in control plane of the network layer

4.2 What's Inside a Router?
-----------------------------
### 4.2.1 Input Port Processiing and Destination-Based Forwarding
+ **longest prefix matching**
### 4.2.2 Switching
+ Switching via memory
    + only one memeory read/write can be done at a time.
+ Switching via a bus
    + only one packet can cross the bus at a time.
+ Switching via an interconnection network
    + crossbar switch **non-blocking**
    + a packet being forwarding will not be blocked as long as no other packet is currently being forwarded to that output port.
### 4.2.3 Output Port Processing
### 4.2.4 Where Does Queueing Occur?
+ queueing-at both input ports and output ports
+ factor: **line speed**, **traffic load**, **relative speed**
+ **Input Queueing**
    + head-of-line(HOL) blocking
    a queued packet in an input queue must wait for transfer through the fabric even though its output port is free
+ **Output Queueing**
    + drop-tail drop the arriving packet
    + active queue management(AQM) 
    Random Early Detection(RED)
### 4.2.5 Packet Scheduling
+ FIFO
+ Priority Queueing
    + non-preemptive priority queuing
    the transmission of a packet is not interrupted once it has begun
+ Round Robin and Weighted Fair Queueing(WFQ)
alternates service among different classes in priority 
queueing
    + **work_conserving queueing**
    move on to the next class in the service sequence when it finds an empty calss queue.(轮到服务你但是你为空我就跳过)
+ WFQ each class may receive a different amout of service in any interval of time.

4.3 The Internet Protocol(IP): IPv4,IPv6,Addressing
----------------------
### 4.3.1 IPv4 Datagram Format
20 bytes of header(no optons)
+ *Version number* 4bits
+ *Header length* 
+ *Type of service*
+ *Datagram length* 16bits long
+ *Identifier, flags, fragmentation offset*
+ *Time-to-live*
+ *Protocol*
    指定IP datagram的data portion应该传给transport-layer的哪种协议
+ *Checksum*
    + 路由器检查到错误就丢弃datagram，因为每经过一个路由器TTL和option（可能）都会改变，所以要重新计算checksum
    + 为什么TCP/IP 在transport layer和networklayer 都要error checking？
    + IP能携带不会传给TCP/UDP的数据
+ *Source and destination IP address*
+ *Option* IPv6没有
+ *Data(Playload)*
    包含transport-layer segment(TCP/UDP)还可以包含其他数据(ICMP)

### 4.3.2 IPv4 Datagram Fragmentaion
+ maximum transmission unit(MTU)
+ 为什么要fragmentation?
  因为不同的link-layer protocol有不同的MTU
+ fragments need to be reassembled befroe reach transport layer
### 4.3.3 IPv4 Addressing
+ **interface**
    * 什么是interface?
    * an IP address is technically associated with an interface, rather than with the host or router containing that interface*
+ **subnet**
    + 如何划分子网
    + 255.255.255.255 广播地址
+ **subnet mask**
    + 注意，路由器之间也算可以构成子网
+ **DHCP**
    dynamic host configuration protocol 自动分配IP地址
    + first-hop router = default gateway
    + DHCP protocol的four-step process
        + DHCP server discovery **DHCP discover message**
        + DHCP server offer **DHCP offer message** 同个子网可能有多个DHCP server
        + DHCP request **DHCP request message**
        + DHCP message **DHCP ACK**
### 4.3.4 Network Address Translation(NAT)
+ private network
    + 10.0.0.0/8 是三种保留的IP地址之一
    + **NAT translation table** 让router知道该把外网的datagram传给哪个host