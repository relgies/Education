Traditionally, network devices were managed almost exclusively through ***command-line interfaces (CLIs)***.

For network monitoring, ***Simple Network Management Protocol (SNMP)*** is still widely used.

Data modeling is replacing manual configuration as it provides a standards-based, programmatic method of writing configuration data and gathering statistics and operational data from devices.

YANG data models have been developed specifically to address the need for standardization and commonality in network management.  

Model-drive programmability enables you to automate the configuration and control of network devices.

***Cisco IOS XE***, a network operation system for enterprises, ***Cisco NX-OS***, a network operating system for data centers, and ***Cisco IOS XR***, a network operating system for service providers, support three standards-based programmable interfaces for operating on the ***YANG*** data models:

-   ***NETCONF***
-   ***RESTCONF***
-   ***gRPC***

***gRPC*** is an open-source project started by Google to provide a modern ***remote procedure call (RPC)*** framework that can be used in any environment - not just for network configurations.

When a client request is received via NETCONF, RESTCONF, or gRPC, it is first converted into an abstract ***message object***.  Based on the ***namespace*** in the request, the message object is delivered to the underlying model infrastructure, where it is processed and executed on the device ***data store***.  The results are returned to the client through the agent on which the request was received.

**Figure 12-1** *Model-Driven Programmability on Cisco Devices*

![Figure 12-1 Model-Driven Programmability on Cisco Devices](assets/images/Figure%2012-1%20Model-Driven%20Programmability%20on%20Cisco%20Devices.jpeg)

&nbsp;

#   NETCONF

&nbsp;

***Simple Network Management Protocol (SNMP)*** is a network management protocol that was initially developed in the late 1980s.  The intention with SNMP was to create a protocol to help with both configuration and monitoring of network devices.

The ***Network Configuration Protocol (NETCONF)*** was developed by the IETF based on requirements put forth to replace for a new network management technology to replace SNMP.  

NETCONF specifies the means of opening a secure management session with a network device, includes a set of operations to manipulate the configuration data and retrieve the operational state, and describes a mechanism to send out notifications.

While the NETCONF protocol specifies the mechanism to establish a connection and exchange data between a network administrator and a device, ***it does not define the actual format of the data***.  This is the role of the ***YANG (Yet Another Next Generation) data model***, which was defined by the IETF in 2010 in RFC 6020 specifically to be used with NETCONF.

