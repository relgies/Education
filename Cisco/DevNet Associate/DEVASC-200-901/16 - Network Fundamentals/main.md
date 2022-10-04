#   Foundation Topics

&nbsp;

Network devices have been built for more than 50 years now.  The term *device* is used here to mean any piece of electronic equipment that has a network interface card of some sort.  End-user devices or consumer devices such as personal computers, laptops, smartphones, tablets, and printers, as well as infrastructure devices such as switches, routers, firewalls, and load balancers have been interconnected in both private and public networks for many years.  What started as islands of disparate devices connected on university campuses in the 1960s and then connected directly with each other on ARPANET has evolved to become the Internet, where everyone and everything is interconnected.  This chapter discusses the fundamentals of networking.

&nbsp;

#   Network Reference Models

&nbsp;

Several network reference models have been developed through the years, some of them proprietary and some open.  Two reference models stand out from the crowd for their importance and longevity: the OSI model and the TCP/IP reference model.

&nbsp;

##  The OSI Model

&nbsp;

In the late 1970s, as computing devices became more and more popular, a need to correct them in a manner in which they would be able to exchange data between them arose.  The old sneakernet - which involved physically copying data that needed to be transferred between devices on a floppy disk and delivering it on foot - was no longer appropriate for the amounts of data that needed to be exchanged.  Disparate proprietary solutions such as *System Network Architecture (SNA)* from IBM and DECnet from *Digital Equipment Corporation (DEC)* existed for this purpose, but there was a need to have a standard, interoperable, and common way to do networking.  The *International Organization for Standardization (ISO)* took on the challenge and came up with the *Open Systems Interconnection (OSI)* model.  Although it has not been implemented in production systems, the OSI model is still extensively used especially from an educational perspective.  The Simpler TCP/IP (Transport Control Protocol/Internet Protocol) model has had such more success in real life and is covered in more detail later in this chapter.

&nbsp;

The main idea with developing networking models based on different layers that interact with each other was inspired by the computer science mantra of splitting a difficult problem into smaller more manageable problems.  Following this philosophy, the OSI model splits the data transmission processes needed to transfer data between two or mode devices into seven layers.  An advantage with a layered approach is that there can be different vendors at different layers implementing the specific functionality required by each layer.  There are network equipment vendors that focus on developing devices that operate at Layer 2 of the OSI model, called *switches*, and devices that operate at Layer 3 of the model, called *routers*, and so on.  But probably the biggest advantage of layering is the level of innovation that this model allows at each layer.  As long as the functionality provided by each layer stays consistent with the expectations of the layer above, protocols, hardware, and software can be developed and improved.  Take, for example, the way the Ethernet protocol and specifications have evolved over the years from transfer rates of 10 Mbps in the early days of the protocol to 400 Gbps today.  This improvement of several orders of magnitude has been possible because of the layering philosophy.  As long as the data transmission layer provides a set of primitives to the layer above, it can freely innovate and improve.

&nbsp;

>   ***`Key Topic`***

&nbsp;

In the layered approach, each layer provides a set of functionality and features to the layer above it and consumes the features of the layer below it.  The OSI model defines seven layers for exchanging data between network devices (see Figure 16-1).  Two or more devices that would exchange data with each other using the OSI model need to implement all seven layers.

&nbsp;

**Figure 16-1** *OSI Model Layer*

![Figure 16-1 OSI Model Layer](assets/images/Figure%2016-1%20OSI%20Model%20Layer.jpeg)

&nbsp;

Applications that need to transmit data over the network start at the application layer, gathering the data that needs to be transmitted.  This data makes its way down the transmission model and gets processed at each layer by being split into smaller chunks, with header and foot information added, and then being encoded on the physical medium.  As the bits arrive at the destination, the reverse process takes place: As the data moves up the layers at the receiver, headers and footers are removed, and data is recombined into bigger chunks and made available to the receiving application.  This is similar in a way to how postal mail works.  When sending out heartwarming holiday wishes via snail mail, first you need to put your message on a piece of paper.  This is the equivalent of the application layer at the sender.  Then you put the paper with the message in an envelope, seal the envelope, write down the sender and receiver information, and drop the envelope in a mailbox or at the post office.  The postal service plays the role of the physical layer in this case, as it sorts through the mail and delivers each piece to its destination.  The person receiving hte mail makes sure that the envelope is meant for him or her and then goes ahead and reverses part of the process you went through, removing the paper from the envelope and reading the message.  The message is successfully delivered from source to destination in both cases - on a network and via snail mail - but it takes a fraction fo a second for data to get anywhere on planet earth on a network, whereas it might take days or weeks for snail mail to reach a recipient, depending on how far the recipient is from the sender.

&nbsp;

Data transmission protocols have been developed at each layer of the OSI model to perform the functionality required by that layer.  Each layer is supposed to perform specific tasks and provide specific functionality to the layers above it.

&nbsp;

The **physical layer** is tasked with the transmission and reception of raw bit streams.  At this layer, specifications about the voltage levels, pinouts of the connectors, physical transmission data rates, modulation schemes, and so on are defined.  This is where the proverbial rubber meets the road, and data to be transmitted is converted into electrical, optical, or radio signals.  Protocols such as Ethernet and Bluetooth have specifications at the physical layer.

&nbsp;

The **data link layer** provides device-to-device data transfer on a local-area network.  It defines how data is formatted for transmission and how access to the physical medium is controlled.  Errors that might have happened in transit on the physical layer are corrected at the data link layer.  Bridges and switches are devices that operate at the data link layer.  The IEEE has several protocols defined for the data link layer, organized into the IEEE 802 family of protocols.  According to the specifications in these protocols, the data link layer is further subdivided into two sublayers:

-   The ***Media Access Control (MAC)*** layer provides specifications on how devices gain access to the transmission medium.
-   The ***Logical Link Control (LCC)*** layer is responsible for encapsulating network layer data and frame synchronization.

&nbsp;

The **network layer** provides connectivity between devices that are connected to separate networks.  Whereas the data link layer ensures communication between directly connected devices on a local network, the network layer enables communication between devices that are in geographically separate locations.  Logical addressing of all the devices on the network and routing of data packets on the best path between a sender and a receiver are also specified at the network layer.  Routers are devices that operate at the network layer.  If the data that needs to be transmitted over the data link layer is too large to be sent at once, the network layer has the capability to fragment the data into smaller pieces.  As the name indicates, the process of *fragmentation* consists of splitting the data into smaller pieces, sending those pieces on the newark, and then reassembling them when they arrive at another device on the network.  Fragmentation should eb avoided as much as possible as it slows down the transmission of data considerably.  This slowdown occurs because of how modern routers forward data packets and the mechanism they implement to accomplish this as fast as possible.  Most modern routers perform data routing in hardware using specialized integrated circuits called ASICs.  When data becomes fragmented, in stead of being forwarded in hardware using the ASICs, the packets get process switched, which means they are forwarded based on an interrupt system using the regular CPU on the router.  Data delivery at the network layer is best effort, as reliable transmission is not required at this layer.  As we'll see shortly, reliable transmission is handled at the next higher layer, the transport layer.

&nbsp;

The **transport layer**, as the name suggests, is responsible for end-to-end transport of data from the source to the destination of the data traffic.  It segments data that it receives from the layer above and reassembles it into a stream of data on the receiving device.  This layer specifies several mechanisms so that data is reliably transmitted between devices.  Error detection and recovery mechanisms and information flow control ensure reliable service.  This is also where the delineation between the application and the network is usually done.  The transport layer and the network, data link, and physical layers make up the data transport layers.  The main purpose of these layers is to reliably transfer the data from the sending device to the receiving device.  The layers on top of the transport layer - the session, presentation, and application layers - as you will soon see, are concerned more with application issues and making sure data is formatted the right way.  Two types of protocols are defined at this layer: connection-oriented and connectionless protocols.

