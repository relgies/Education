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

```
type yang:ipv4-address;
```

&nbsp;

>   ***`Key Topic`***

&nbsp;

YANG defines four types of nodes for data modeling:

-   Leaf nodes
-   Leaf-list nodes
-   Container nodes
-   List nodes

&nbsp;

The simplest component of a YANG module is the leaf node.  A leaf node has one value of a specific type.  The following definition of an interface name is an example of a leaf node:

```
leaf intf-name {
    type string;
    description "The name of the interface";
}
```

&nbsp;

The instantiation of this leaf node - also known as the wire representation - in a NETCONF message includes only the XML element and its value:

```
<intf-name>GigabitEthernet0/0</intf-name>
```

&nbsp;

A leaf-list is a series of leaf nodes of a specific type.  The following list of trunk interfaces is an example ofa leaf-list:

```
leaf-list trunk-interfaces {
    type string;
    description "List of trunk interfaces";
}
```

&nbsp;

The NETCONF XML instantiation of this model on the wire would look like this:

```
<trunk-interfaces>TenGigabitEthernet0/1</trunk-interfaces>
<trunk-interfaces>TenGigabitEthernet0/2</trunk-interfaces>
<trunk-interfaces>TenGigabitEthernet0/3</trunk-interfaces>
<trunk-interfaces>TenGigabitEthernet0/4</trunk-interfaces>
```

&nbsp;

A container is used to group related nodes within a subtree.  It has only child nodes and no value.  A container can contain any number of child nodes of any type.  Example 12-1 shows a container called **statistics** that contains four leaf nodes of different types:

&nbsp;

**Example 12-1** *YANG Container Example*

```
container statistics {
     description "A collection of interface statistics.";
     leaf in-octets {
              type yang:counter64;
              description "The total number of octets received on the interface.";
     }
     leaf in-errors {
              type yang:counter32;
              description "Number of inbound packets that contained errors.";
     }
     leaf out-octets {
              type yang:counter64;
              description "The total number of octets sent out on the interface.";
     }
     leaf out-errors {
              type yang:counter32;
              description "Number of outbound packets that contained errors.";
     }
}
```

&nbsp;

The XML instantiation of this model is the following:

```
<statistics>
     <in-octets>5983247896</in-octets>
     <in-errors>2578</in-errors>
     <out-octets>678845633</out-octets>
     <out-errors>0</out-errors>
</statistics>
```

&nbsp;

The last type of node that is used for data modeling in YANG is the list.  A list defines a sequence of list entries.  Each entry is a record instance and is uniquely identified by the value of its key leaves.  A list can be thought of as a table organized around the key leaf with all the leaves are rows in that table.  For example, the user list in Example 12-2 can be defined as having three leaves called **name**, **uid**, and **full-name**, with the name **leaf** being defined as the key leaf.

&nbsp;

**Example 12-2** *YANG List Example*

```
list user {
    key name;
    leaf name {
        type string;
    }
    leaf uid {
        type uint32;
    }
    leaf full-name {
        type string;
    }
}
```

&nbsp;

An instantiation of this data model on the wire might look in this case as shown in Example 12-3.

&nbsp;

**Example 12-3** *Instantiation of the YANG List*

```
<user>
    <name>john</name>
    <uid>1000</uid>
    <full-name>John doe</full-name>
</user>
<user>
    <name>jeanne</name>
    <uid>1001</uid>
    <full-name>Jeanne Doe</full-name>
</user>
```

&nbsp;

We could combine all the nodes discussed so far to create a rudimentary YANG data model.  Let's call this module **bogus-interfaces**.  The data model defined in this module will be saved in a file that has to match the module name.  In this case, the file that will contain the module will have to be called **bogus-interfaces.yang**.

&nbsp;

There are several components that go into building the YANG data model, as shown in figure 12-3.

&nbsp;

>   ***`Key Topic`***

&nbsp;

**Figure 12-3** *YANG Module Components*

![Figure 12-3 YANG Module Components](assets/images/Figure%2012-3%20YANG%20Module%20Components.jpeg)

&nbsp;

The YANG header contains the namespace for the module.  The namespace is used to uniquely identify each module on a system that implements NETCONF.  Next, the prefix is used as short notation for the module, so that it can be more easily referenced, if needed.  The namespace and prefix statements in YANG have exactly the same role as in XML documents.  (Keep in mind that YANG is an XML schema definition language.)  The header also includes identifying information such as the name of the organization that created the module, contact information, a short description, and revision information.  Revision information is particularly of interest; as the model evolves, the revision information will change.  This way, a user can distinguish between different version of the data model.

&nbsp;

A section of imports and includes follows the header.  In this section of the module, information contained in additional modules and submodules is included, if needed.  **import** is used to refer to destinations in another YANG module.  It pulls references from the YANG module but does not actually pull in the body of the file that's being imported.  It's very common to have definitions of data types and groupings defined in a module that are imported and used in several other modules.  The **include** statement is used to pull a submodule into a main module.  A module does not have to be contained in a single file.  It can easily be split into several submodules for maintenance purposes and for easier separation of content.  The **include** statement completely pulls the submodule into the main module.

&nbsp;

