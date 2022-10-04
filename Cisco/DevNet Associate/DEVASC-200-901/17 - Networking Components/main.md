#   What Are Networks?

&nbsp;

NIST CNSSI 4009 defines a network as follows:

<p style="text-align: left; margin:1em;">information system(s) implemented with a collection of interconnected components.  Such components may include routers, hubs, cabling, telecommunications controllers, key distribution centers, and technical control devices.</p>

&nbsp;

In other words, a network is formed when two or more systems are connected to each other and are able to communicate with each other.  With different types of connections, various types of networks can be built.  Three different factors are used to classify networks:

-   Topology
-   Standard
-   Size or location

&nbsp;

>   ***`Key Topic`***

&nbsp;

Topology refers to how the various nodes or elements connect.  Figure 17-1 shows three prominent network topologies:

-   **Bus**:  In a bus network, all the elements are connected one after the other.
-   **Star**:  In a star topology, all nodes in the system are connected to a central point.
-   **Ring**:  A ring topology is very similar to star except that a token is passed around, and a node can transmit only when it has a valid token.

&nbsp;

**Figure 17-1** *Network Topologies*

![Figure 17-1 Network Topologies](assets/images/Figure%2017-1%20Network%20Topologies.jpeg)

&nbsp;

***Standard*** refers to the protocol that the network uses.  Ethernet is one example of a standard.  An Ethernet network uses a star topology with concentrators connecting all the nodes in the network.  Ethernet speeds vary from 10 Mbps to 100 Mbps to 1 Gbps.  Another standard is Token Ring, which, as the name suggests, is a ring topology type.  Token Ring rates vary from 4 Mbps to 16 Mbps.

&nbsp;

The ***size*** of a network is a bit of an arbitrary concept.  Network sizes fall into basically four network types:

-   **Local-area network (LAN)**:  A LAN is typically a single network for an office, an enterprise,  or a home, and it is located completely within a single facility.  Figure 17-2 shows an example of a LAN that consists of various laptops, PCs, servers, and printers.

&nbsp;

**Figure 17-2** *Local-Area Network*

![Figure 17-2 Local-Area Network](assets/images/Figure%2017-2%20Local-Area%20Network.jpeg)

&nbsp;

-   **Campus-area network (CAN)**:  A CAN consists of two or more LANs within a limited area.  CANs help interconnect various buildings or departments within a campus of an enterprise or large office or school.  Figure 17-3 shows an example of a CAN that connects various LAN segments.

&nbsp;

**Figure 17-3** *Campus-Area Network*

![Figure 17-3 Campus-Area Network](assets/images/Figure%2017-3%20Campus-Area%20Network.jpeg)

&nbsp;

-   **Metropolitan-area network (MAN)**:  A MAN is a network that is extended to cover multiple locations within a slightly larger distance than a CAN.  A classic example of a MAN is the cable network in a city.  Figure 17-4 shows an example of a MAN that connects various network segments.

&nbsp;

**Figure 17-4** *Metropolitan-Area Network*

![Figure 17-4 Metropolitan-Area Network](assets/images/Figure%2017-4%20Metropolitan-Area%20Network.jpeg)

&nbsp;

-   **Wide-area network (WAN)**:  A WAN covers an even larger geographic area than a MAN.  The connections are through public networks, such as the telephone system, microwaves, satellite links, or leased lines.  Figure 17-5 shows an example of a WAN that connects various remote offices with the headquarters.

&nbsp;

**Figure 17-5** *Wide-Area Network*

![Figure 17-5 Wide-Area Network](assets/images/Figure%2017-5%20Wide-Area%20Network.jpeg)

&nbsp;

#   Elements of Networks

&nbsp;

Now that you have seen the various types of networks, let's look at what constitutes a network.  A network has several basic components:

-   Hubs
-   Switches
-   Bridges
-   Routers

&nbsp;

The following sections look at each of those elements in detail and also looks at the difference between them.  In the following sections you will see how to build a simple home network in which you want to connect two or three computers or devices.

&nbsp;

##  Hubs

&nbsp;

>   ***`Key Topic`***

&nbsp;