&nbsp;

A connection-oriented protocols establishes and end-to-end connection between the sender and the receiver, keeps track of all the segments that are being transmitted, and has a retransmission mechanism in place.  Retransmissions happen in cases in which some of the segments that are sent are lost on the way and don't get to their destination or become corrupted and cannot be recovered at the receiver.  A system of acknowledgements is in place to signal successfully receiving the data and availability to receive additional data.  A sliding windows mechanisms dynamically adjusts the amount of data that is transmitted on the wire before the sender is waiting for an acknowledgement from the receiver.  Large data transfers, SSH terminal sessions, and the World Wide Web and email sessions use connection-oriented protocols at the transport layer.  Although not defined with the OSI specification, transmission Control Protocol (TCP) is the most common connection-oriented protocol at the transport layer.

&nbsp;

A connectionless protocol does not establish an end-to-end connection between the sender and the receiver.  This type of data transmission is mostly used for real-time traffic such as voice and video, in which it is better to ignore the data segments that are lost or corrupted on the way than to stop the transfer of data and ask for retransmission.  For example, in the case of a voice over IP (VoIP) call, the end-user experience is much better if the network just ignores a few milliseconds of lost data that the human ear can compensate for anyway than if the network stops the flow of data, queues the data already received at the receiver, retransmits the missing few milliseconds, replays the message, and then dequeues the data that was waiting for playback at the receiver.  User Datagram Protocol (UDP) is the most common connectionless protocol used at the transport layer.

&nbsp;

The **session layer** establishes, manages, and terminates sessions between two communicating devices.  On top of the end-ot-end communication channel that the transport layer establishes, the session layer has the role of keeping track of whose turn it is to transmits data, and it ensures that the same operation is not performed at the same time by different clients or even by resuming failed transmissions.  Applications that implement the Remote Procedure Call (RPC) framework use the session layer extensively.

&nbsp;

The **presentation layer** ensures that the information from the application layer of the sending device is readable and interpretable by the application layer of the receiving device.  The presentation layer is not focused on the moving of bits between devices as much as it is focused on how the data being transferred is originated and the syntax and semantics used for this data.  For example, if different encodings for text-based exchange of information are used on sending and receiving devices (for example, ASCII versus EBCDIC), the two presentation layers use a common encoding format for translating between the two encodings and makes sure data at the application layer is displayed correctly on both systems.  Also at this layer, the data is differentiated and encoded based on the type of information it contains ,such as text files, video files, binary files, and so on.

&nbsp;

The **application layer** is the OSI layer that is closest to the user and contains all the applications and protocols that the users are interacting with, such as email, file transfer, and video streaming.  One application layer protocol that is extensively used is Hypertext Transfer Protocol (HTTP), which is at the heart of the World Wide Web.  Whenever a website is accessed on a web server, the data between the client browser and the web server is carried over HTTP.

&nbsp;

The OSI model didn't find much success when it was initially developed, and it was not adopted by most network equipment vendors at the time, but it is still used for education purposes and to emphasize the important of separating data transmission in computer networks into layers with specific functions.

&nbsp;

##  The TCP/IP Model

&nbsp;

A much more successful implementation of the layered architecture to data transmission and device networking is the TCP/IP (Transmission Control Protocol/Internet Protocol) reference model, also referred to as the *Internet Protocol suite*.  Created around the same time as the OSI model, the TCP/IP reference model was adopted and implemented by most networking vendors back in those days and has over time become the reference model for the internet.

&nbsp;

The Internet Protocol suite and the main protocols that make up the model, TCP and IP, started as a research project by the U.S. Department of Defense through a program called Defense Advanced Research Project Agency (DARPA) in the 1960s.  It was the middle of the Cold War, and the main purpose of the project was to build a telecommunications network that would be able to withstand a nuclear attack and still be able to function if any of the devices making up the network were destroyed or disabled.

&nbsp;

>   ***`Key Topic`***

&nbsp;

Much like the OSI model, the TCP/IP reference model uses a layered approach (see Figure 16-2).  Each layer provides the functionality and features specified in the reference model and serves a the layer above it.

&nbsp;

**Figure 16-2** *TCP/IP Reference Model Layer*

![Figure 16-2 TCP/IP Reference Model Layer](assets/images/Figure%2016-2%20TCP%20IP%20Reference%20Model%20Layer.jpeg)

&nbsp;

The **network access layer** in hte TCP/IP model corresponding to the physical and data link layers in the OSI model, and it provides the same services to the layer above.  It deals with moving data packets between the Internet layer interfaces of two devices connected on the same link.  It specifies the physical characteristics of serial lines, Ethernet, and wireless links, such as voltage, data transmission rates, maximum transmission distance, and physical connectors.  The network layer defines how data is formatted for transmission on the physical link, how the data packet is received from the Internet layer for transmission by adding a header and footer, how the data frames are transmitted over the physical medium, how access to the network is controlled, and which device can transmit at which point.  Switching and switches, as described later in this chapter, operate at the network access layer.

&nbsp;

The **Internet layer** of the TCP/IP reference model corresponds to the network layer of the OSI model in terms of functions and characteristics.  It is responsible for transmitting data cross disparate and distant networks in a process called *data routing*.  *Routers* are devices that operate at the Internet layer and perform the routing function.  As oyu might have guessed from the name of the reference mode, Internet Protocol (IP) is the main protocol operating at the Internet layer.  The IP protocols performs two basic functions:

-   Device addressing and identification
-   Data packet routing

&nbsp;

Devices connected to a TCP/IP network are identified by their IP addresses.  two addressing solutions are currently supported by the Inter: IP version 4 (IPv4) and IP version 6 (IPv6).  IPv4 uses addressing based on 32 bits, which means that approximately 4 billion devices can be uniquely identified on the network, as you can imagine, there are more than 4 billion endpoints connected to the Internet today.  Temporary solutions to address the lack of IPv4 addresses have been developed over the years, including private IP address subnets and Network Address Translation (NAT), both of which are discussed later in this chapter.  The permanent fix to this problem was the development and standardization in 1998 of IPv6, which uses 128-bit addresses and is able to provide unique addresses for a gigantic number of endpoints and devices.  Both IPv4- and IPv6-addressed device are currently supported and connected to the Internet, but Ipv4 is slowly being phased out.

&nbsp;

The second function of the Internet layer is data packet routing.  Routing packets means forwarding data from its source toward the destination through a network of interconnected routers.  Through this functionality, the Internet layer makes possible internetworking and the connection of different IP networks, essentially establishing the Internet.  The packet forwarding at the Internet layer is best effort and unreliable, and any error correction and retransmission mechanisms required have to be implemented at higher layers.  The Internet layer is agnostic to the data structures and the operations that the layer above it is implementing.  If we go back to the post mail analogy, the Internet layer acts as the postal service infrastructure and the mail carries who deliver the letters and packages without knowing what they actually contain.  In the same way, the Internet layer receives data segments from the transport layer and carries them all the way to th destination without knowing what the actual data is.

&nbsp;

The **transport layer** is the core of the TCP/IP reference model.  It establishes end-to-end data channels over which applications exchange data, regardless of the structure of the user data and the underlying network.  Since the Internet layer is best effort, the protocols at the transport layer provide flow control, congestion control, segmentation, and error control.  Differentiating between different applications running on the same host occurs at the transport layer through port number.  The transport layer port is a 16-bit logical construct allocated for each of the communications channels an application requires.  The ports in the range 0 to 1023, called *well-known ports* or *system ports*, are used for system processes that provide widely used types of network services.  For example, web servers that implement HTTP are by default listening for connections on port 80 for regular HTTP traffic or on port 443 for secure HTTP traffic via HTTP Secure (HTTPS).  End-to-end connections at the transport layer can be categorized as either connection oriented (usually implemented using TCP) or connectionless (using UDP).