After the **import** and **include** sections of the data model, an optional section of data type definitions follows.  This is where any extra data types that are needed to build the module are defined.  The next section is where the actual data model is built.  All the configuration and operational data declarations are in this part.  An optional section at the end is used to define custom RPCs and notifications.

&nbsp;

A YANG data model can be defined by combining all the data nodes discussed earlier in this chapter.  Example 12-3 shows this in a YANG data model example.

&nbsp;

**Example 12-4** *YANG Data Model Example*

```
// Contents of "bogus-interfaces.yang"
module bogus-interfaces {
     namespace "http://bogus.example.com/interfaces";
     prefix "bogus";
 
     import "ietf-yang-types" {
          prefix yang;
     }

     organization "Bogus Inc.";
     contact "john@bogus.example.com";
     description
          "The module for entities implementing the Bogus interfaces .";

     revision 2020-01-06 {
          description "Initial revision.";
     }
     container interfaces {
          leaf intf-name {
               type string;
               description "The name of the interface";
          }

          leaf-list trunk-interfaces {
               type string;
               description "List of trunk interfaces";
          }

          container statistics {
               description "A collection of interface statistics.";
                    leaf in-octets {
                         type yang:counter64;
                         description "Total number of octets received on the
                         interface.";
                    }

                    leaf in-errors {
                         type yang:counter32;
                         description "Number of inbound packets that contained
                         errors.";
                    }

                    leaf out-octets {
                         type yang:counter64;
                         description "Total number of octets sent out on the
                         interface.";
                    }

                    leaf out-errors {
                         type yang:counter32;
                         description "Number of outbound packets that contained
                         errors.";
                    }
          }
          list user {
               key name;
               leaf name {
                    type string;
               }
               leaf uid {
                    type uint32;
               }
               leaf full-name {
                    type string;
               }
          }
     }
}
```

&nbsp;

The IETF and other standards-setting groups have defined several YANG models.  The following are some of the IETF YANG models:

-   RFC 7224:  *IANA Interface Type YANG Module*
-   RFC 7317:  *A YANG Data Model for System Management*
-   RFC 7404:  *A YANG Data Model for SNMP Configuration*
-   RFC 8299:  *YANG Data Model for L3VPN Service Delivery*
-   RFC 8343:  *A YANG Data Model for Interface Management*
-   RFC 8344:  *A YANG Data Model for IP Management*

&nbsp;

For an up-to-date and complete collection of YANG modules, see https://github.com/YangModels/yang.  Anyone can create YANG data models.  In most cases, though, they are created by network equipment vendors, the IETF, and OpenConfig.  openConfig is a group of network operators, including AT&T, Googl,e Microsoft, Facebook, and Apple, that was created to define standards intended to make networks more open and programmable.  Because OpenConfig is not a formal standards body, the OpenConfig data models change rapidly.  The data models released by the IETF are also called *open* data models.  Open data models provide a common interface across multiple platforms, acting as the lowest common denominator for data models.  Native data models are specific for each network vendor and each network operating system.  Native models are usually not interoperable with other platforms; they closely mirror the structure of the LCI and define extra features that are specific ot each vendor.

&nbsp;

YANG is an extensible language, allowing extension statements to be defined by standards bodies, vendors, and individuals.  The statement syntax allows these extensions to coexist with standard YANG statements in a natural way.  YANG allows a module to augment a date model by inserting additional YANG nodes into the model.  This allows vendors to add vendor-specific parameters to standard data models in an interoperable way.  The **augment** statement allows a module to add data to the schema tree.  As an example, let's consider the statistics container as being part of the interfaces-statistics module.  The statistics container looks as shown in Example 12-5.

&nbsp;

**Example 12-5** *YANG Data Model Augmentation*

```
container statistics {
     description "A collection of interface statistics.";
     leaf in-octets {
          type yang:counter64;
          description "The total number of octets received on the interface.";
     }
     leaf in-errors {
          type yang:counter32;
          description "Number of inbound packets that contained errors.";
     }
     leaf out-octets {
          type yang:counter64;
          description "The total number of octets sent out on the interface.";
     }
     leaf out-errors {
          type yang:counter32;
          description "Number of outbound packets that contained errors.";
     }
}

In order to augment the module, the "augment" statement is used as follows:

import interface-statistics {
          prefix "intf-stats";
     }
     augment "/intf-stats:statistics" {
          leaf in-unicast-pkts {
               type yang:counter64;
               description "Number of unicast packets received on the interface.";
          }
          leaf out-unicast-pkts {
               type yang:counter64;
               description "Number of unicast packets sent out the interface.";
          }
      }
```

&nbsp;

Notice in Example 12-5 that the **augment** statement takes as input the relative path for the **statistics** object in the **intf-stats** module.  Two new leaves are added to the model: **in-unicast-pkts** for inbound unicast data packets on an interface and **out-unicast-pkts** for outbound unicast data packets on the interface.

&nbsp;

YANG supports the definition of NETCONF RPCs.  This means that in addition to the predefined NETCONF operations (**get**, **get-config**, and **edit-config**), additional operations can be defined in YANG.  This is done through the **rpc** declaration.  It's a common occurrence to have several different operating system images stored in the flash memory of networking devices, including the current running image, the previous image, and an image for upgrade.  Upgrading software packages and operating system images is a common operational requirement for network administrators.  NETCONF does not support this common operational task by default.  Example 12-6 shows the YANG definition of a new NETCONF action to activate a specific software image on the device that implements this action.