A hub is the least intelligent and most rudimentary network device.  With ah ub, traffic or data packets that come in any port are always sent out to all other ports.  For example, in Figure 17-6, Laptop 1 wants to communicate to Device 3.  The hub replicates and sends the packet from the laptop to each of the ports.  Only Device 3 responds back, and that response is again replicated to all ports.  Every device connected to the hub "sees" everything.  It is up to the devices themselves to decide if a packet is for them and whether they should respond.  The hub remains passive and does not really know or understand the traffic that flows through it.

&nbsp;

**Figure 17-6** *Hub: Every Device Receives Every Packet*

![Figure 17-6 Hub: Every Device Receives Every Packet](assets/images/Figure%2017-6%20Hub%20Every%20Device%20Receives%20Every%20Packet.jpeg)

&nbsp;

One of the biggest challenges with hubs is that every frame shows up at every device attached to a hub, instead of just showing up at the intended destination.  This can be a huge security problem.  Another challenge has to do with performance:  Because a hub can receive a lot of inbound frames, sending out frames can be difficult and can result in performance issues on the network.

&nbsp;

##  Bridges

&nbsp;

A bridge connects two physical network segments that use the same protocol.  Each network bridge builds a MAC address table of all devices that are connected on its ports.  When packet traffic arrives at the bridge and its target address is local to that side of the bridge, the bridge filters that frame, so that it stays on the local side of the bridge.

&nbsp;

If the bridge is unable to find the target address on the side that received the traffic, it forwards the frame across the bridge, hoping the destination will be on the other network segment.  In some cases, multiple bridges are cascaded.

-   Figure 17-7 shows how a bridge connects two LAN segments.

&nbsp;

**Figure 17-7** *Using a Bridge to Connect Two LAN Segments*

![Figure 17-7 Using a Bridge to Connect Two LAN Segments](assets/images/Figure%2017-7%20Using%20a%20Bridge%20to%20Connect%20Two%20LAN%20Segments.jpeg)

&nbsp;

##  Switches

&nbsp;

>   ***`Key Topic`***

&nbsp;

You can think of a switch as an "intelligent" hub.  A switch does what a hub does - but more efficiently and intelligently.  It analyzes the traffic as it flows.  A switch builds a port-to-MAC address table as devices start communicating.  This means a switch offers dramatically better performance than a hub.  To analyze the traffic, specialized hardware (called ***application-specific integrated circuits [ASICs]***) is needed.  If we replace the hub with a switch in our example, we get the setup shown in Figure 17-8, where a Layer 2 switch maintains a port-to-MAC address lookup table.

&nbsp;

**Figure 17-8** *Using a Layer 2 Switch for Port-to-MAC Address Mapping*

![Figure 17-8 Using a Layer 2 Switch for Port-to-MAC Address Mapping](assets/images/Figure%2017-8%20Using%20a%20Layer%202%20Switch%20for%20Port-to-MAC%20Address%20Mapping.jpeg)

&nbsp;

As you can see in Figure 17-8, each of the devices is "seen," and the MAC address is registered when the first packet is sent by the device.  Over a period, the switch generates a table that contains the port number on which each MAC address was seen.  It then uses this table to do a lookup for the destination MAC address and sends the incoming packet to the correct outgoing port.  In the figure, a packet destined for Device 3 is sent only to the correct port.

&nbsp;

Recall our look at the OSI model layers in Chapter 16.  The switch described so far in this section is a Layer 2 switch, which works at LAyer 2 of the OSI model (the data link layer).  The switch sends a packet to a destination port by using the MAC address lookup table, which stores the MAC address of a device associated with each port.  In contrast, a Layer 3 switch works at the network layer of the OSI model (Layer3 3), which means it looks at the IP address in order to do the switching.  Figure 17-9 shows a Layer 3 switch and how it maintains a port-to-IP address lookup table.

&nbsp;

**Figure 17-9** *Using a Layer 3 Switch for Port-to-IP Address Mapping*

![Figure 17-9 Using a Layer 3 Switch for Port-to-IP Address Mapping](assets/images/Figure%2017-9%20Using%20a%20Layer%203%20Switch%20for%20Port-to-IP%20Address%20Mapping.jpeg)