&nbsp;

TCP uses several different technologies to ensure reliable bit stream delivery.  First of all, data is delivered in the order in which it was sent, and TCP has mechanisms of keeping track of each data segment sent.  A dynamic windowing system controls traffic congestion and ensures that the sender doesn't overwhelm the receiver with too much data.  If packets are lost on the way to the destination or become corrupted in transit, TCP handles the retransmission of this data.  IF the data becomes duplicated in transmission, the duplicated data is discarded at the receiver.

&nbsp;

UDP is a connectionless datagram protocol that is used in situations where timely data delivery is more important than reliability.  It is a best-effort, unreliable protocol that implements a basic checksum mechanism for error detection.  UDP is typically used for applications such as streaming media, voice, and video.

&nbsp;

The TCP/IP model transport layer corresponds roughly to the OSI model transport layer described earlier in this chapter.

&nbsp;

The **application layer**, as the name suggests, contains all the end-user applications that need to exchange data over the network.  The application layer protocols exchange data on top of the end-to-end, sender-to-receiver connection that is established by the lower-layer protocols.  There are a large number of application layer protocols, including the following:

-   ***Hypertext Transfer Protocol (HTTP)*** is used for transferring web pages between web browsers and web servers.
-   ***File Transfer Protocol (FTP)*** is used for transferring files between a client and a server.
-   ***Dynamic Host Configuration Protocol (DHCP)*** is used to dynamically assign IP addresses to devices on a network.


&nbsp;

The application layer in the TCP/IP reference model corresponds to the session, presentation, and application layers of the OSI model.

&nbsp;

>   ***`Key Topic`***

&nbsp;

In order to be able to communicate between devices using a layered model, the protocols running at each layer on the source host must be able to communicate with their counterparts at the destination host.  The data that is being exchanged at each layer is called a ***protocol data unit (PDU)***.  Based on the layer processing the data, the PDUs have different names:

-   At the application layer, the general term for the PUD is ***data***
-   At the transport layer, the PDU is called a ***segment***.
-   At the Internet layer, the PDU is called a ***packet***.
-   At the data link layer, the PDU is called a ***frame***.

&nbsp;

Figure 16-3 shows the PDUs at each layer and the flow of data from sender to receiver.

&nbsp;

**Figure 16-3** *TCP/IP Reference Model PDUs at Each Layer*

![Figure 16-3 TCP/IP Reference Model PDUs at Each Layer](assets/images/Figure%2016-3%20TCP%20IP%20Reference%20Model%20PDUs%20at%20Each%20Layer.jpeg)

&nbsp;

As data moves down the layers at the sending host, it gets processed at each layer.  This process is called ***encapsulation***, and there is a corresponding process at the destination host called ***de-encapsulation***.  The encapsulation process consists in adding extra protocol information at each layer so that the layer-to-layer communication can take place.  Starting at the top, the user data generated in the application layer gets passed down to the transport layer for transmission.  the protocol running at the transport layer takes the data it receives from the application layer, adds its header information, and passes the datagram PDU to the Internet layer.  Similarly, the Internet layer adds its own header and passes the packet PDU to the data link layer.  The data link layer takes the data from the Internet layer and build a frame PDU that is ready to be sent on the physical medium by adding its own protocol header and a ***frame check sequence (FCS)*** footer.  The role of the FCS footer is to ensure that the data is transmitted without errors.  At each hop along the way to the destination, a checksum of the whole frame is computed and added to the FCS footer.  If the computed checksum is different from the checksum in the FCS footer, the receiving devices knows an error occurred on the transmission path.  At the data link layer, the user information with all the header and footer information is finally transmitted on the physical medium.

&nbsp;

As the data is received at the destination host, it goes through a similar process but in the reserve order.  This process, called ***de-encapsulation***, consists of removing the header and footer information at each layer and passing the data to the layer above until it gets to the application layer, where it is interpreted by the application protocol.  Figure 16-4 shows the processes  of encapsulation at the sender and de-encapsulation at hte receiver.

&nbsp;

**Figure 16-4** *Encapsulation and De-encapsulation*

![Figure 16-4 Encapsulation and De-encapsulation](assets/images/Figure%2016-4%20Encapsulation%20and%20De-encapsulation.jpeg)

&nbsp;

#   Switching Concepts

&nbsp;

Data frame switching is a critical process in moving data traffic from a source network endpoint to a destination endpoint within a local-area network (LAN).  this section introduces several networking concepts: Ethernet, MAC addresses, VLANs, and switching.

&nbsp;

##  Ethernet

&nbsp;

A LAN is a network that is confined within a building or campus.  These types of networks start on the smaller side with home networks, where end-user devices such as personal computers, smartphones, laptops, and printers connect - usually through a wireless connection - to a local home network.  The main characteristic of these networks is that the data traffic between the devices connected to the LAN stays local and can be transferred between these devices by a *switch*, which is a network device that operates at the data link layer and enables direct communication between devices connected to a LAN.

&nbsp;

The most common LAN technology is Ethernet.  Ethernet is a data link layer protocol defined by the IEEE.  The Ethernet protocol encompasses guidelines and standards that specify cabling and signaling formats at the physical and data link layers.  For example, EThernet standards specify characteristics for different types of cables and network interface ports, and they also specify voltage levels and the maximum distance the signal can travel before it becomes too attenuated to be successfully received.  Over time, the Ethernet protocol has evolved from transfer rates of 10 Mbps to 100 Gbps and even 400 Gbps.  The transmission medium has also evolved from coaxial cable to twisted-pair cable, fiber optics, and wireless.

&nbsp;

As mentioned previously, the PDU at the data link layer is called a *frame*.  The Ethernet protocol specifies the format shown in Figure 16-5 for the Ethernet frame, which includes the following fields:

&nbsp;

**Figure 16-5** *Ethernet Frame Format*

![Figure 16-5 Ethernet Frame Format](assets/images/Figure%2016-5%20Ethernet%20Frame%20Format.jpeg)

&nbsp;

-   **Preamble**:  This field consists of 8 bytes of alternating 1s and 0s that are used to synchronize the signals of the sender and receiver.
-   **Destination Address**:  This field contains the address of the receiver.
-   **Source Address**:  This field contains the address of the source device.
-   **Type**:  This field contains a code that identifies the network layer protocol.
-   **Data**:  This field contains the data that was received from the network layer and that needs to be transmitted to the receiver.
-   **Frame Checksum Sequence (FCS)**:  This 4-byte field includes a checksum mechanism to ensure that the frame has been transmitted without corruption.

&nbsp;

##  MAC Addresses

&nbsp;

***Media Access Control (MAC)*** addresses are used to enable communication between devices connected to a local network.  Several types of MAC addresses are used to accommodate the different types of network communications.  There are three major types of network communications:

-   **Unicast**:  In this type of communication, data frames are sent between one specific source and addressed to one specific destination.  This type of transmission has one sender and one receiver, and it is the most common type of traffic on any network.
-   **Broadcast**:  In this type of communication, data frames are sent from one source address to all other source addresses connected to the same LAN.  There is one sender, but the information is sent to all devices connected to the network.
-   **Multicast**:  In this type of communication, information is sent from one device to a group of devices or clients.  In order for the clients to receive the multicast data, they have to be members of a multicast group.  Whereas broadcast is used to transmit data to all the clients on the network, multicast is used to transmit data to just a subset of those clients.

&nbsp;

In order to distinguish between these three types of network communications, the IEEE has defined MAC addresses for each type:

-   When the least significant bit of a MAC address's first byte is 0, it means the frame is meant to reach only one receiving NIC, which means unicast traffic.
-   When the least significant bit of a the first octet of a MAC address is 1, it means the frame is a multicast frame, and the receiving NICs will process it if they were configured to accept multicast MAC addresses.  An example of a multicast MAC address that is used by ***Cisco Discovery Protocol (CPD)*** is 01-00-0C-CC-CC-CC
-   When all the bits are set to 1, it means the frame is a broadcast frame, and it is being received by all the NICs on that network segment.

&nbsp;

>   ***`Key Topic`***

&nbsp;

Each client that needs to exchange data on an Ethernet network needs to have a unique MAC address so that the data is directed to the proper destination device.  The MAC address is burned into the ***network interface card (NIC)*** and is also called the ***burned-in address (BIA)*** or the physical address of the device.  A MAC address has 48 bits organized as 12 hexadecimal numbers.  There are several different ways of representing MAC addresses, all of them containing the same information.  The following representations of a MAC address are all equivalent:

-   0000.0c59.beef
-   00:00:0c:59:be:ef
-   00-00-0C-59-BE-EF

&nbsp;

A MAC address has two components (see Figure 16-6):

-   **Organizationally unique identifier (OUI)**:  This 24-bit number identifies the manufacturer of the NIC.  the IEEE assigns OUIs to NIC manufacturers.
-   **Vendor-assigned address**:  This 24-bit number uniquely identifies the Ethernet hardware.

&nbsp;

**Figure 16-6** *MAC Address Components*

![Figure 16-6 MAC Address Components](assets/images/Figure%2016-6%20MAC%20Address%20Components.jpeg)

&nbsp;

##  Virtual Local-Area Networks (VLANs)

&nbsp;

A virtual local-area network (VLAN) is a group of devices on an Ethernet network that are logically segmented by function, team, or application.  Image a university campus network and all the devices that need access to it.  It is common practice to combine into the same logical construct devices that need the same type of access to the network or that perform the same function.  For example, the student devices will probably be grouped into the student VLAN, the faculty devices into the same faculty VLAN, the finance department devices into the finance VLAN, and so on.  On top of the physical network that connects these devices, a software layer is added to separate them into different silos.  this is done following the IEEE 802.1q standard, which specifies an additional field in the data link layer frame: the 802.1q header.  this header is 4 bytes long and is wedged between the source MAC address field and the Type field, as shown in Figure 16- 7.

&nbsp;

**Figure 16-7** *Typical Ethernet Frame Versus 802.1q Ethernet Frame*

![Figure 16-7 Typical Ethernet Frame Versus 802.1q Ethernet Frame](assets/images/Figure%2016-7%20Typical%20Ethernet%20Frame%20Versus%20802.1q%20Ethernet%20Frame.jpeg)

&nbsp;

>   ***`Key Topic`***

&nbsp;

In the 802.1q header, 12 bits are dedicated to the VLAN identifier, so a maximum of 4094 VLANs can be defined on an Ethernet network; the VLANs with IDs 0 and 4095 are reserved.  Each VLAN defines its own broadcast domain.  A data link layer broadcast domain is defined as the subset of devices on a network that receive Layer 2 broadcast traffic.  Layer 2 broadcast traffic stops and is not forwarded further by Layer 3 devices or routers.  It is a best practice to keep the Layer 2 broadcast domain as small as possible.  Going back to the university campus example, imagine the thousands of devices connected ot the network as being part of the same broadcast domain.  In addition, because there is no ***Time to Live (TTL)*** field in the EThernet frames, and redundant connections are required between switches, broadcast storms might bring down the network and make it unusable.  Creating VLANs and assign the devices to specific VLANs limits the broadcast domain, reduces the change of a broadcast storm, and logically groups the devices for easier troubleshooting.  For each VLAN, a dedicated Layer 3 Ip subnet is usually allocated.  It is much easier to enforce security policies and limit access between VLANs at a Layer 3 device than it is to accomplish the same on a port-by-port basis on a switch.  No matter the physical location in the network, devices can be part of the same VLAN (see Figure 16-8).

&nbsp;

**Figure 16-8** *Virtual Local-Area Networks (VLANs)*

![Figure 16-8 Virtual Local-Area Networks (VLANs)](assets/images/Figure%2016-8%20Virtual%20Local-Area%20Networks%20(VLANs).jpeg)

&nbsp;

VLANs provide network segmentation by reduce the broadcast domains and organizational flexibility by combining devices on a network, based on the needs of the organization.

&nbsp;

##  Switching

&nbsp;

Switching is the process through which a data frame is forwarded from its source toward its destination by a Layer 2 device called a *switch*.  In a typical LAN, all devices connect to the network either through an Ethernet port available on the NIC or through a wireless NIC that connects to a wireless access point that is connected to a switch port.  In the ned, whether wired or wireless, all client devices connect to Ethernet switches.  Forwarding of data traffic between devices at Layer 2 is based on the MAC address table that is stored on each switch within the network.  the MAC address table is dynamically built and contains a list of all the MAC addresses that the switch has learned and hte switch ports on which it learned those addresses.

&nbsp;

A MAC address table on a switch might look as shown in Table 16-2.

&nbsp;

**Table 16-2** MAC Address Table

| VLAN | MAC Address | Type | Ports |
| -- | -- | -- | -- |
| 10 | 001b.10.ao.2500 | Dynamic | Gi0/1 |
| 20 | 001b.10ae.7d00 | Dynamic | Gi0/2 |
| 30 | 0050.7966.6705 | Dynamic | Gi0/3 |

&nbsp;

Based on this table, the switch can forward the Layer 2 data frames toward their destination.  If a data frame with MAC destination address 0050.7966.6705 arrives at the switch with this MAC address table, the switch will forward the frame out its GigabitEthernet0/3 port toward the host with that specific MAC address.

&nbsp;

>   ***`Key Topic`***

&nbsp;

The switch dynamically builds and maintains the MAC address table and indicates where each devices is connected in the network.  Let's assume that as witch was just rebooted, and its MAC address table is empty.  As the devices that are connected to the switch start exchanging data, the MAC address table gets populated with their addresses.  From the first device that sends data on the network, the switch looks at the source MAC address in the data frame and records it in the MAc address table, together with the port on which it received the data.  Since this is the first MAC address in the table, the switch doesn't have the destination MAc address of the frame, so it floods it over all the ports except the port on which it received the data.  As the frame gets flooded throughout the network, eventually it will get to its destination.  The destination devices replies with its own data frame, in which the source and destination MAC address get swapped.  All the other devices drop the original frame because it was not destined for them.  The switch receives the frame, takes note of the source MAC address, and records it in its table, together with the port on which it was received.  This way, the switch dynamically builds its MAc address switching table and can forward traffic between all the devices that are connected to it.

&nbsp;

#   Routing Concepts

&nbsp;

Routing, or Layer 3 packet forwarding, is the process of selecting a path through a network.  To understanding routing, you need to understand IPv4 and IPv6 addresses.  Then you can learn about the routing process itself.

&nbsp;

##  IPv4 Addresses

&nbsp;

The most common protocol at the Internet layer is Internet Protocol (IP).  The Internet, the worldwide network connecting billions of devices and users, is built on top of IP.  There are currently two versions of IP available: IP version 4 (IPv4) and IP version 6 (IPv6).  Both protocol versions are used in the Internet, and a slow migration toward IPv6 is in progress.

&nbsp;

>   ***`Key Topic`***

&nbsp;