&nbsp;

The RPC definition contains inputs and outputs.  In this case, the input leaf specifies the binary of the image that will be activated, and the output leaf contains the status of the RPC action.  Keep in mind that the additional RPCs are defined through YANG models and available on the server side on the device.  The client or the management system interacting with the server would also have to be able to interpret the output and execute the custom RPC action.

&nbsp;

**Example 12-6** *NETCONF RPC Action Definition*

```
rpc activate-software-image {
    input {
        leaf image {
            type binary;
        }
    }
    output {
        leaf status {
            type string;
        }
    }
}
```

&nbsp;

NETCONF supports notification messages, which are similar to SNMP traps.  The **notification** statement is used to define NETCONF notifications.  It takes only one argument, which is the identifier, followed by a block of data statements that contain the detailed notification information.  Example 12-7 shows a simple NETCONF notification for a configuration change.

&nbsp;

**Example 12-7** *NETCONF Notification Definition*

```
notification config-change {
    description "The configuration change.";
    leaf operator-name {
        type string;
    }

    leaf-list change {
        type instance-identifier;
    }
}
```

&nbsp;

The notification in Example 12-7 has two nodes: one for the name of the operator that performed the change and one for the list of changes performed during the configuration session.

&nbsp;

Reading a YANG data model straight from an RFC specification can be a daunting task, especially when you're new to data models.  **pyang** is a Python program that has been developed to validate and convert YANG models to more user-friendly and readable formats.  pyang can be downloaded from https://github.com/mbj4668/pyang.  To see how pyang version 2.1.1 works, consider the **ietf-interfaces** YANG model defined in RFC 8343 and downloaded from https://github.com/YangModels/yang.  This data model follows the structure discussed in this chapter, and Example 12-8 shows what the **ietf-interfaces.yang** file looks like.

&nbsp;

**Example 12-8** ***ietf-interfaces** YANG Data Model Snippet*

```
module ietf-interfaces {
  yang-version 1.1;
  namespace "urn:ietf:params:xml:ns:yang:ietf-interfaces";
  prefix if;

  import ietf-yang-types {
    prefix yang;
  }

  organization
    "IETF NETMOD (Network Modeling) Working Group";

  contact
    "WG Web:   <https://datatracker.ietf.org/wg/netmod/>
     WG List:  <mailto:netmod@ietf.org>

     Editor:   Martin Bjorklund
               <mailto:mbj@tail-f.com>";
  description
    "This module contains a collection of YANG definitions for
     managing network interfaces.+

     Copyright (c) 2018 IETF Trust and the persons identified as
     authors of the code.  All rights reserved.

     Redistribution and use in source and binary forms, with or
     without modification, is permitted pursuant to, and subject
     to the license terms contained in, the Simplified BSD License
     set forth in Section 4.c of the IETF Trust's Legal Provisions
     Relating to IETF Documents
     (https://trustee.ietf.org/license-info).

     This version of this YANG module is part of RFC 8343; see
     the RFC itself for full legal notices.";

  revision 2018-02-20 {
    description
      "Updated to support NMDA.";
... omitted output
```

&nbsp;

You can run this YANG model through pyang and specify the tree format by using the command **pyang -f tree ietf-interfaces.yang**.  This results in the output shown in Example 12-9.

&nbsp;

**Example 12-9** *pyang Output for **ietf-interfaces.yang***

```
module: ietf-interfaces
  +--rw interfaces
  |  +--rw interface* [name]
  |     +--rw name                        string
  |     +--rw description?                string
  |     +--rw type                        identityref
  |     +--rw enabled?                    boolean
  |     +--rw link-up-down-trap-enable?   enumeration {if-mib}?
  |     +--ro admin-status                enumeration {if-mib}?
  |     +--ro oper-status                 enumeration
  |     +--ro last-change?                yang:date-and-time
  |     +--ro if-index                    int32 {if-mib}?
  |     +--ro phys-address?               yang:phys-address
  |     +--ro higher-layer-if*            interface-ref
  |     +--ro lower-layer-if*             interface-ref
  |     +--ro speed?                      yang:gauge64
  |     +--ro statistics
  |        +--ro discontinuity-time    yang:date-and-time
  |        +--ro in-octets?            yang:counter64
  |        +--ro in-unicast-pkts?      yang:counter64
  |        +--ro in-broadcast-pkts?    yang:counter64
  |        +--ro in-multicast-pkts?    yang:counter64
  |        +--ro in-discards?          yang:counter32
  |        +--ro in-errors?            yang:counter32
  |        +--ro in-unknown-protos?    yang:counter32
  |        +--ro out-octets?           yang:counter64
  |        +--ro out-unicast-pkts?     yang:counter64
  |        +--ro out-broadcast-pkts?   yang:counter64
  |        +--ro out-multicast-pkts?   yang:counter64
  |        +--ro out-discards?         yang:counter32
  |        +--ro out-errors?           yang:counter32
  x--ro interfaces-state
     x--ro interface* [name]
        x--ro name               string
        x--ro type               identityref
        x--ro admin-status       enumeration {if-mib}?
        x--ro oper-status        enumeration
        x--ro last-change?       yang:date-and-time
        x--ro if-index           int32 {if-mib}?
        x--ro phys-address?      yang:phys-address
        x--ro higher-layer-if*   interface-state-ref
        x--ro lower-layer-if*    interface-state-ref
        x--ro speed?             yang:gauge64
        x--ro statistics
           x--ro discontinuity-time    yang:date-and-time
           x--ro in-octets?            yang:counter64
           x--ro in-unicast-pkts?      yang:counter64
           x--ro in-broadcast-pkts?    yang:counter64
           x--ro in-multicast-pkts?    yang:counter64
           x--ro in-discards?          yang:counter32
           x--ro in-errors?            yang:counter32
           x--ro in-unknown-protos?    yang:counter32
           x--ro out-octets?           yang:counter64
           x--ro out-unicast-pkts?     yang:counter64
           x--ro out-broadcast-pkts?   yang:counter64
           x--ro out-multicast-pkts?   yang:counter64
           x--ro out-discards?         yang:counter32
           x--ro out-errors?           yang:counter32
```