&nbsp;

Table 17-2 looks at some of the differences between Layer 2 and Layer 3 switches.

&nbsp;

**Table 17-2** Differences Between Layer 2 and Layer 3 Switches

| Layer 2 Switch | Layer 3 Switch |
| -- | -- |
| Operates at Layer 2 (data link) of the OSI model | Operates at Layer 3 (network layer) of the OSI model |
| Uses MAC addresses for forwarding | Uses IP addresses for forwarding |
| Performs Layer 2 switching only | Performs both Layer 2 and Layer 3 switching |
| Can be used to reduce traffic security on the local network | Can be used to implement a virtual local-area network (VLAN) |
| Has a single broadcast domain | Haas multiple broadcast domains |

&nbsp;

##  Virtual Local Area Networks (VLANs)

&nbsp;

>   ***`Key Topic`***

&nbsp;

A switch can be logically segmented into multiple broadcast domains by using virtual LANs (VLANs).  That is, if you have one switch, you can create multiple logical switches.  A VLAN is identified by a VLAN ID.  The VLAN ID is usually a value between 0 and 4095.  The default VLAN on any network is VLAN 1.  Every port on a switch can be assigned a different VLAN, or a group of ports can be assigned a particular VLAN ID.  VLANs allow network administrators to logically split a switch, allowing multiple broadcast domains to coexist on the same hardware but maintaining the isolation, security, and performance benefits of using completely separate switches.

&nbsp;

There are several advantages to creating VLANs:

-   **Network security**:  Creating VLANs within a switch also creates an automatic logical level of protection.  This kind of logical separation is very useful when there is a need to create networks for various departments in an enterprise.  Figure 17-10 shows three VLANs - VLAN 10, VLAN 20, and VLAN 30 - each assigned to a different department.

&nbsp;

**Figure 17-10** *Using a VLAN for Network Security*

![Figure 17-10 Using a VLAN for Network Security](assets/images/Figure%2017-10%20Using%20a%20VLAN%20for%20Network%20Security.jpeg)

&nbsp;

-   **Broadcast traffic distribution**:  Segmenting a large LAN into smaller VLANs can reduce broadcast traffic because each broadcast packet is sent only to the relevant VLAN.  For example, in Figure 17-10, which shows three VLANs - one for each of the domains - broadcast traffic will go to only the devices in the appropriate VLAN.
-   **Performance increase**:  Creating multiple broadcast domains reduces the broadcast traffic on the entire network tremendously, which in turn boosts the overall performance of the network.

&nbsp;

Say that you have a single switch.  By default, all of the ports on this switch are in one VLAN, such as VLAN 1.  Any port can be configured to be an access port or a trunk port:

-   **Access port**:  An access port is essentially a port that can be assigned to only one VLAN.  You can change the port membership by specifying the new VLAN ID.
-   **Trunk port**:  A trunk port can essentially have two or more VLANs configured.  It has the ability to transport traffic for several VLANs simultaneously.

&nbsp;

Figure 17-11 shows how trunk ports connect various VLANs across switches.

&nbsp;

**Figure 17-11** *VLAN Trunk Ports*

![Figure 17-11 VLAN Trunk Ports](assets/images/Figure%2017-11%20VLAN%20Trunk%20Ports.jpeg)

&nbsp;

##  Routers

&nbsp;

A router is a device that forwards packets between networks via the network layer of the OSI model (Layer 3).  It forwards, or routes, packets based on the IP address of the destination device.  A router also has the intelligence to determine the best path to reach a particular network or device.  It can determine the next hop, or routing destination, by using routing protocols such as Routing Information Protocol (RIP), Open Shortest Path First (OSPF), and Border Gateway Protocol (BGP).

&nbsp;

What is the difference between a Layer 3 switch and a router?  Both forward packets based on IP address, right?  The difference is pretty straightforward:  Whereas a switch operates within a network, a router connects two or more networks.  It routers packets to go across different protocols (such as Ethernet and WAN technologies such as cable, DSL, or satellite).  Another difference is that switches usually have dedicated hardware (ASICs) to forward packets as they come in.  In contrast, routers need more intelligence to route packets, and this intelligence is typically provided by software.