The main role of IP is to uniquely identify devices at the Internet layer in the TCP/IP reference model and Layer 3 in the OSI model.  Ipv4 uses 32-bit addresses, which means it can theoretically support 2<sup>32</sup> (just over 4 billion) unique addresses.  It is a connectionless protocol, IP data packets are forwarded individually, the delivery of packets is best effort, and there is no retransmission or data recovery functionality specified in the protocol definition.  In case of lost or corrupt packets, retransmission and data recovery are left to be implemented by the higher-layer protocols.  Since the physical medium and transmission are handled by the data link layer, all those specifications are abstracted from the Internet layer, and IP operates independently of the medium that is carrying the data.

&nbsp;

IP addresses are similar to physical addresses of home and businesses.  The same way the address of a house uniquely identifies all the devices connected to the Internet so that data packages can be exchanged and delivered.  For easier readability for humans, Ipv4 addresses are split into four octets, with each decimal value separated by a dot - in a format known as dotted decimal notation.  Each octet is made up of 8 bits, and each bit can have a value of 1 or 0.  For example, an IP address would take the following form in the IP header: 11000000101010000011000001000001.  It is very easy to make mistakes when representing IP addresses this way.  The four-octet dotted decimal notation for the same address becomes 192.168.48.65, which is much easier to remember and keep track of.  Table 16-3 shows decimal and binary representations of this IPv4 address.

&nbsp;

**Table 16-3** IPv4 Address Representation with Decimal and Binary Values

| | | | | |
| -- | -- | -- | -- | -- |
| **Decimal** | 192 | 168 | 48 | 65 |
| **Octet/binary** | 11000000 | 10101000 | 00110000 | 01000001 |

&nbsp;

An IP address consists of two parts:

-   **Network ID**:  The network address part starts from the leftmost bit and extends to the right.  Devices on a network can communicate directly only with devices that are in the same network.  If the destination IP address is on a different network than the network the source IP address is on, a router needs to forward the traffic between the two networks.  the router maintains a routing table with routes to all the networks it knows about.
-   **Host ID**:  The host address part starts from the rightmost bit and extends to the left.  The host ID uniquely identifies a specific device connected to the network.  Although the host ID can be the same between different devices on different networks, the combination of network Id and host ID must be unique throughout the network.

&nbsp;

In order to accommodate networks of different sizes, IP addresses are organized into different classes.  There are in total five classes of IPv4 addresses.  Classes A, B, and C are available for public use; Class D is used for multicast addresses; and Class E is reserved for research and is not available for public use.  The Internet Assigned Numbers Authority (IANA) manages the assignment and allocation of IP addresses to Internet service providers (ISPs), which in turn assign IP address ranges to their customers.  the five classes of IPv4 addresses are described in Table 16-4.

&nbsp;

**Table 16-4** Classes of IPv4 Addresses

| Addresses Class | Bit Pattern of First Byte | First-Byte Decimal Range | Host Assignment in Dotted Decimal Format |
| -- | -- | -- | -- |
| A | 0xxxxxxx | 1 to 127 | 1.0.0.1 to 127.255.255.254 |
| B | 10xxxxxx | 128 to 191 | 128.0.0.1 to 191.255.255.254 |
| C | 110xxxxx | 192 to 223 | 192.0.0.1 to 223.255.255.254 |
| D | 1110xxxx | 224 to 239 | 224.0.0.1 to 239.255.255.254 |
| E | 11110xxx | 240 to 255 | 240.0.0.1 to 255.255.255.255 |

&nbsp;

Class A uses the first byte for the network Id and the other 3 bytes (or 24 bits) for the host Id.  As you can imagine, networks with 2<sup>24</sup> (more than 16 million) hosts in the same network are nonexistent; technologies such as ***classless interdomain routing (CIDR)*** and ***variable-length subnet masking (VLSM)*** have been developed to address the wastage of IPv4 addresses with the original definition of classes of IPv4 addresses.  The first bit of the first byte in a Class A IP address is always 0.  this means that the lowest number that can be represented in the first byte is 00000000, or decimal 0, and the highest number is 01111111, or decimal 127.  The 0 and 127 Class A network addresses are reserved and cannot be used as routable network addresses.  Any IPv4 address that has a value between 1 and 126 in the first byte is a Class A address.

&nbsp;

Class B uses the first 2 bytes for the network Id and the last 2 bytes for the host ID.  The first 2 bits of the first byte in a Class B IPv4 address are always 10.  The lowest number that can be represented in the first byte is 10000000, or decimal 128, and the highest number that can be represented is 10111111, or decimal 191.  Any IPv4 address that has a value between 128 and 191 in the first byte is a Class B address.

&nbsp;

Class C uses the first 3 bytes for the network ID and the last byte for the host ID.  Each Class C network can contain up to 254 hosts.  A Class C network always begins with 110 in the first byte, meaning it can represent networks from 11000000, or decimal 192, to 11011111, or decimal 223.  If an IP address contains a number in the range 192 to 223 in the first byte, it is a Class C address.

&nbsp;

The role of the address mask is to identify which portion of the IP address is the network Id part and which portion is the host ID.  Similarly to IPv4 address, address masks are also 32 bits long and use dotted decimal notation.  IPv4 addresses and address masks go together hand in hand.  Address masks specify the network ID portion of an IP address by turning the corresponding bit into a 1 and the host ID portion of the IP address by turning the corresponding address mask bit into a 0.  The default address masks for the first three classes of IPv4 address are as follows:

-   **Class A**:  The default address mask is 255.0.0.0 or /8, indicating that the first 8 bits of the address contain the network ID, and the other 24 bits contain the host ID.
-   **Class B**:  The default address mask is 255.255.0.0 or /16, indicating that the first 16 bits of the address contain the network ID, and the last 16 bits contain the host ID.
-   **Class C**:  The default address mask is 255.255.255.0 or /24, indicating that the first 24 bits of the address contain the network ID, and the last 8 bits contain the host ID.

&nbsp;

In each IP network, there are two reserved addresses.  The IP address where all the host ID bits are 0 is reserved and is used to identify the network itself.  For example, the Class C network address 192.16.1.0 cannot be assigned to any host on the network because it is used to identify the network.  This is how the network is represented in the routing tables of routers throughout the network.  The other reserved IP address is the one where all the host ID bits are 1; this address, called the ***broadcast address***, is used to send information to all the hosts on the network and cannot be assigned to any device.  In the previous example with the Class C network, the broadcast address for the that network would be 192.16.1.255.  Class C networks can accommodate and uniquely address 256 - 2 = 254 devices on each network.

&nbsp;

The Internet has experienced explosive growth, and it won't be long before IANA runs out of available IPv4 address ranges to assign.  A large number of the IPv4 address ranges that were initially allocated were also used in private networks, so IANA decided to create a group of private IPv4 address ranges for those networks.  Private IPv4 networks, defined by the ***Internet Engineering Task Force (IETF)*** in RFC 1918: *Address Allocation for Private Internets*, are meant to preserve the IPv4 address space by having dedicated networks for private networks.  Three blocks of IP addresses (1 Class A, 16 Class B, and 256 Class C Networks) are reserved for private, internal use (see Table 16-5).

&nbsp;

**Table 16-5** Private IPv4 Addresses

| Address Class | Private Network ID | Network Address Range |
| -- | -- | -- |
| A | 10.0.0.0 | 10.0.0.0 to 10.255.255.255 |
| B | 172.16.0.0 | 172.16.0.0 to 172.32.255.255 |
| C | 192.168.0.0 | 192.168.0.0 to 192.168.255.255 |

&nbsp;

IP addresses in these ranges are not routable in the Internet.  When private networks using these IPv4 addresses need to connect to the Internet, their addresses need to be translated to public, Internet-routable IPv4 addresses.  This translation process is called Network Address Translation (NAT), and it is discussed in more detail in Chapter 18, "IP Services."

&nbsp;