&nbsp;

Example 12-9 shows a compressed version of a YANG data model that is 1123 lines long, with only the critical information left.  The clear separation between configuration (**rw**, which means read/write) and state (**ro**, which means read-only) data can be observed right away.  All the leafs and groupings in the model and their types are also displayed.  pyang is extremely versatile and useful as it validates the correctness of YANG models and also converts them into several formats, including yin, dsdl, trees, jstree, uml, and jsonxdsl.

&nbsp;

Let's now explore the NETCONF interface that is provided by the Cisco IOS XE operating system.  Cisco IOS XE is a network operating system for enterprising switching, routing, wried, and wireless access.  The following examples use Cisco IOS XE 16.6.3 running on a Cisco CSR1000V device with NETCONF enabled.  Enabling NETCONF on the Cisco CSR1000V running Cisco IOS XE version 16.6..3 is extremely simple:  Just issue the **netconf-yang** command in the configuration mode of the device.  By default, the NETCONF server on the device runs on TCP port 830 and uses the SSH process for transport.  A NETCONF session can be established by using an SSH client and specifying port 830 when connecting to the device.  When establishing a NETCONF session with a device, a complete list of all the capabilities and YANG modules supported by the device is exchanged with the client.  An example of this exchange can be observed in Example 12-10.

&nbsp;

**Example 12-10** *Capabilities Exchanged When Established a NETCONF Session*

```
<?xml version="1.0" encoding="UTF-8"?>
<hello xmlns="urn:ietf:params:xml:ns:netconf:base:1.0">
<capabilities>
<capability>urn:ietf:params:netconf:base:1.0</capability>
<capability>urn:ietf:params:netconf:base:1.1</capability>
<capability>urn:ietf:params:netconf:capability:writable-running:1.0</capability>
<capability>urn:ietf:params:netconf:capability:xpath:1.0</capability>
<capability>urn:ietf:params:netconf:capability:validate:1.0</capability>
<capability>urn:ietf:params:netconf:capability:validate:1.1</capability>
<capability>urn:ietf:params:netconf:capability:rollback-on-error:1.0</capability>
<capability>urn:ietf:params:netconf:capability:notification:1.0</capability>
<capability>urn:ietf:params:netconf:capability:interleave:1.0</capability>
<capability>urn:ietf:params:netconf:capability:with-defaults:1.0?basic-Ω
<capability>urn:ietf:params:netconf:capability:yang-library:1.0?revision=2016-06-21
&amp;module-set-id=0de3f66ee656759ede57b7f3b6cd310d</capability>
<capability>http://tail-f.com/ns/netconf/actions/1.0</capability>
<capability>http://tail-f.com/ns/netconf/extensions</capability>
<capability>http://cisco.com/ns/cisco-xe-ietf-ip-deviation?module=cisco-
xe-ietf-ip-deviation&amp;revision=2016-08-10</capability>
<capability>http://cisco.com/ns/cisco-xe-ietf-ipv4-unicast-routing-
deviation?module=cisco-xe-ietf-ipv4-unicast-routing-deviation&amp;revis
ion=2015-09-11</capability>
<capability>http://cisco.com/ns/cisco-xe-ietf-ipv6-unicast-routing-
deviation?module=cisco-xe-ietf-ipv6-unicast-routing-deviation&amp;revis
ion=2015-09-11</capability>
<capability>http://cisco.com/ns/cisco-xe-ietf-ospf-
deviation?module=cisco-xe-ietf-ospf-deviation&amp;revision=2015-09-11</
capability>
<capability>http://cisco.com/ns/cisco-xe-ietf-routing-deviation?module=cisco-xe-ietf-routing-
deviation&amp;revision=2016-07-09</
capability>
<capability>http://cisco.com/ns/cisco-xe-openconfig-acl-
deviation?module=cisco-xe-openconfig-acl-deviation&amp;revision=2017-08-21</
capability>
<capability>http://cisco.com/ns/mpls-static/
devs?module=common-mpls-static-devs&amp;revision=2015-09-11</capability>
<capability>http://cisco.com/ns/nvo/devs?module=nvo-devs&amp;revision=2015-09-11</
capability>
<capability>http://cisco.com/ns/yang/Cisco-IOS-XE-aaa?module=Cisco-IOS-XE-
aaa&amp;revision=2017-09-05</capability>
<capability>http://cisco.com/ns/yang/Cisco-IOS-XE-acl?module=Cisco-IOS-XE-
acl&amp;revision=2017-08-01</capability>
<capability>http://cisco.com/ns/yang/Cisco-IOS-XE-acl-
oper?module=Cisco-IOS-XE-acl-oper&amp;revision=2017-02-07</
capability>
...
</capabilities>
<session-id>5546</session-id></hello>]]>]]>
```