&nbsp;

Figure 17-12 shows a router connecting different types of networks.

&nbsp;

**Figure 17-12** *Using a Router to Connect Different Networks*

![Figure 17-12 Using a Router to Connect Different Networks](assets/images/Figure%2017-12%20Using%20a%20Router%20to%20Connect%20Different%20Networks.jpeg)

&nbsp;

##  Routing in Software

&nbsp;

As discussed earlier in this chapter, routers participate in route discovery, path determination, and packet forwarding.  Route discovery and path determination are part of the routing protocol, and as the router becomes part of this discovery process, it discovers and updates the routing tables accordingly.  There are basically three types of forwarding:

>   ***`Key Topic`***

&nbsp;

-   **Process switching**:  The CPU is involved for every packet that is routed and requires a full routing table lookup.  Process switching, shown in Figure 17-13, is the slowest type of forwarding as each of the packets that the interface driver receives (step 1 in the figure) is punted and put in the input queue for the processor for further action (step 2).  In this case, the processor receives the packets (step 3), determines the next interface it needs to send them to, and rewrites the headers as needed and puts the new packets in the output queue (step 4).  Finally, the kernel drivers for the new network interface picks up the packets and transmits them on the interface (step 5)

&nbsp;

**Figure 17-13** *Process Switching with the CPU Involved in Packet Routing Decisions*

![Figure 17-13 Process Switching with the CPU Involved in Packet Routing Decisions](assets/images/Figure%2017-13%20Process%20Switching%20with%20the%20CPU%20Involved%20in%20Packet%20Routing%20Decisions.jpeg)

&nbsp;

-   **Fast switching**:  Fast switching is the next-level evolution of process switching.  The CPU is involved for only the first packet that is routed.  It determines the outgoing interface required for the packet and updates the route cache, which typically resides in the kernel.  Once the route cache is populated, the input interfaces driver does a route-cache lookup and fast switches the packet to the outgoing interface.  Figure 17-14 shows fast switching, in which the processor essentially updates the route cache after it learns the next hop.  All subsequent packets are fast switched.

&nbsp;

**Figure 17-14** *Fast Switching and the Route Cache*

![Figure 17-14 Fast Switching and the Route Cache](assets/images/Figure%2017-14%20Fast%20Switching%20and%20the%20Route%20Cache.jpeg)

&nbsp;

-   **Cisco Express Forwarding (CEF) switching**:  CEF switching is an advanced Cisco-proprietary form of fast switching.  CEF switching sometimes involves specialized hardware and distributed routing, and the CPU may not need to get involved int he data path at all.  It does this by building a route cache with forwarding information; this is known as the ***Forwarding Information Base (FIB)*** table.  The FIB table contains precomputed reverse lookups and next-hop information for routes, including the interface and Layer 2 information to use.  When a network topology or routing table change occurs, the change is also reflected in the FIB table.  Figure 17-15 shows CEF switching, where both Layer 2 and LAyer 33 information is used.

&nbsp;

**Figure 17-15** *CEF Switching: Data Switching Using FIB Tables*

![Figure 17-15 CEF Switching: Data Switching Using FIB Tables](assets/images/Figure%2017-15%20CEF%20Switching%20Data%20Switching%20Using%20FIB%20Tables.jpeg)

&nbsp;

This analogy is sometimes used to illustrate the three types of switching:

-   Process switching is like doing mat hon paper:  Write down each step and solve the problem.
-   Fast switching, using the route cache, is like solving a problem by hand once and then simply recalling the answer from memory if the same problem is given.
-   CEF switching is like using formulas in an Excel spreadsheet, and when the numbers hit the cells, the answer is automatically calculated.

&nbsp;

##  Functions of a Router

&nbsp;

As discussed earlier in this chapter, a router is a device that appropriately and efficiently directs traffic from an incoming interface to the correct outgoing interface.  Apart from this primary function, a router has several other functions:

-   **Network segmentation**:  A router uses Network Address Translation (NAT) to map private IP addresses to public IP addresses.  Using NAT at the router secures the private network and also reduces the number of IP addresses needed to get messages to the public internet.  Figure 17-16 shows how network segmentation is achieved by using NAT.

&nbsp;

**Figure 17-16** *Router NAT: Translating Internal Addresses to External Addresses*

![Figure 17-16 Router NAT: Translating Internal Addresses to External Addresses](assets/images/Figure%2017-16%20Router%20NAT%20Translating%20Internal%20Addresses%20to%20External%20Addresses.jpeg)

-   **IP address management**:  A router uses Dynamic Host Configuration Protocol (DHCP) to assign IP addresses to devices that connect to the network.  Clients send DISCOVER broadcast message to figure out if a local DHCP server exists in the network.  If a DHCP server exists, it offers configurations such as an IP address, a MAC address, a domain, and so on via an OFFER message.  The client can then send a formal REQUEST to the server for allocating an IP address.  The server responds with an ACK unicast message to the client, indicating that the IP address has been allocated and confirmed.  Figure 17-17 shows a flow of clients requesting IP addresses via DHCP.

&nbsp;

**Figure 17-17** *Using DHCP to Assign IP Addresses*

![Figure 17-17 Using DHCP to Assign IP Addresses](assets/images/Figure%2017-17%20Using%20DHCP%20to%20Assign%20IP%20Addresses.jpeg)

&nbsp;

-   **Firewalls**:  A firewall safeguards a network from intentional or unintentional intrusion.  A firewall sits at the junction point or gateway between two networks - usually a private networks and a public network such as the Internet.  Users on the local area network of the router need to be protected from hackers and other malicious users.  A firewall blocks traffic from unauthorized users.  It also helps in allowing or blocking certain types of traffic on certain ports.  For example, a firewall may allow access to certain applications only, such as HTTP or SSH, and block all UDP traffic.  Figure 17-18 shows a firewall that allows only HTTP access to the outside world and blocks all incoming UDP traffic.

&nbsp;

**Figure 17-18** *Router Firewall: Allowing/Blocking Certain Apps or Traffic*

![Figure 17-18 Router Firewall: Allowing/Blocking Certain Apps or Traffic](assets/images/Figure%2017-18%20Router%20Firewall%20Allowing%20Blocking%20Certain%20Apps%20or%20Traffic.jpeg)

&nbsp;

-   **Domain name proxy**:  Modern firewalls interact with cloud DNS servers such as Cisco Umbrella or Open DNS to resolve DNS queries.  The queries and, in turn, the hosts can be stopped at the source if they are deemed harmful or malicious.

&nbsp;

##  Network Diagrams: Bringing It All Together

&nbsp;

So far in this chapter, you have learned about all the elements that constitute a network.  The best way to visually represent a network topology is by using a network diagram.  A network diagram maps out the structure of a network with different network element icons and connections between them.  This kind of visual presentation makes it simple and easy for anyone to understand how a network is built and can help not only during initial network deployment but also in debugging.

&nbsp;

Figure 17-19 shows a typical network topology.  At the core of the network is a router (Router 1) that connects three different networks.  One router interface is connected to a switch (Switch 1), a second router interface is connected to a switch (switch 2), and a third router interface is connected to a router (Router 2):

-   Switch 1 connects to Gigabit-ether 0/0 on the router.
-   Switch 2 connects to Gigabit-ether 0/1 on the router.
-   Router 2 connects to Fast-ethernet 0/0 on the router.

&nbsp;

**Figure 17-19** *Network Diagram*

![Figure 17-19 Network Diagram](assets/images/Figure%2017-19%20Network%20Diagram.jpeg)

&nbsp;

Both Switch 1 and Switch 2 have networks that consist of various devices such as computers, printers, and so on.  router 2 is the Internet router with firewall functionality and a connection to the service provider.

&nbsp;

#   Software-Defined Networking

&nbsp;

The term software-defined network (SDN) applies to a type of network architecture design that enables IT managers and network engineers to manage, control, and optimize network resources programmatically. 

&nbsp;

