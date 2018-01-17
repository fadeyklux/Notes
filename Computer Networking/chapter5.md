Chapter5 Network Layer-Control Plane
=========
link state中的oscillation是什么？
distance vecotr中最坏的情况是？

----------------------
##goals
+ understanding principles behind network control plane
+ SDN controllers
+ Internet Control Message Protocol
+ network management
+ OSPF BGP OpenFlow ODL ONOS
+ ICMP SNMP
----------------
## 5.1 introductino
+ **two network-layer function**
    + forwarding-data plane
    + routing-control plane
+ **two approches of control plane**
    + per-router control
    + logically centralized control 
        software defined networking
------------------
## 5.2 routing protocols
+ link state
    dijkstra **oscillations???**
+ distance vector
    bellman-ford $D_x(y)=min\{c(x,v)+d_v(y)\}$
    when link cost change what will happen?
    **convergence timn varies, count-to-infinity**
---------------------
## 5.3 intra-AS routing in the internet:OSPF
+ **autonomous system(AS)**
+ **intra-AS routing**
    routing in same AS
    all routers in AS must run **same** intra-domain protocol
    + intra-AS routing algorithm
+ **inter-AS routing**
    routing among AS
    + inter-AS routing algorithm
router in AS1 destined outside of AS1
propagate rechability info to all routers in AS1
+ interior gateway protocols(IGP)
##intra-AS routing protocols:
+ RIP routing information protocol
+ OSPF open shortest path
    use link-state algorithm
    carried in OSPF messages directly over **IP**
    like IS-IS routing protocol
    + hierarchical OSPF
        two-level hierarchy: local area, backbone
        link-state advertisement only in area
        + area border routers
        + backbone routers
        + boundary routers
+ IGRP interior gateway routing protocol
-------------------
## 5.4 inter-AS routing
**BGP(border gateway protocol)**
eBGP
iBGP
+ BGP session: over TCP connection
    advertise: prefix(destination)+attributesd = route
    two attributes
    **AS-PATH**
    **NEXT-HOP**
    policy-based routing
    how BGP path advertisement works?
    BGP route slection
    + local preference-**policy**
    + shortest AS-PATH
    + closest NEXT-HOP-**hot potato routing**
    + additional criteria
## different between inter/intra routing
+ **policy**
    inter-AS: admin wants to control how traffic is routed
    intra-AS: no need
+ **scale**
    hierarchical routing saves table size, reduced update traffic
+ **performance**
    intra-AS: can focus on performance
    inter-AS: policy may dominate over performance
-------------------------------
## 5.5 software defined networking(SDN)
+ network control applications
+ SDN controller
+ network switches
+ **openflow protocol**
    controller to switch message
    switch to controller message
-------------------------------
## 5.6 ICMP(internet control message protocol)
+ **ICMP**
    used by hosts & routers to communicate
    ICMP msgs carried in IP datagrams
    **format** type+code+first 8 bytes of IP datagram
    source send UDP to routers and routers back ICMP(name of routers and ip address)
----------------------------------
## 5.7 network management
**managed devices** contain **managed objects** whose data is gathered into a **management information base(MIB)**
+ **SNMP protocol**
    + request/response mode
    + trap mode