&nbsp;

All the YANG models supported by the device are included in the HELLO message, and so is a session ID.  This version of Cisco IOS XE supports both NETCONF 1.0 and 1.1 as well as the writable-running capability (which makes it possible to write directly to the running configuration of the device), the rollback-on-error 1.0 capability, and the notification 1.0 capability.  These capabilities translate into YANG models defined by the IETF, as you can see in their XPath defintion:

`urn:ietf:params:netconf:`

&nbsp;

The delimiter string **]]>]]>** at the end of the response signifies the end of the message.  Next, the client needs to respond to the hello message with a list of capabilities that it supports.  The simplest response that a client can send is the following:

```
<?xml version="1.0" encoding="UTF-8"?>
<hello xmlns="urn:ietf:params:xml:ns:netconf:base:1.0">
<capabilities>
  <capability>urn:ietf:params:netconf:base:1.0</capability>
</capabilities>
</hello>]]>]]>
```

&nbsp;

There is no reply from the device to the client's initial hello message, which is expected behavior; however, an active NETCONF connection to the device is now established.  In order to retrieve the running configuration of the device, the following XML message is sent next.

```
<?xml version="1.0" encoding="UTF-8"?>

<rpc message-id="101" xmlns="urn:ietf:params:xml:ns:netconf:
base:1.0">

     <get-config>

          <source>

               <running/>

          </source>

     </get-config>

</rpc>]]>]]>
```

&nbsp;

This example shows a NETCONF rpc message with an ID of 101 defined by the base IETF NETCONF 1.0 namespace.  The message ID is used to keep track of the response received from the device.  The operation within the message is **get-config**, with the target data source of the configuration that is stored in the **running** data store.  The response contains the running configuration of the device enclosed in an \<rpc-reply> XML element and is displayed in Example 12-11.

&nbsp;

**Example 12-11** *Snippet of the NETCONF **get-config** Operation for the Running Configuration*

```
<?xml version="1.0" encoding="UTF-8"?>
<rpc-reply xmlns="urn:ietf:params:xml:ns:netconf:base:1.0" message-id="101">
   <data>
      <native xmlns="http://cisco.com/ns/yang/Cisco-IOS-XE-native">
         <version>16.6</version>
         <boot-start-marker />
         <boot-end-marker />
        <service>
            <timestamps>
               <debug>
                  <datetime>
                     <msec />
                  </datetime>
               </debug>
               <log>
                  <datetime>
                     <msec />
                  </datetime>
               </log>
            </timestamps>
         </service>
         <platform>
            <console xmlns="http://cisco.com/ns/yang/Cisco-IOS-XE-platform">
               <output>serial</output>
            </console>
         </platform>
         <hostname>csr1kv</hostname>
         <enable>
            <password>
               <secret>cisco</secret>
            </password>
            <secret>
               <type>5</type>
               <secret>$1$A1eZ$Vp95LGeOXX3CfOKO5K5Nf1</secret>
            </secret>
         </enable>
... omitted output
   </data>
</rpc-reply>
```

&nbsp;

While interacting with a NETCONF server this way is possible, it is very cumbersome and error prone.  Several publicly available NETCONF tools and clients make it much easier to interact with a NETCONF server.  One popular NETCONF client is the Python 3 **ncclient** library.  Next, let's use ncclient to explore the Cisco NX-OS NETCONF interface.

&nbsp;

**Cisco NX-OS is the network operating system that powers Cisco Nexus switches in data centers** around the world.  **Built on top of Linux**, Cisco NX-OS, also known as Open NX-OS, exposes the full power of Linux, with rich programmable interfaces and a diverse set of automation tools.  The following examples use Cisco NX-OS version 9.2.3, ncclient version 0.6.7, and Python 3.7.4.  You enable NETCONF on Cisco NX-OS version 9.2.3 by issuing the **feature conf** command in configuration mode.  Much as with Cisco IOS XE, the NETCONF server is running by default on TCP port 830 and uses the SSH protocol as transport.

&nbsp;

The **manager** module within the ncclient library handles all NETCONF RPC connections between the client and the server.  By using the **connect** method available with the **manager** module, it is very easy to establish a connection to a NETCONF server.  The **connect** method takes as input parameters the hostname or the IP address of the NETCONF server, the port on which the server is running, the username and password that are used to connect, and the **hostkey_verify** parameter, which specifies whether the script should look for hostkey verification information in the ~/.ssh/known_hosts location on the server on which the script is run.  Example 12-12 shows a simple Python 3 script that retrieves the capabilities of the NETCONF server and displays them to the console.

