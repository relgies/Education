# Foundation Topics

&nbsp;

Traditionally, network devices were managed almost exclusively through ***command-line interfaces (CLIs)***.  For network monitoring, ***Simple Network Management Protocol (SNMP)*** is still widely used.  While CLis are extremely powerful, they are also highly proprietary - different from vendor to vendor - and human intervention is required to understand and interpret their output.  Also, they do not scale for large network environments.  SNMP also has limitations, as discussed later in this chapter.  A common standard way of managing and monitoring network devices was needed.  Data modeling is replacing manual configuration as it provides a standards-based, programmatic method of writing configuration data and gathering statistics and operational data from devices.  YANG data models have been developed specifically to address the need for standardization and commonality in network management.  Model-drive programmability enables you to automate the ocnfiguraiton and control of network devices.

&nbsp;

***Cisco IOS XE, a network operating system for enterprises, Cisco NX-OS, a network operating system for data centers, and Cisco IOS XR, a network operating system for service providers, support three standards-based programmable interfaces for operating on the YANG data models: NETCONF, RESTCONF, and gRPC.***

&nbsp;

>   ***`Key Topic`***

&nbsp;

When a client request is received via NETCONF, RESTCONF, or gRPC, it is first converted into an abstract message object.  Based on the namespace in the request, the message object is delivered to the underlying model infrastructure, where it is processed and executed on the device data store.  The results are returned to the client through the agent on which the request was received.  **gRPC is an open-source project started by Google to provide a modern ***remote procedure call (RPC)*** framework that can be used in any environment - not just for network configuration.**  More details about it can be found at grpc.io.  NETCONF and RESTCONF are discussed in detail in this chapter.  Figure 12-1 shows all the protocols that Cisco devices support for model-driven programmability.

&nbsp;

**Figure 12-1** *Model-Driven Programmability on Cisco Devices*

![Figure 12-1 Model-Driven Programmability on Cisco Devices](assets/images/Figure%2012-1%20Model-Driven%20Programmability%20on%20Cisco%20Devices.jpeg)

&nbsp;

# NETCONF

&nbsp;

In an effort to better address the concerns of network operators, the ***Internet Engineering Task Force (IETF)*** and the ***Internet Architecture Board (IAB)*** set up a workshop on network management in 2022.  Several network operators were invited, and workshop participants had a frank discussion about the status of the network management industry as a whole.  The conclusions and results of that workshop were captured in RFC 3535.  Up to that point the industry had been extensively using Simple Network Management Protocol (SNMP) for network management.  SNMP is discussed in more detail in Chapter 18, "IP Services," but for the purpose of this chapter, you just need to know that SNMP is a network management protocol that was initially developed in the late 1980s.  The intention with SNMP was to create a protocol to help with both configuration and monitoring of network devices.  Several iterations of the protocol have been developed through the years, and version 3 is the latest one.  SNMP has been extensively implemented by network vendors in their devices and used by network operators.  By the middle of 2002, when the IETF/IAB workshop took place, the advantages and shortcomings of SNMP were clear.  SNMP had proved to work reasonable well for monitoring devices, especially when small amounts of information needed to be retrieved.  For configuration purposes, however, the protocol had pretty much failed for a variety of reasons, including lack of writable MIBs, security concerns, and scaling constraints.  By comparing SNMP with other network management options, such as CLIs, HTTP, and XML, network operators came up with a list of requirements for the network management technology of the future.  Some of the requirements are summarized in the following list:

-   This new network management technology should be easy to use.
-   There should be a clear distinction between configuration data and operational data.
-   It should be possible to configure extensive network services as a whole (such as IPTV and Layer 3 VPNs) instead of just configuring a network device by device.
-   Configuration transactions and easy rollback in the vent of failure should be supported.
-   There should be a standard and consistent representation of the network configuration commands between different vendors.
-   A distinction between candidate and active configurations should exist,t meaning that devices should be able to hold multiple configurations and activate them as needed.

&nbsp;

>   ***`Key Topic`***

&nbsp;

Based on these requirements, the IETF developed ***Network Configuration Protocol (NETCONF)***.  **The NETCONF protocol specifies the means of opening a secure management session with a network device, includes a set of operations to manipulate the configuration data and retrieve the operational state, and describe a mechanism to send out notifications.**  NETCONF was initially defined in 2006 in RFC 4741 and updated in 2011 with RFC 6241.  **While the NETCONF protocol specifies the mechanism to establish a connection and exchange data between a network administrator and a device, it does not define the actual format of the data.**  **This is the role of the ***YANG (Yet Another Next Generation)*** data modeling language, which was defined by the IETF in 2010 in RFC 6020 specifically to be used with NETCONF.**

&nbsp;

YANG proved to be so successful and powerful that it has evolved to be used as a general-purpose data modeling language in different programming environments.  A data model is simply a well-understood and agreed upon method to describe something.  As an example, let's consider a simple data model for a person.  A person can be classified based on gender (male or female), height (feet/inches, meters/centimeters), weights (pounds, kilograms), hair (brown, blond, black, bald, other), and eye color (brown, blue, green, other) - to name just a few characteristics.  Using this generic data model for a person, you can describe an individual in a way that is easy for others to understand.  If I tell you Amy is a woman who is 5'8" and 160 pounds with blond hair and blue eyes, you can very easily interpret and understand this data model information for a person.

&nbsp;

The NETCONF protocol defines transports over SSH and includes operations and configuration data stores that allow for the management of network devices.  NETCONF authentication options are the same as for any SSH communication.  Username and password as well as SSL certificates can be used, just as SSH is used with CLI commands.

&nbsp;

NETCONF uses a client/server communication model.  The server side is implemented on the network device through a NETCONF agent that acts as a northbound API.  Clients connecting to the agent send partial or complete configuration data and receive state and operation data from the device.  Any system that implements the protocol can be a client; some common ones are Cisco NSO and the ncclient Python library.

&nbsp;

>   ***`Key Topic`***

&nbsp;

Figure 12-2 shows the NETCONF architecture stack and the relationship with YANG

&nbsp;

**Figure 12-2** *NETCONF*

![Figure 12-2 NETCONF](assets/images/Figure%2012-2%20NETCONF.jpeg)

&nbsp;

The main purpose of NETCONF is to transport data payloads between client and server.  The data payloads can be configuration data, operational and status data, and notifications.  NETCONF supports notifications, which are similar to SNMP trapts.

&nbsp;

Messages sent with NETCONF use remote procedure calls (RPCs), a standard framework for clients to send a request to a server to perform an action and return the results.  The client or the manager application sends its XML-formatted message to the server, nesting the request within an \<rpc> XML element, and the server returns results within an \<rpc-reply> element.

&nbsp;

As previously mentioned, the first version of NETCONF was defined in 2006, but YANG was not defined until 2010.  So what was used as a payload with the first version of NETCONF?  Configuration payloads in those days defaulted to CLI commands.  This was an advantage as new features exposed with new CLI commands were available over NETCONF right away; at the same time, this brought all the drawbacks of CLI to network automation, including unstructured data and vendor-specific proprietary CLI commands.  YANG was created as a standard way to define common data models for NETCONF. 

&nbsp;

NETCONF provides a set of operations to manage device configurations and retrieve status information.  These operations include retrieving, configuring, copying, and deleting configuration data stores and retrieving operational data.  Depending on the NETCONF capabilities that are advertised by a device, additional operations can be supported.  Table 12-2 shows a common set of NETCONF operations.