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

&nbsp;

>   ***`Key Topic`***

&nbsp;

**Table 12-2** NETCONF Operations

| Operation | Description |
| -- | -- |
| \<get> | Retrieve running configuration and device state information |
| \<get-config> | Retrieve all or part of the specified configuration data store |
| \<edit-config> | Load all or part of a configuration to the specified configuration data store |
| \<copy-config> | Replace an entire configuration data store with another |
| \<delete-config> | Delete a configuration data store |
| \<commit> | Copy the candidate data store to the running data store |
| \<lock> / \<unlock> | Lock or unlock the entire configuration data store system |
| \<close-session> | Gracefully terminate the NETCONF session |
| \<kill-session> | Forcibly terminate the NETCONF session |

&nbsp;

The NETCONF \<edit-config> operation supports several attributes:

-   **merge**:  When this attribute is specified, the configuration data is merged with the configuration at the corresponding level in the configuration data store.  This is the default behavior.
-   **replace**:  The configuration data replaces any related configuration in the configuration data store.  Only the configuration that is present in the config parameter is affected.
-   **create**:  The configuration data is added to the configuration only if the configuration data does not exist on the device.  If the configuration already exists, an \<rpc-error> message is returned with the \<error-tag> value data-exists.
-   **delete**:  When this attribute is specified, the configuration data is deleted from the configuration data store.

&nbsp;

>   ***`Key Topic`***

&nbsp;

NETCONF defines the existence of one or more configuration data stores and allows configuration operations on these data stores.  A configuration data store is a set of configuration data that is needed to get the device from its default initial state into a desired operational state.  The configuration data stores do not contain operational data.  

&nbsp;

Three types of configuration data stores are defined in NETCONF:

-   **running**:  This data store holds the complete configuration currently active on the network device.  Only one running data store can exist on a device, and it is always present.  NETCONF protocol operations refer to this data store with the \<running> XML element.
-   **candidate**:  This data store acts as a workplace for creating and manipulating configuration data.  A \<commit> operation causes the configuration data contained in it to be applied to the running data store.
-   **startup**:  This data store contains the configuration data that is loaded when the device boots up and comes online.  An explicit \<copy-config> operation from the \<running> data store into the \<startup> data store is needed to update the startup configuration with the contents of the running configuration.

&nbsp;

The existence of these data stores is advertised by the NETCONF device through capabilities.  When opening a new session with a NETCONF server, the first message that is sent by the server contains a list of all the capabilities that the server supports.

&nbsp;

The information that can be retrieved from a NETCONF server is separated into two classes:  configuration data and state data or operational data.  Configuration data is the set of writable data that starts in the system operations; operational data, also known as the read-only status data, is the non-configuration data of the system (for example, interface traffic statistics, power supply status, etc).

&nbsp;

# YANG

&nbsp;
As mentioned in RFC 6020, YANG is "a data modeling language used to model configuration and state data manipulated by the Network Configuration Protocol (NETCONF), NETCONF remote procedure calls, and NETCONF notifications."  The main motivation behind YANG was to provide a standard way to model configuration and operational data so that the network devices can be configured and monitored in a standard and common way.  While CLI configuration and monitoring of network devices is user friendly, it is not necessarily network automation friendly.  Different network vendors have different CLIs with different features and capabilities.  Trying to find a standard way to automate the configuration and monitoring of a heterogenous network with devices from different vendors was almost impossible before NETCONF and YANG data models were created.

&nbsp;

>   ***`Key Topic`***

&nbsp;

YANG is a language used to model data for the NETCONF protocol.  A YANG module defines a hierarchy of data that can be used for NETCONF-based operations.  It allows a complete description of all data sent between a NETCONF client and server.  YANG models the hierarchical organization of data as a tree in which each node has a name and either a value or a set of child nodes.  YANG provides a clear and concise descriptions of the nodes, as well as the interaction between those nodes.

&nbsp;

YANG strikes a balance between high-level data modeling and low-level bits-on-the-wire encoding.  The reader of a YANG module can see the high-level view of the data model and understand how the data will be encoded in NETCONF operations.

&nbsp;

YANG structures data models into modules and submodules.  A module can import data from external modules, and it can include data from submodules.  The hierarchy can be augmented, allowing one module to add data nodes to the hierarchy defined in another module.

&nbsp;

A YANG module contains three types of statements:

-   Module-header statements describe the module and give information about it.
-   Revision statements provide information about the history of the module.
-   Definition statements are the body of the module, where the data model is defined.

&nbsp;

A NETCONF server may implement a number of modules, which is the most common implementation for the Cisco devices that support NETCONF, or it might implement only one module that defines all the available data.

&nbsp;

YANG is expressed in XML, meaning that an instance of a YANG model is an XML document.

&nbsp;

YANG defines a set of built-in types and has a mechanism through which additional types can be defined.  There are more than 20 base types fot start with, including the ones in Table 12-3.

&nbsp;

**Table 12-3** YANG Built-in Data Types

| Data Type | Description |
| -- | -- |
| binary | Binary data |
| bits | Set of bits |
| boolean | True or false |
| decimal64 | 64-bit signed decimal number |
| empty | No value |
| enumeration | Enumerated strings |
| int8/16/32/64 | Integer |
| uint8/16/32/64 | Unsigned integer |
| string | Unicode string |

&nbsp;

The **typedef** YANG statement can be used to define derived types from base types.  In the following example, a new data type called **percent** is created by limiting a 16-bit unsigned integer value to a range from 0 to 100:

```
typedef percent {
     type uint16 {
          range "0 .. 100";
}
Description "Percentage":
}
```

&nbsp;

This new type of data can then be used when building the YANG models.  It is common practice to have definitions of new types of data contained in a YANG submodule that will then be imported in the main YANG module.  IETF has also defined in RFC 6021 a large number of YANG types that are commonly used in networking.  These data types are organized in the **inet-yang-types** module.  The following are some of the many data types defined in this RFC:

-   ipv4-address
-   ipv6-address
-   ip-prefix
-   domain-name
-   uri
-   mac-address
-   port-number
-   ip-version
-   phys-address
-   timestamp
-   date-and-time
-   flow-label
-   counter32/64
-   gauge32/64

&nbsp;

When building YANG modules, the **import** statement can be used to make all these data types available in the new model:

```
import "ietf-yang-types" {
    prefix yang;
}
```

&nbsp;

When importing an external YANg module, the **prefix** statement defines the prefix that will be used when accessing definitions inside the imported module.  for example, in order to reference the IPv4 address data type from the newly imported **ietf-yang-types** module, you can use the following statement:

`type yang:ipv4-address;`

&nbsp;

>   ***`Key Topic`***

&nbsp;

YANG defines four types of nodes for data modeling:

-   Leaf nodes
-   Leaf-list nodes
-   Container nodes
-   List nodes