&nbsp;

**Example 12-12** *Python Script to Retrieve and Print NETCONF Capabilities*

```python
#!/usr/bin/env python
""" Get the capabilities of a remote device with NETCONF """

from ncclient import manager

NXOS_HOST = "10.10.10.10"
NETCONF_PORT = "830"
USERNAME = "admin"
PASSWORD = "password"

# create a get_capabilities() method
def get_capabilities():
    """
    Method that prints NETCONF capabilities of remote device.
    """
    with manager.connect(
            host=NXOS_HOST,
            port=NETCONF_PORT,
            username=USERNAME,
            password=PASSWORD,
            hostkey_verify=False
        ) as device:

        # print all NETCONF capabilities
        print('\n***NETCONF Capabilities for device {}***\n'.format(NXOS_HOST))
        for capability in device.server_capabilities:
            print(capability)

if __name__ == '__main__':
    get_capabilities()
```

&nbsp;

After importing the **manager** module from ncclient, the NETCONF server IP address, port number, username, and password are defined.  The **get_capabilities()** function establishes a connection to the NETCONF server, retrieves the server capabilities with **device.server_capabilities()**, iterates with a **for** loop over each capability, and displays the capabilities to the console.  Example 12-13 shows the result of running this script on a Cisco Nexus 9000 switch running Cisco NX-OS 9.2.3 with NETCONF enabled.

&nbsp;

**Example 12-13** *Output of the Python Script from Example 12-12*

```
***NETCONF Capabilities for device 10.10.10.10***

urn:ietf:params:netconf:base:1.0
urn:ietf:params:netconf:base:1.1
urn:ietf:params:netconf:capability:writable-running:1.0
urn:ietf:params:netconf:capability:rollback-on-error:1.0
urn:ietf:params:netconf:capability:candidate:1.0
urn:ietf:params:netconf:capability:validate:1.1
urn:ietf:params:netconf:capability:confirmed-commit:1.1
http://cisco.com/ns/yang/cisco-nx-os-device?revision=2019-02-17&module=Cisco-NX-OS-
device&deviations=Cisco-NX-OS-device-deviations
```

&nbsp;

At this writing, Cisco NX-OS by default implements the base NETCONF capabilities for  version 1.0 and 1.1 as well as the YANG models for writable running configuration, rollback-on-error, candidate data store, and others.  Additional YANG models are supported and can be installed manually.

&nbsp;

In order to perform changes on the NETCONF server, the **edit_config** method available with the **manager** module can be used.  In example 12-14, a new loopback interface is created, the administrative state is switched to up, and an IP address is configured on the newly created interface.

&nbsp;

**Example 12-14** *Python Script to Create a New Loopback Interface*

```python
#!/usr/bin/env python
""" Add a loopback interface to a device with NETCONF """

from ncclient import manager

NXOS_HOST = "10.10.10.10"
NETCONF_PORT = "830"
USERNAME = "admin"
PASSWORD = "password"
LOOPBACK_ID = "01"
LOOPBACK_IP = "1.1.1.1/32"

# create add_loopback() method
def add_loopback():
    """
    Method that adds loopback interface and configures IP address
    """

    add_loop_interface = """<config>
    <System xmlns="http://cisco.com/ns/yang/cisco-nx-os-device">
        <intf-items>
            <lb-items>
                <LbRtdIf-list>
                    <id>lo{id}</id>
                    <adminSt>up</adminSt>
                    <descr>Intf configured via NETCONF</descr>
                </LbRtdIf-list>
            </lb-items>
        </intf-items>
        <ipv4-items>
            <inst-items>
                <dom-items>
                    <Dom-list>
                        <name>default</name>
                        <if-items>
                            <If-list>
                                <id>lo{id}</id>
                                <addr-items>
                                    <Addr-list>
                                        <addr>{ip}</addr>
                                    </Addr-list>
                                </addr-items>
                            </If-list>
                        </if-items>
                    </Dom-list>
                </dom-items>
            </inst-items>
        </ipv4-items>
    </System>
    </config>""".format(id=LOOPBACK_ID, ip=LOOPBACK_IP)

    with manager.connect(
            host=NXOS_HOST,
            port=NETCONF_PORT,
            username=USERNAME,
            password=PASSWORD,
            hostkey_verify=False
        ) as device:

        # Add loopback interface
        print("\n Adding Loopback {} with IP address {} to device {}...\n".\
            format(LOOPBACK_ID, LOOPBACK_IP, NXOS_HOST))
        netconf_response = device.edit_config(target='running',
        config=add_loop_interface)
        # Print the XML response
        print(netconf_response)

if __name__ == '__main__':
    add_loopback()
```

&nbsp;