The need for further divide IPv4 address classes, especially the Class A and Class B networks, and to create additional subnetworks became clear as networks started to grow in size and complexity and IPv4 addresses started to run out.  As previously mentioned, a Class A network with the default address mask can address more than 16 million devices on the same network.  Having more than 16 million devices on one Layer 3 network is theoretically possible but practically impossible.  Class B networks have 16 bits dedicated ot host IDs, which means each Class B network can address 2<sup>16</sup> = 65,536 - 2 = 65,534 devices (with two addresses reserved for the network address and the broadcast address).  These networks also are in need of further subnetting.  Subnetting is the process of borrowing bits from the host Id portion of a network and transforming them into network ID bits.

&nbsp;

Classless interdomain routing (CIDR) goes beyond the class limits and the default address masks and represents a way of specifying the subnet mask for an IP address.  Initially when the classes of IPv4 addresses were defined, the default masks for each class were already implied and were not even mentioned when assigning networks for customer consumption.  As the available IPv4 addresses became more and more scarce, especially for Class A and Class B networks, CIDR was introduced as a way to capture the transition from a class-based Internet to a classless one.  In a classless Internet, it is no longer feasible to assume that the address mask for a Class A network is 255.0.0.0 or /8 or for a Class B network that is 255.255.0.0 or /16.  The purpose of the / notation is to specify how many bits in the subnet mask are dedicated to the network ID.  Network addresses can be subdivided further to create *subnets*.  This is accomplished by using variable-length subnet masking (VLSM) to indicate how many bits in an IPv4 address are dedicated to the network ID and how many bits are dedicated ot the host ID.  As an example, the 10.0.0.0 private network can be further subdivided, and new subnets can be created out of it.  Instead of having one network with more than 16 million hosts, which is not helpful in real life, 65,536 subnets with 254 hosts - each similar to 10.0.0.0/24, 10.0.1.0/24, 10.0.2.0/24, and so on - can be created out of the 10.0.0.0/8 network.  This is done by borrowing 16 bits from the 24 bits that are dedicated to host IDs and transforming them into network ID bits.  By applying a different subnet mask - using /24 instead of /8 - we can use VLSM and CIDR notation to adjust the host portion of the network address.

&nbsp;

Let's take a practical example and create new subnets for a fictitious enterprise called Acme, Inc.  the network administrator is planning on using the 192.168.0.0/24 network to address all the devices that are connected to the Acme, Inc. enterprise network.  As you would expect, there are several departments in the Acme, Inc. world, and there are different numbers of employees in each department.  Let's assume that the total number of departments is 8 and include the typical corporate organization: engineering, support, human resources, finance finance and accounting, and so on.  Acme, In. is still a small company and there are not more than 20 devices connected to the network in each of the 8 departments.  The network administrator would like to segment each department into its own network so that security can be more easily enforced by using Layer 33 access control lists (ACLs) and also a limit to the broadcast domain for each department.  The 192.168.0.0/24 CIDR notation indicates that for this subnet, there are 24 bits reserved for the network, and the rest of the bits, 8, are reserved for hosts.  In order to create 8 subnets out of the original 1, 3 bits (2<sup>3</sup> = 8) would have to be borrowed from the host portion and dedicated to the new network IDs.  The subnet mask in this case changes as follows:

-   **Original subnet mask** 11111111.11111111.11111111.00000000 (/24)
-   **New subnet mask**:  11111111.11111111.11111111.11100000 (/27)

&nbsp;

There are still 5 bits left for hosts on each subnet, which results in 2<sup>5</sup> = 32 - 2 (1 reserved for the network address and 1 reserved for the broadcast address) = 30 usable IP addresses for each subnet.  This is more than needed to accommodate the 20 devices for each department.  The new subnet looks like shown in Table 16-6; each one has a /27 mask:

&nbsp;

**Table 16-6** Creating Additional Subnets from 192.168.0.0/24

| Subnet | Network Address | Broadcast Address | Available Host Address Range|
| -- | -- | -- | -- |
| Subnet 1 | 192.168.0.0 | 192.168.0.31 | 192.168.0.1 to 192.168.0.30 |
| Subnet 2 | 192.168.0.32 | 192.168.0.63 | 192.168.0.33 to 192.168.0.62 |
| Subnet 3 | 192.168.0.64 | 192.168.0.95 | 192.168.0.65 to 192.168.0.94 |
| Subnet 4 | 192.168.0.96 | 192.168.0.127 | 192.168.0.97 to 192.168.0.126 |
| subnet 5 | 192.168.0.128 | 192.168.159 | 192.168.0.129 to 192.168.0.158 |
| Subnet 6 | 192.168.0.160 | 192.168.0.191 | 192.168.0.161 to 192.168.0.190 |
| Subnet 7 | 192.168.0.192 | 192.168.0.223 | 192.168.0.193 to 192.168.0.222 |
| Subnet 8 | 192.168.0.224 | 192.168.0.255 | 192.168.0.225 to 192.168.0.254 |

&nbsp;

New subnets can be easily created to accomodate any number of devices.  In the previous example, each subnet can address up to 330 devices, but the subnets can be further subnetted, if needed.  By borrinwg additional bits from the host section, subnet masks of /28, /29, and even /330 can be specified to create new subnets for 2<sup>4</sup> = 16 - 2 = 14, 2<sup>3</sup> = 8 - 2 = 6, or 2<sup>2</sup> = 2 - 2 = 2 hosts in each subnet.  /30 subnets are specifically useful on point-to-point serial connections between two routers - for example, where there are only 2 devices connected and there is no point in using larger subnets as that would only lead to wasted addresses.  table 16-7 provides a breakdown of the subnet masks from /24 to /32, their binary representations, and the number of subnets and hosts for each subnet. 

&nbsp;

**Table 16-7** Subnet Mask Representations and the Number of Subnets and Hosts for Each

| Decimal Subnet Mask | Binary Subnet Mask | CIDR | Subnets | Hosts per Subnet |
| -- | -- | -- | -- | -- |
| 255.255.255.255 | 11111111.11111111.111111111.11111111 | /32 | None | N/A |
| 255.255.255.254 | 11111111.11111111.111111111.11111110 | /31 | None | N/A |
| 255.255.255.252 | 11111111.11111111.111111111.11111100 | /30 | 64 | 2 |
| 255.255.255.248 | 11111111.11111111.111111111.11111000 | /29 | 32 | 6 |
| 255.255.255.240 | 11111111.11111111.111111111.11110000 | /28 | 16 | 14 |
| 255.255.255.224 | 11111111.11111111.111111111.11100000 | /27 | 8 | 30 |
| 255.255.255.192 | 11111111.11111111.111111111.11000000 | /26 | 4 | 62 |
| 255.255.255.128 | 11111111.11111111.111111111.10000000 | /25 | 2 | 126 |
| 255.255.255.0 | 11111111.11111111.111111111.00000000 | /24 | 1 | 254

&nbsp;

##  IPv4 Addresses

&nbsp;

IPv4 has valiantly served the Internet from the early days, when only a handful of devices were interconnected at college campuses in the United States for research purposes, to today, when billions of devices are interconnected and exchanging massive amounts of data.  The longevity of IPv4 and the addressing scheme it defines is a testament to how robust and scalable IP actually is.  Even so, IPv4 faces limitations, including the insufficiency of 32-bit addresses, the need for the IP header to be streamlined and simplified, and the need for security embedded in the protocol rather than implemented as an afterthought.

&nbsp;