SDN essentially decouples network configuration and data flow engineering, regardless of the underlying hardware infrastructure.  It allows you to consistently control the network by using standard open APIs.

&nbsp;

Networks are often shown using three-level architecture, as shown in Figure 17-20, which consists of hardware and two planes:

-   **Data plane**:  As described in this chapter, a router can route packets faster by using techniques such as fast switching or CEF switching.  These techniques for punting packets from the incoming interface to the outgoing interface operate on what is traditionally known as the data plane.  The main objective of the data plane is to determine how the incoming packet on the a port must be forwarded to an outgoing port, based on specific values in the packet headers.
-   **Control plane**:  Routing protocols and other protocols make up the control plane.  the control plane determines how a packet is routed among routers or other network elements as the packet traverses end-to-end from source host to destination host.  The control plane also deals with packets that are destined for the router itself.  Device and network management are also part of the control plane.  Management functions include initializing interfaces with default configurations, IP addresses, policies, user accounts, and so on.

&nbsp;

**Figure 17-20** *Control Plane and Data Plane*

![Figure 17-20 Control Plane and Data Plane](assets/images/Figure%2017-20%20Control%20Plane%20and%20Data%20Plane.jpeg)

&nbsp;

Figure 17-21 shows three network elements: a router, a switch, and a wireless access point.  For each one of them, the figure shows the control plane and data plane.  The management of these devices includes the functions you use to control and monitor these devices.  As the controlling and monitoring function has to be done on each device, we call this architecture a "distributed control plane architecture."  The drawback is that network engineers or administrator have to manage each device independently, logging in to each device and setting it up.  Imagine that you have to make a simple configuration change such as enabling a syslog server; you would have to log in to each device independently and make the changes.

&nbsp;

**Figure 17-21** *Distributed Control Plane Architecture*

![Figure 17-21 Distributed Control Plane Architecture](assets/images/Figure%2017-21%20Distributed%20Control%20Plane%20Architecture.jpeg)

&nbsp;

To prevent the inefficiency of manually managing network devices, a network controller can be used.  When you use a network controller, you move the control planes from each network device and consolidate all of them in the network controller.  The network controller can then communicate with the network elements, and the network elements can send management data to the controller.  Because you now have one controller, this architecture is called a centralized control plane.  Figure 17-22 shows how a network controller cna be used to programmatically manage and control various networking elements using the northbound and southbound APIs.

&nbsp;

**Figure 17-22** *Centralized control Plane with a Network Controller*

![Figure 17-22 Centralized control Plane with a Network Controller](assets/images/Figure%2017-22%20Centralized%20control%20Plane%20with%20a%20Network%20Controller.jpeg)

&nbsp;

Communication between the network controller and the network elements is bidirectional.  Both sides use application programming interfaces (APIs), which allow the network controller and the network devices to communicated programmatically.  The network controller interacts with the network devices via southbound APIs, and the network elements interact with the network controller via northbound APIs.

&nbsp;

#   SDN Controllers

&nbsp;

>   ***`Key Topic`***

&nbsp;

An SDN controller is often considered the "brain" in a modern network.  The Open Networking Foundation (ONF) defines SDN as follows:

<p style="text-align: left; margin:1em;">an emerging architecture that is dynamic, manageable, cost-effective, and adaptable, making it ideal for the high-bandwidth, dynamic nature of applications.  This architecture decouples the network control and forwarding functions, enabling the network control to become directly programmable and the underlying infrastructure to be abstracted for applications and network services.</p>

&nbsp;

An SDN controller possesses a "global" view of the entire network.  It knows about all the network elements that constitute the network, the best paths between them, and other potential routes.  As indicated in the ONF SDN definition, SDN is a network architecture that separates the control and data planes for network devices and provides centralized management.  There are two widely popular controllers:

-   **OpenFlow**:  The ONF manages this standard used for communication between the SDN controller and managed network devices.
-   **OpenDayLight**:  The Linux Foundation (LF) manages this standard, which uses OpenFlow to manage network devices.

&nbsp;

As shown in Figure 17-23, SDN involves three layers: application layer, control layer, and infrastructure layer.