After importing the **manager** module from the ncclient library, the connection details for the NETCONF server are specified.  The loopback interface ID and IP address that will be created are also defined at this point in the script.  The **add_loopback()** function contains the XML document that specifies the NETCONF configuration information in the **add_loop_interface** variable.  The YANG model that is used in this case is specified through the XPath value, **`xmlns="http://cisco.com/ns/yang/cisco-nx-os-device"`**.  Recall that this YANG data model is included by default in Cisco NX-OS.  The actual path in the treelike YANG model where the configuration changes are going to be performed is also included in the XML document.  This XML document matches one to one the YANG data model **cisco-nx-os-device**.  The script uses the **connect** method to establish a connection to the NETCONF server and then send the XML configuration document to the **running** data store.  The response received is displayed to the console using the **print** function.  The result of successfully running this script looks similar to the following:

```
Adding Loopback 01 with IP address 1.1.1.1/32 to device
10.10.10.10...

<?xml version="1.0" encoding="UTF-8"?>

<rpc-reply message-id="urn:uuid:6de4444b-9193-4b74-837b-
e3994d75a319" xmlns="urn:ietf:params:xml:ns:netconf:base:1.0">

    <ok/>

</rpc-reply>
```

&nbsp;

# RESTCONF

&nbsp;

According to RFC 8040, RESTCONF is "an HTTP-based protocol that provides a programmatic interface for accessing data defined in YANG, using the datastore concepts defined in the Network Configuration Protocol (NETCONF)."  Basically, **RESTCONF provides a REST-like interface to the NETCONF/YANG interface model**.

&nbsp;

Although NETCONF provides significant improvements over SNMP, it doesn't provide network interfaces with a good REST API interface.  Rather than developing an entirely new protocol and data model, the IETF extended NETCONF into RESTCONF.  RESTCONF is not a replacement for NETCONF.  Rather, RESTCONF provides an API that aligns with other web application APIs to provide an easy entry point for developers.

>    ***`Key Topic`***

&nbsp;

Like other REST APIs, RESTCONF uses the HTTPS protocol to encapsulate and send messages.  Authentication is accomplished using typical HTTP authentication models, such as basic authentication, where usernames and passwords are Base64 encoded and transmitted from the client to the server via an Authentication header.  Figure 12-4 shows the RESTCONF protocol stack.

&nbsp;

**Figure 12-4** *RESTCONF Protocol Stack*

![Figure 12-4 RESTCONF Protocol Stack](assets/images/Figure%2012-4%20RESTCONF%20Protocol%20Stack.jpeg)

&nbsp;

REST APIs typically implement CRUD (create, retrieve, update, and delete) operations, leveraging HTTP methods.  RESTCONF maps the NETCONF operations into HTTP methods as shown in Table 12-4.

&nbsp;

**Table 12-4** RESTCONF HTTP Methods and Their Corresponding NETCONF Operations

| RESTCONF | NETCONF |
| -- | -- |
| GET | \<get>, \<get-config> |
| POST | \<edit-config> (operation="create") |
| PUT | \<edit-config> (operation="create/replace") |
| PATCH | \<edit-config> (operation="merge") |
| DELETE | \<edit-config> (operation="delete") |

&nbsp;

The available RESTCONF methods and their corresponding NETCONF operations are as follows:

-    The HTTP GET method is sent in the RESTCONF request by the client to retrieve data and metadata for a specific resource.  It translates into the NETCONF \<get> and \<get-config> operations.  The GET method is supported for all resource types except operation resources.
-    The HTTP POST method is used for NETCONF RPCs and to create a data resource.  It represents the same semantics as the NETCONF \<edit-config> operation with operation="create".
-    The PUT method is used to create or replace the contents of the target resource.  It is the equivalent of the NETCONF \<edit-config> operation with operation="create/replace".
-    The PATCH method provides the framework for resource patching mechanism.  It is the equivalent of the NETCONF \<edit-config> operation with operation="merge".
-    The HTTP DELETE method is used to delete the target resource and is the equivalent of the NETCONF \<edit-config> with operation="delete".

&nbsp;

RESTCONF data is encoded with either XML or JSON.  Compared with NETCONF, RESTCONF has added support for the JSON encoding.  There are two new media types defined for RESTCONF:

-    **application/yang.api+xml** for XML-encoded payloads
-    **application/yang.api+json** for JSON-encoded data

&nbsp;

With all REST APIs, including RESTCONF APIs, the URI is important in identifying the data being requested or configured.  A unique characteristic of RESTCONF is that it lacks any true API documentation that a developer would use to learn how to use it.  Rather, the YANG models themselves are the API documentation.

&nbsp;

>    ***`Key Topic`***

&nbsp;

All RESTCONF URIs use the following format:

**`https://<ADDRESS>/<ROOT>/data/<[YANG_MODULE:]CONTAINER>/ <LEAF>[?<OPTIONS>]`**

where

-    ADDRESS is the IP address of the hostname and port number where the RESTCONF agent is available.
-    ROOT is the main entry point for RESTCONF requests.  Before connecting to a RESTCONF server, the root must be determined.  Per the RESTCONF standard, devices implementing the RESTCONF protocol should expose a resource called **/.well-known/host-meta** to enable discovery of ROOT programmatically.
-    data is the RESTCONF API resource type for data.  The operations resource type is also available for access to RPC operations.
-    [YANG_MODULE:]CONTAINER is the base mode container being used.
-    LEAF is an individual element from within the container.
-    [?\<OPTIONS>] are the options that some network devices may support that are sent as query parameters that impact the returned results.  These options are optional and can be omitted.  The following are some examples of possible options:
     -    **depth = unbounded**:  If nothing is specified, this option is the default.  It indicates that the returned data should follow the nested models to the end.  Integer values specifying the depth of the data to be returned are also supported.
     -    **content = [all, config, nonconfig]**:  This query option controls the type of data returned.  If nothing is specified, the default value **all**, is used.
     -    **fields = expr**:  This option limits what leafs are returned in the response.