IPv6 is an evolutionary upgrade to IP that is meant to address most of the shortcomings of IPv4.  IPv6 is defined in RFC 2460, *Internet Protocol, Version 6 (IPv6) Specification,* issued by the IETF.  Several other RFCs that hve been created following the initial definition describe the architecture and services supported by IPv6.  IPv6 addresses are 128 bits long instead of 32 bits.  The 128 bits provides $3.4 \times 10^{38}$ addresses; this is the equivalent of a full IPv4 addressing space for each living person on Earth.  Currently both IPv4 and IPv6 addresses are supported ont he Internet, and gradual transition to only IPv6 is happening, but we won't be there until sometime far in the future.  Several migration technologies have been developed to ease the transition from IPv4 to IPv6.  The dual-stack method involves having both IPv4 and and IPv6 addresses configured on the same interface and seems to be the most popular option.  Tunneling mechanisms are also available for IPv4 tunneling over IPv6 networks and IPv6 tunneling over IPv4 networks.

&nbsp;

>   ***`Key Topic`***

&nbsp;

IPv6 brings several improvements compared to IPv4, including the following:

-   Larger address space means improved global reachability and better aggregation of IP prefixes, which leads to smaller routing tables, which leads to faster routing.
-   End-to-end communication is now possible, as there is no need for technologies such as Network Address Translation (NAT) or Port Address Translation (PAT) that have been developed to address the lack of public IPv4 addresses.
-   Address autoconfiguration allows hosts and devices connecting to the network to easily and automatically obtain IPv6 addresses.  This is especially important for mobile devices as they roam between different networks; autoconfiguration makes the transition seamless.
-   The coexistence of multiple addresses on the same interface increases reliability and load balancing.
-   A simplified header means better routing efficiency and increased forwarding performance.
-   No broadcast addresses and no broadcast traffic mean no broadcast storms, improving the reliability of the whole network.
-   Security is increased, thanks to built-in IPsec capabilities.

&nbsp;

IPv6 addresses can be displayed as 32 hexadecimal characters split into 8 sections, as follows:

-   Colons separate entries *x:x:x:x:x:x:x:x*, where *x* is a 16-bit hexadecimal field.
-   Hexadecimal characters are case insensitive.
-   Leading zeros in a field are optional.
-   Successive fields of zero can be represented as :: once per address.

&nbsp;

An example of an IPv6 address is 2031:0000:120F:0000:0000:09C0:9A73:242C.  Following the guidelines just specified, this address can also be written as follows:

-   2031:0000:120F::9C0:9A73:242C (because successive fields of zero can be represented as ::)
-   2031:0:120F::9C0:9A73:242C (because leading zeros in a field are optional)

&nbsp;

Figure 16-9 shows a simple illustration of how IPv6 addresses and subnetting work.

&nbsp;

**Figure 16-9** *IPv6 Subnetting*

![Figure 16-9 IPv6 Subnetting](assets/images/Figure%2016-9%20IPv6%20Subnetting.jpeg)

&nbsp;

The Internet Assigned Numbers Authority (IANA) is the organization that manages the assignment of IPv6 addresses at a global level.  IANA assigns /23 blocks of IPv6 addresses to the registries that manage IPv6 addresses at a regional level, such as the Asia-Pacific Network Information Center (APINIC) or the American Registry for Internet Numbers (ARIN).  The regional registries assign /32 blocks of IPv6 addresses to the Internet service providers (ISPs) that operate in their geographic areas.  The ISPs, in turn, assign /48 IPv6 subnets to their customers, which can subnet further and create their own subnets, usually down to a /64, giving them up to 65,536 IPv6 subnets that they can assign to their sites. 

&nbsp;

The interface ID portion of an IPv6 address is usually base don the MAc address of the device, following the EUI-64 specification.  This specification creates the 64 bits needed for the interface ID portion fo the address by splitting the 48-bit MAC address right down the middle and inserting the 16-bit oxFFFE between the OUI and the vendor-assigned bits.

&nbsp;

The hierarchical distribution of IPv6 addresses allows for better aggregation of routes, which leads to smaller Internet routing tables and faster routing.

&nbsp;

>   ***`Key Topic`***

&nbsp;

There are several different types of IPv6 addresses:

-   Global
-   Link-local
-   Multicast
-   Loopback
-   Unspecified

&nbsp;

**Global** IPv6 addresses are the equivalent of public unicast IPv4 addresses.  global IPv6 addresses are assigned in a controlled fashion so that they can be easily aggregated at all levels, registry, ISPs, and customers.  Currently IANA is assigned IPv6 addresses that started with the binary value 001 (2000::/3).  This represents one-eighth of the total IPv6 address space.  A global unicast IPv6 address typically consists of a 48-bit global routing prefix in the most significant portion of the address, followed by a 16-bit subnet ID and 64-bits dedicated to the interface identifier.  Addresses with prefixes in the range 2000::/3 to E000::/3 are required to have 64-bit interface identifiers that follow the EUI-64 format mentioned previously.

&nbsp;

**Link-local** addresses in IPv6 are a new concept compared to IPv6.  These addresses refer only to a particular physical link and are not forwarded by routers.  They are used only for local communication between devices on the same physical network segment.  Link-local addresses are part of the link-local prefix FE80::/10 and are extensively used in IPv6 routing protocols for neighbor and router discovery, as well as in automatic address configuration.  They are usually dynamically created on all IPv6 interfaces by adding the 64-bit interface ID to the FE80::/10 prefix.

&nbsp;

IPv6 **multicast** addresses are part of the FF00::/8 prefix.  There is no broadcast traffic in IPv6, so that functionality is taken by multicast and anycast traffic in IPv6.  There are several reasons broadcast traffic has been left out of IPv6, including the fact that each broadcast packet on the network generates an interrupt on all the devices that are part of the same broadcast domain, even if the traffic is not directly meant fro them; in addition, broadcast storms can bring down entire networks.  With IPv6, it was decided to implement the one-to-many type of data traffic by using multicast.  Multicast increases the efficiency of delivering data from one device to many, and with IPv6, it gets a larger address space, too.  A data packet sent to a multicast address is delivered to all interfaces identified by the multicast address.  Multicast addresses also have scope.  The scope of a multicast address can be that of a node, a link, a site, an organization, or a global scope and is represented by a scope parameter of 1, 2, 5, 8 or E, respectively.  As an example, the multicast address with the prefix FF02::/16 is a multicast address with a link scope.  All devices implementing IPv6 are required to join the all-nodes multicast group with the FF02:0:0:0:0:0:0:1 multicast address.  IPv6 routers must also join the all-routers multicast group FF02:0:0:0:0:0:0:2.  The scope on both of these multicast addresses is link-local.

&nbsp;

**Loopback** IPv6 addresses are similar to the loopback addresses in IPv4: They are used for testing local traffic on a device.  In IPv6 there is only one address dedicated for this purpose: 0:0:0:0:0:0:0:1 (or ::1 when using the zero compression feature in IPv6).

&nbsp;

The **unspecified** address is used for situations when a device doesn't have any IPv6 address assigned and needs to populate the Source field when sending a datagram on the network, such as when obtaining an IPv6 from a DHCPv6 server.  This address is the all-zeros address: 0:0:0:0:0:0:0:0 (or just :: when using the zero compression feature in IPv6)

&nbsp;

**Anycast** addresses are allocated from the unicast global space.  Their purpose is to accommodate the one-to-nearest data traffic requirement.  In this case, multiple devices share the same unicast address, and data traffic that is destined for the anycast address is routed through the network to the closest device that has that anycast address configured on one of its interfaces.  In this case, of course, all the anycast nodes have to provide a similar, uniform service.  Anycast is suitable for load balancing and content delivery services.  An example of a service that can be implemented using anycast addresses is Domain Name System (DNS).  DNS is covered in Chapter 18; for the purpose of this example, you just need to know that DNS is a critical component of the Internet and is mainly used to resolve domain names to IP addresses.  Configuring several DNS servers on a network with the same anycast address ensures a consistent DNS configuration on all the devices in the network.  Instead of having to configure several different DNS server IP addresses for redundancy purposes, in IPv6, a single address, the anycast address, can be configured on all DNS clients.  As long as at least one of the DNS servers that have been configured as part of the anycast group is online, DNS redundancy is guaranteed.