&nbsp;

**Figure 17-23** *Software-Defined Networking: Layered Architecture*

![Figure 17-23 Software-Defined Networking: Layered Architecture](assets/images/Figure%2017-23%20Software-Defined%20Networking%20Layered%20Architecture.jpeg)

&nbsp;

The infrastructure layer is composed of networking equipmenet and lements that form the actual network and elements that help to forward network traffic.  It could be a set of network switches and routers in the network or data centers.  The infrastructure layer is the physical layer over which network virtualization functions lay via the control layer.

&nbsp;

The control layer is where the SDN controllers reside to control network infrastructure.  The control layer has the business logic to fetch and maintain different types of network information, state details, topology details, and statistics details.  the SDN controller is all about managing networks, and it has all the control logic for network use cases such as switching, routing, Layer 2 VPNs, firewall security rules, DNS, DHCP, and clustering.  Cisco implements various services in its SDN controllers.  These services expose APIs (typically REST-based) to the upper layer (application layer), which makes life easy for network administrators who use apps on top of SDN controllers to configure, manage, and monitor the underlying network.  The control layer exposes two types of interfaces:

-   **Northbound interface**:  This interface is used for communication with the upper layer (the application layer) and is in general realized through REST APIs of SDN controllers.
-   **Southbound interfaces**:  This interface is meant for communication with the lower layer (the infrastructure layer) of network elements and is in general realized through southbound protocols, such as OpenFlow and NETCONF.

&nbsp;

The application layer is a developing area where a lot of innovations are happening.  The applications in this layer leverage information about the network topology, network state, network statistics, and so on.  Several types of applications can be developed, such as those related to network automation, network configuration, and management, network monitoring, network troubleshooting, network policies, and security.  Such SDN applications can provide various end-to-end solutions for real-world enterprise and data center networks.

&nbsp;

##  Cisco Software-Defined Networking (SDN)

&nbsp;

Cisco has introduced many SDN controllers in various domains, including the data center, campus, and even service provider domains.  The following is the list of Cisco's SDN products:

-   **Cisco Application Centric Infrastructure (ACI)**:  ACI ias the first Cisco SDN solution, and it has three components:
    -   **Application Network Profile**:  This is a collection of endpoint groups (EPGs), their connections, and the policies that define the connections.
    -   Application Policy Infrastructure Controller (APIC):  This is a centralized software controller that manages downstream switches and acts as a management plane.
    -   **ACI fabric**:  This is the connection between spine and leaf switches.  In the ACI world, spine and leaf are the cisco Nexus 9000 Series switches, which act as the control plane and the data plane of the ACI.
-   **Cisco Digital Network Architecture (DNA)**:  Cisco DNA introduces the concept of intent-based networking, which interprets business needs into technical solutions.
-   **Cisco Network Services Orchestrator (NSO)**:  This is a solution mostly for automating tasks in service provider environments.  NSO is a multivendor controller installed in Linux that supports NETCONF, OpenFlow, SNMP, and APIs.
-   **Cisco Software-Defined WAN (SD-WAN)**:  SD-WAN deals with creating and managing WAN connections in a cloud-based environment.  SD-WAN solutions have several key features - including segmentation, centralized policies, zero-touch provisioning, and configuration templates - that can be very helpful to customers.  Cisco SD-WAN has four main components, each with a very specific role.
    -   **vManage (for management)**:  vManage is a GUI-based network management system that handles the management plane.  vManage is a single pane of glass that provides various key stats.  An operations team can use vManager for day-to-day operational activities.
    -   **vSmart (controller)**:  vSmart is the main brain of SD-WAN, and it manages the control plane.  vSmart does all the complex work of path calculation, route advertisement, and so on by allowing the data plane to do only packet forwarding.
    -   **vEdge (data plane)**:  The vEdge router's job is to forward packets based on the policies configured with vSmart.  The vEdge keeps a constant connection with vSmart to get updaters.
    -   **vBond (orchestrator)**:  vBond is the orchestrator and the gatekeeper that validates and authorizes every vEdge device trying to join the network.  It also orchestrates the connectivity between vEdge and vSmart.