&nbsp;

Consider the **ietf-interfaces** YANG model defined in RFC 8343 and partially presented in Figure 12-5.  Using the data model details, the URIs for RESTCONF requests can be easily constructed.  Generating the code to support RESTCONF APIs and the mapping of those API calls into NETCONF can be automated because the mapping from a YANG data model to a RESTCONF URI is known and well defined.

&nbsp;

**Figure 12-5** *Mapping Between the YANG Model and RESTCONF URI*

![Figure 12-5 Mapping Between the YANG Model and RESTCONF URI](assets/images/Figure%2012-5%20Mapping%20Between%20the%20YANG%20Model%20and%20RESTCONF%20URI.jpeg)

&nbsp;

RESTCONF helps support a common, REST-based programming model for network automation in general. 

&nbsp;

Enabling RESTCONF on Cisco IOS XE is simple and straightforward.  First, RESTCONF runs over HTTPS, so a secure HTTP server is enabled on the device by using **ip http  secure-server** in configuration mode.  Next, RESTCONF is enabled with the **restconf** command in configuration mode.  Once these two commands are enabled and a network administrator account exists on the device, RESTCONF is read yto be accessed.  Cisco IOS XE 16.6.3 and Postman 7.13 are used in the following examples.

&nbsp;

Devices that implement the RESTCONF protocol should expose a resource called /.well-known/host-meta in order to enable the discovery of the REST API root resource programmatically.  Using Postman to perform a GET request on the https://{{host}}:{{port}}/.well-known/host-meta endpoint results in the output shown in Figure 12-6.

&nbsp;

**Figure 12-6** *Getting the REST API Root Resource*

![Figure 12-6 Getting the REST API Root Resource](assets/images/Figure%2012-6%20Getting%20the%20REST%20API%20Root%20Resource.jpeg)

&nbsp;

The **href** attribute in the response contains the path to the REST API root resource: **/restconf**.  Exploring the API further and performing a GET request on https://{{host}}:{{port}}/restconf will expose the top-level resources available in RESTCONF: **data** and **operations**, as shown in Figure 12-7.

&nbsp;

**Figure 12-7** *Top-Level Resource Available in RESTCONF*

![Figure 12-7 Top-Level Resource Available in RESTCONF](assets/images/Figure%2012-7%20Top-Level%20Resource%20Available%20in%20RESTCONF.jpeg)

&nbsp;

To explore further down the API tree and into the YANG models and retrieve a complete list of all the interfaces, their status, and traffic statistics through the RESTCONF interface, you can perform a GET request on the https://{{host}}:{{port}}/restconf/data/ietf-interfaces:interfaces-state/ endpoint.  The response received back from the API should look similar to the one in Figure 12-8.

&nbsp;

**Figure 12-8** *Getting Interface Statistics with RESTCONF*

![Figure 12-8 Getting Interface Statistics with RESTCONF](assets/images/Figure%2012-8%20Getting%20Interface%20Statistics%20with%20RESTCONF.jpeg)

&nbsp;

#  Model-Driven Telemetry

&nbsp;

Timely collection of network statistics is critical to ensuring that a network performs as expected and foreseeing and preventing any problems that could arise.  Technologies such as SNMP, syslog, and the CLi have historically been used to gather this state information from the network.  Using a pull model to gather the data, in which the request for network data originates from the client, does not scale and restricts automation efforts.  With such a model, the network device sends data only when the client manually requests it.  A push model continuously streams data from the network device to the client.  **Telemetry enables the push model, providing near instantaneous access to operational data.  Clients can subscribe to specific data they need by using standard-based YANG data models delivered over NETCONF.**

&nbsp;

>    ***`Key Topic`***

&nbsp;

There are two types of telemetry subscriptions:

-    **Dynamic**:  The subscriber sends a request, usually via the **ietf-yangpush.yang** data model.  The device approves the request, replies with a subscription ID, and begins streaming telemetry data.  Dynamic subscriptions cannot be changed but can be terminated at any time, usually by closing the NETCONF session.
-    **Configured**:  The subscription is configured via the CLI, NETCONF, or RESTCONF and is persistent between reboots.  Configured subscriptions can be modified and terminated at any point and can be used to stream data to more than one received.

&nbsp;

A subscription can specify how notifications are sent to the receivers:

-    **Periodic notifications**:  These notifications are sent with a fixed rate defined in the telemetry subscription.  This data is ideal for device counters or measures such as CPU utilization or interface statistics because of their dynamic, always-changing nature.
-    **On-change notifications**:  These notifications are sent only when the data changes.  These types of notifications might be sent, for example, for faults, new neighbors being detected, and thresholds being crossed.