&nbsp;

##  Routing

&nbsp;

Routing is the process of selecting a path through a network.  This functionality is performed by routers, which are devices made to interconnect networks, find the best paths ofr data packets from their source toward their destination, and route data based on a routing table.  As switches have a critical role at Layer 2 in connecting devices in the same physical area and creating local-area networks, routers have a critical role at Layer 3 in interconnecting networks and creating wide-area networks.  The main functions of a router are the following:

-   Path determination
-   Data packet routing or forwarding

&nbsp;

Path determination is the process through which routers look up information in their routing tables to determine where to forward the data packets received on their interfaces.  In a typical scenario, a router has at least two interfaces - and usually more.  Each interface connects to a Layer 33 network, which means the interface on the router is configured with an IP address in that network.  In most cases, the router acts as the default gateway for that Layer 3 network, meaning that any traffic that is not destined for the local network will be forwarded to the router, and the router will forward it further toward its destination.  Each router maintains its own routing table, which contains a list of all the destination or networks that are known to the router and how to reach those destinations.  When receiving a packet on one of its interfaces, the router checks the destination IP address in the data packet header and looks up the best match for that destination in its routing table.  If the destination IP address matches one of the networks in the routing table, it means that either the network is directly connected to the router or it can be reached via another router that is directly connected, and it becomes the next-hop router toward the final destination of the data packet.  If there is no match for that destination IP address in the routing table, the router sends the data packet to the default route, and if there is no default route, the router drops the data packet.

&nbsp;

After determining the correct path for the packet, the router forwards the packet through a network interface toward the destination.  Figure 16-10 shows a simple network diagram.

&nbsp;

**Figure 16-10** *Simple Network Diagram*

![Figure 16-10 Simple Network Diagram](assets/images/Figure%2016-10%20Simple%20Network%20Diagram.jpeg)

&nbsp;

The routing table for the network in Figure 16-10 might look like Table 16-8.

&nbsp;

**Table 16-8** Routing Table

| Network | Interface or Next Hop |
| -- | -- |
| 10.10.0.0/24 | directly connected: Gi0/0 |
| 10.10.1.0/24 | directly connected: Gi0/1 |
| 10.10.2.0/30 | directly connected Se:0/0/0 |
| 0.0.0.0/0 | via 10.10.2.2 (next-hop router) |

&nbsp;

Each row in the routing table lists a destination network and the corresponding interface or next-hop address.  For directly connected networks, the router has has an interface that is part of that network.  For example, let's assume that a router receives a data packet on its GigabitEthernet0/1 interface with destination IP address 10.10.0.15.  The router looks up the destination address in its routing table and decides to route the packet out its GigabitEthernet0/0 interface toward the destination.

&nbsp;

Following the same logic, let's assume next that the router receives a packet on its GigabitEthernet0/0 interface with destination IP address 172.16.0.25.  The router performs a routing table lookup and finds that it doesn't have an explicit route for that network, but it does have a default route (0.0.0.0/0) via the next-hop router with IP address 10.10.2.2.  Looking up recursively how to reach the 10.10.2.0 network, the router forward the packet out its Serial0/0/0 interface toward the next-hop router, which should be closer to the destination.  Default routes on routers - much like the default gateway configuration on end host devices - are used as a last resort for routing any data packets for which the destination doesn't explicitly exist in the routing table.  Default routes are extremely helpful in maintaining a small routing table and hence decreasing the routing table lookups and also decreasing the amount of time needed to decide on which interface to route the traffic, leading to faster routing of data packets.  For the majority of routers, a full Internet routing table with hundreds of thousands of routes is not necessary, and a default route towards the next hop is sufficient.

&nbsp;

>   ***`Key Topic`***

&nbsp;

There are several ways in which routing tables are populated:

-   Directly connected networks
-   Static routes
-   Dynamic routes
-   Default routes

&nbsp;

We've already discussed **directly connected networks**, in which the router has an interface configured for that network and its routing traffic for it and the default routes, which are used as a last resort in the event that a more specific route doesn't exist in the routing table.

&nbsp;

**Static routes** are configured manually bt the network administrator or the person managing a router.  In small networks in which there are not expected to be any changes, static routes can work just fine.  In larger networks that are more dynamic in nature, with devices and routers going offline and coming online constantly, static routes do not work very well because the administrator needs to manually change the entries as the changes happen in the network.  A much more scalable solution in this case is dynamic routes.

&nbsp;

**Dynamic routes**, as the name implies, are learned dynamically through specialized software applications called ***dynamic routing protocols***.  Several routing protocols have been developed over the years, including ***Open Shortest Path First (OSPF)***, ***Enhanced Interior Gateway Routing Protocol (EIGRP)***, ***Routing Information Protocol (RIP)***, ***Border Control Protocol (BGP)***, and ***Intermediate System-to-Intermediate System (IS-IS)***.  Each of these protocols has its own characteristics, advantages, adn drawbacks.  It is the role of the network administrator to decide which protocol to choose to run on the network and to determine whether a dynamic routing protocol is even necessary in the first place.  Medium and large networks run at least one of these protocols on all the routers in the network.  The routers running dynamic routing protocols exchange data between them and dynamically build their routing tables based on the information they receive from their neighbor routers.  If multiple routing protocols are configured on the routers, there needs to be a way to decide which routes to choose and to populate the routing table with them.  Each routing protocol has an administrative distance associated with it that is based on the trustworthiness of the protocol.  For example, if a route for the same network is learned through RIP and OSPF, the OSPF route will take precedence as OSPF has a lower administrative distance than RIP.  A lower administrative distance means a higher degree of trust in that source - so a higher chance of getting added to the routing table.

&nbsp;

Connected routes, meaning the router has an interface configured in a specific network, have the lowest administrative distance (AD), 0.  Static routes are preferred next as they usually have an AD of 1.  Routing protocols have different administrative distance values; for example, BGP has an AD of 20, and RIP has an AD of 120.  These values for AD are default values, and they can be changed if additional tweaking of the routing table is necessary.  All dynamic protocols mentioned support routing for both IPv4 and IPv6.

&nbsp;

As we've seen previously in this chapter, the Internet has become classless, and there are a large number of networks and subnets that can be created from those networks.  The same way that a large network address space can be subdivided into small subnet,s the reverse process is also available; it is called ***supernetting***.  This means that smaller subnets can be combined into a larger network, and instead of having several routing table entries for each individual subnet, a single routing table entry can encompass them all.  For example, when an ISP assigns a certain prefix range to one of its customers, the ISP does not need to know all the details of how the customer is implementing subnetting in its internal network.  All the ISP needs to know is that the whole prefix is assigned to the customer, and it can be reached via the customer's border routers.  Supernetting is critical in maintaining an Internet routing table of manageable size.

&nbsp;

Another important aspect when building a routing table is the longest prefix match concept.  Longest prefix match means that when the router is looking in the routing table for a match to route the data packet toward its destination, it does so by trying to match it to the longest prefix it has in the table.  For example, let's assume that the routing table has two entries: 10.10.10.0/24 via interface GigabitEthernet0/0 and 10.10.0.0/16 via interface GigabitEthernet0/1.  If the router receives a data packet destined for 10.10.10.15, it looks in its routing table, and it will match the longest-prefix network (in this case, 10.10.10.0/24) and route the packet out of its GigabitEthernet0/0 interface.  If the data packet has destination address 10.10.20.15, the router matches the other entry, 10.10.0.0/16, since that is the longest prefix match it has for that subnet.