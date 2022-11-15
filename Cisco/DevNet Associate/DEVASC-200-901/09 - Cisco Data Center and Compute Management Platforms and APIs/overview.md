#   Cisco ACI

&nbsp;

Cisco ***Application Centric Infrastructure (ACI)*** is the SDN-based solution from Cisco for data center deployment, management, and monitoring.  The solution is based on two components: the Cisco Nexus family of switches and Cisco ***Application Policy Infrastructure Controller (APIC)***

&nbsp;

The Cisco Nexus 9000 family of switches can run in two separate modes of operation, depending on the software loaded on them.  

The first mode is called ***standalone*** (or ***NX-OS***) ***mode***, which means the switches act like regular Layer 2 / Layer 3 data center devices that are usually managed individually.

In the second mode, ***ACI mode***, the Cisco Nexus devices are part of an ACI fabric and are managed in a centralized fashion.

&nbsp;

The central controller for the ACI fabric is the Cisco ***Application Policy Infrastructure Controller (APIC)***.

This controller is the main architectural component of the Cisco ACI solution and provides a single point of automation and management for the Cisco ACI fabric, policy enforcement, and health monitoring.  

The Cisco APIC was built on an API-first architecture.  On top of this API, a command-line interface (CLI) and a graphical user interface (GUI) have been developed.

&nbsp;

The API is exposed through a REST interface and is accessible as a northbound interface for users and developers to integrate and develop their own custom solutions on top of the Cisco APIC and Cisco ACI fabric.  

The Cisco APIC interacts with and manages the Cisco Nexus switches through the ***OpFlex*** protocol, which is exposed as a southbound interface.  

From an SDN controller perspective, a northbound interface specifies the collection of protocols that a user can use to interact with and program the controller, while a southbound interface specifies the protocols and interfaces that the controller uses to interact with the devices it manages.  

&nbsp;

Some of the features and capabilities of the Cisco APIC are as follows:

-   Application-centric network policy for physical, virtual, and cloud infrastructure
-   Data model-based declarative provisioning
-   Designed around open standards and open APIs
-   Cisco ACI fabric inventory and configuration
-   Software image management
-   Fault, event, and performance monitoring and management
-   Integration with third-party management systems such as VMware, Microsoft, OpenStack
-   Cloud APIC appliance for Cisco cloud ACI deployments in public cloud environments

A minimum of three APICs in a cluster are needed for high availability.

&nbsp;

The Cisco ACI fabric is built in a ***leaf-and-spine*** architecture.

Some of the Cisco Nexus switches that are part of the ACI fabric are called ***leaves*** and perform a function similar to that of an access switch, to which both physical and virtual endpoint servers are connected.  

Some of the switches are called ***spines*** and perform a function similar to that of a distribution switch to which all the access switches are connected.

Not all Cisco Nexus 9000 switches support all functions in a leaf-and-spine architecture.

***Leaf*** switches connect to all the spine switches and to endpoint devices, including the Cisco APICs.

The Cisco APICs never connect to spine switches.

***Spine*** switches can only ever connect to leaf switches and are never interconnected with each other.

&nbsp;

The configuration of the ACI fabric is stored in the APIC using an ***object-oriented schema***.  This configuration represents the logical model of the fabric.  The APIC compiles the logical model and renders the policies into a concrete model that runs in the physical infrastructure.

Each of these switches contains a complete copy of the concrete model.  When a policy that represents a configuration is created in the APIC, the controller updates the logical model.  It then performs the intermediate step of creating a complete policy that it pushes into all the switches, where the concrete model is updated.  

The Cisco Nexus 9000 switches can only execute the concrete model when running in ACI mode.

Each switch has a copy of the concrete model.  If by any chance, all the APIC controllers in a cluster go offline, the fabric keeps functioning, but modifications to the fabric policies are not possible.

&nbsp;

The ACI policy model enables the specification of application requirements.  When a change is initiated to an object in the fabric, the APIC first applies that change to the policy model.  This policy model change triggers a change to the concrete model and the actual managed endpoint.  This management framework is called the ***model-driven framework***.

In this model, the system administrator defines the desired state of the fabric but leaves the implementation up to the APIC.

&nbsp;

The Cisco ACI fabric is composed of physical and logical components.  These components are recorded in the ***Management Information Model (MIM)*** and can be represented in a ***hierarchical management information tree (MIT)***.  

Each node in the ***Management Information Tree (MIM)*** represents a ***managed object (MO)***.  A manage object (MO) can represent a concrete object, such as a switch, an adapter, a power supply, or a logical object, such as an application profile, an endpoint group, or an error message.  

All of the components of the ACI fabric can be represented as managed objects (MO).

&nbsp;

The MIT hierarchical structure starts at the top of the root object and contains parent and child nodes.  Each node in the tree is an MO, and each object in the fabric has a ***distinguished name (DN)***.  The DN describes the object and specifies its location in the tree.  

The following objects contain the policies that control the operation of the fabric.

-   **APICs**:  These are the clustered fabric controllers that provide management, application, and policy deployment for the fabric.
-   **Tenants**:  Tenants represent containers for policies that are grouped for a specific access domain.  The following four kinds of tenants are currently supported by the system:
    -   **User**:  User tenants are needed by the fabric administrator to cater to the needs of the fabric users.
    -   **Common**:  The common tenant is provided by the system and can be configured by the fabric administrator.  The tenant contains policies and resources that can be shared by all tenants.<br>Examples of such resources are firewalls, load balancers, and intrusion detection systems.
    -   **Infra**:  The infra tenant is provided by the system and can be configured by the fabric administrator.  It contains policies that manage the operation of infrastructure resources.
    -   **Management**:  The management tenant is provided by the system and can be configured by the fabric administrator.  This tenant contains policies and resources for in-band and out-of-band configuration of fabric nodes.
-   **Access policies**:  These policies control the operation of leaf switch access ports, which provide fabric connectivity to resources such as virtual machine hypervisors, compute devices, storage devices, and so on.  Several access policies come built in with the ACI fabric by default.  The fabric administrator can tweak these policies or create new ones, as necessary.
-   **Fabric policies**:  These policies control the operation of the switch fabric ports.  Configurations for time synchronization, routing protocols, and domain name resolution are managed with these policies.
-   **VM domains**:  Virtual machine (VM) domain group virtual machine controllers that require similar networking policies configurations.  The APIC communicates with the VM controller to push network configurations al the way to the VM level.
-   **Integration automation framework**:  The Layer 4 to Layer 7 service integration automation framework enables a system to respond to services coming online or going offline.
-   **AAA policies**:  Access, authentication, and account (AAA) policies control user privileges, roles, and security for the ACI fabric.

The hierarchical policy model fits very well with the REST API interface.  As the ACI fabric performs its functions the API reads and writes to objects in the MIT.  The API resource represented by the URLs map directly into the distinguished names that identify objects in the IT.

&nbsp;

## **Building Blocks of Cisco ACI Fabric Policies**

&nbsp;

***Tenants*** are top-level MOs that identify and separate administrative control, application policies, and failure domains.  A tenant can represent a customer in a managed service provider environment or an organization in an enterprise environment, or a tenant can be a convenient grouping of objects and policies.

A tenant's sublevel objects can be grouped into two categories: 

-   ***tenant networking*** 
-   ***tenant policy***

**Figure 9-4** *Cisco ACI Tenant Components*

![Figure 9-4 Cisco ACI Tenant Components](assets/images/Figure%209-4%20Cisco%20ACI%20Tenant%20Components.jpeg)

&nbsp;

### ***Tenant Networking***

The ***tenant networking*** objects provide Layer 2 and Layer 3 connectivity between the endpoints and consist of the following constructs: 

-   ***VRF (virtual routing and forwarding) instances***
-   ***bridge domains***
-   ***subnets***
-   ***external networks***

**Figure 9-5** *Cisco ACI Tenant Networking Components*

![Figure 9-5 Cisco ACI Tenant Networking Components](assets/images/Figure%209-5%20Cisco%20ACI%20Tenant%20Networking%20Components.jpeg)

&nbsp;

***VRF instances***, also called ***contexts*** and ***private networks***, are isolated routing tables.  A VRF instance defines a Layer 3 address domain.  

A tenant can contain one or multiple VRF.  VRF instances exist on any leaf switch that has a host assigned to the VRF instance.  

All of the endpoints within a Layer 3 domain must have unique IP addresses because traffic can flow between these devices if allowed by the policy.

&nbsp;

***Bridge domains*** represent the Layer 2 forwarding domains within the fabric and define the unique MAC address space and flooding domain for broadcast, unknown unicast, and multicast frames.  

Each bridge domain is associated with only one VRF instance, but a VRF instance can be associated with multiple bridge domains.  

Bridge domains can contain multiple subnets, which is different from regular VLANs, which are usually associated with only one subnet.

&nbsp;

***Subnets*** are the Layer 3 networks that provide IP address space and gateway services for endpoints to be able to connect to the network.  

Each subnet is associated with only one bridge domain.

Subnets can be the following:

-   **Public**:  A subnet can be exported to a routed connection.
-   **Private**:  A subnet is confined within its tenant.
-   **Shared**:  A subnet can be shared and exposed in multiple VRF instances in the same tenant or across tenants as part of a shared service.

&nbsp;

***External bridged networks*** connect the ACI fabric to legacy Layer 2/Spanning Tree Protocol networks.  This is usually needed as part of the migration process from a traditional network infrastructure an ACI network.

***External routed networks*** create a Layer 3 connection with a network outside the ACI fabric.  Layer 3 external routed networks can be configured using static routes or routing protocols such as BGP, OSPF, and EIGRP.

&nbsp;

### ***Tenant Policy***
The ***tenant policy*** objects are focused on the policies and services that the endpoints receive.  The tenant policy consists of:

-   ***application profiles***
-   ***endpoint groups (EPGs)***
-   ***contracts***
-   ***filters***

**Figure 9-6** *Cisco ACI Tenant Policy Components*

![Figure 9-6 Cisco ACI Tenant Policy Components](assets/images/Figure%209-6%20Cisco%20ACI%20Tenant%20Policy%20Components.jpeg)

&nbsp;

An ***application profile*** defines the policies, services, and relationships between EPGs.  

An application profile contains one or more EPGs.  The application profile contains as many EPGs as as necessary, and these EPGs are logically related to providing the capabilities of the application.

Applications typically contain multiple components, such as a web-based front end, an application logical layer, and one or more database in the back end.

&nbsp;

The ***endpoint group (EPG)*** is the most important object in the policy model.  An EPG is a collection of endpoints that have common policy requirements, such as security, virtual machine mobility, QoS, or Layer 4 or Layer 7 services.  

In the Cisco ACI fabric, each endpoint has an identity represented by its address, a location, and attributes, and it can be physical or virtual.

Endpoint examples include servers, virtual machines, clients on the internet, and network-attached storage devices.  

Rather than configure and manage endpoints individually, you can place them in EPGs and mange them as a group.  Policies apply to EPGs and never to individual endpoints.  

Each EPG can only be related to one bridge domain.

&nbsp;

***Contracts*** define the policies and services that get applied to EPGs.  

Contracts can be used for redirecting services to a Layer 4 to Layer 7 device, assigning QoS values, and controlling the traffic flow between EPGs.  

EPGs can only communicate with other EPGs based on contract rules.  Contracts specify the protocols and ports allowed between EPGs.  If there is no contract, inter-EPG communication is disabled by default.  For intra-EPG communication, no contract is required as this traffic is always allowed by default.

The relationship between an EPG and a contract can be either a consumer or a provider.  EPG providers expose contracts with which a consumer EPG must comply.  When an EPG consumes a contract, the endpoints in the consuming EPG can initiate communication with any endpoint from the provider EPG.

**Figure 9-7** *Cisco ACI Application Profiles and Contracts*

![Figure 9-7 Cisco ACI Application Profiles and Contracts](assets/images/Figure%209-7%20Cisco%20ACI%20Application%20Profiles%20and%20Contracts.jpeg)

&nbsp;

***Filters*** are the objects that define protocols and port numbers used in contracts.  

Filters can contain multiple protocols and ports, and contracts can consume multiple filters.

&nbsp;

##  **APIC REST API**

&nbsp;

The APIC REST API is a programmatic interface that uses the REST architecture.  The API accepts and returns HTTP or HTTPS messages that contain JSON or XML documents. 

Whenever information is retrieved and displayed, it is read through the REST API, and whenever configuration changes are made, they are written through the REST API.

The REST API also provides a way of subscribing to push-based event notifications, so that when a change occurs in the MIT, an event can be sent through a web socket.

The generic APIC REST API URI looks as follows:

```https://APIC_HOST:port/api/{mo|class}/{dn|classname}.{xml|json}?[options]```

Since the REST API matches one to one the MIT, defining the URI to access a certain resource is important.

&nbsp;

APIC REST API username- and password-based authentication uses a special URI as the DN targets of a POST operation  The special URI are:

-   **aaaLogin**
-   **aaaLogout**
-   **aaaRefresh**

The payloads contain a simple XML or JSON document containing the MO representation of an **aaaUser** object.

**Example 9-1 curl** *Command for Cisco APIC Authentication*

```curl
curl -k -X POST \
    https://sandboxapicdc.cisco.com/api/aaaLogin.json \
    -d '{
        "aaaUser": {
            "attributes": {
                "name": "admin",
                "pwd": "ciscopsdt"
            }
        }
    }
```

**Example 9-2** *Cisco APIC Authentication Response*

```
{
   "totalCount" : "1",
   "imdata" : [
      {
         "aaaLogin" : {
            "attributes" : {
               "remoteUser" : "false",
               "firstLoginTime" : "1572128727",
               "version" : "4.1(1k)",
               "buildTime" : "Mon May 13 16:27:03 PDT 2019",
               "siteFingerprint" : "Z29SSG/BAVFY04Vv",
               "guiIdleTimeoutSeconds" : "1200",
               "firstName" : "",
               "userName" : "admin",
               "refreshTimeoutSeconds" : "600",
               "restTimeoutSeconds" : "90",
               "node" : "topology/pod-1/node-1",
               "creationTime" : "1572128727",
               "changePassword" : "no",
               "token" : "pRgAAAAAAAAAAAAAAAAAAGNPf39fZd71fV6DJWidJoqxJmHt1Fephm-
w6Q0I5byoafVMZ29a6pL+4u5krJ0G2Jdrvl0l2l9cMx/o0ciIbVRfFZruCEgqsPg8+dbjb8kWX02FJLcw9Qp
sg98s5QfOaMDQWHSyqwOObKOGxxglLeQbkgxM8/fgOAFZxbKHMw0+09ihdiu7jTb7AAJVZEzYzXA==",
               "unixUserId" : "15374",
               "lastName" : "",
               "sessionId" : "1IZw4uthRVSmyWWH/+S9aA==",
               "maximumLifetimeSeconds" : "86400"
            }
    ...omitted output
}
```

The response to the POST operation contains an authentication token that will be used in the subsequent API operations as a cookie named **APIC-cookie**.

Example using the cookie:

```
curl -k -X GET \
  https://sandboxapicdc.cisco.com/api/node/class/fabricPod.json \
  -H 'Cookie: APIC-cookie=pRgAAAAAAAAAAAAAAAAAAGNPf39fZd71fV6DJWidJoqxJmHt1Fephmw6Q0
  I5byoafVMZ29a6pL+4u5krJ0G2Jdrvl0l2l9cMx/o0ciIbVRfFZruCEgqsPg8+dbjb8kWX02FJLcw9Qpsg
  98s5QfOaMDQWHSyqwOObKOGxxglLeQbkgxM8/fgOAFZxbKHMw0+09ihdiu7jTb7AAJVZEzYzXA=='
```

&nbsp;

An aCI Python SDK called Cobra can be used for advanced development.  For basic day-to-day configuration and monitoring tasks and for getting started with ACI automation, there is a Python library called ***acitoolkit***.  The ***acitoolkit*** library exposes a subset of the APIC object model that covers the most common ACI workflows.

**Example 9-7** *acitoolkit Example*

```python
# /usr/bin/env python
import sys
import acitoolkit.acitoolkit as aci

APIC_URL = 'https://sandboxapicdc.cisco.com'
USERNAME = 'admin'
PASSWORD = 'ciscopsdt'

# Login to APIC
SESSION = aci.Session(APIC_URL, USERNAME, PASSWORD)
RESP = SESSION.login()
if not REST.ok:
    print('Could not login to APIC')
    sys.exit()

ENDPOINTS = aci.Endpoint.get(SESSION)
print('{0:19s}{1:14s}{2:10s}{3:8}{4:17s}{5:10s}'.format(
    "MAC ADDRESS",
    "IP ADDRESS",
    "ENCAP",
    "TENANT",
    "APP PROFILE",
    "EPG"
))
print('-'*80)

for EP in ENDPOINTS:
    epg = EP.get_parent()
    app_profile = epg.get_parent()
    tenant = app_profile.get_parent()
    print('{0:19s}{1:14}{2:10s}{3:8s}{4:17s}{5:10s}'.format(
        EP.mac,
        EP.ip,
        EP.encap,
        tenant.name,
        app_profile.name,
        epg.name
    ))
```

&nbsp;

#   UCS Manager

&nbsp;

Cisco ***Unified Computing System (UCS)*** encompasses most of the Cisco compute products.  

Cisco UCS provides a unified server solution that brings together the following into one system:

-   ***compute***
-   ***storage***
-   ***networking***

With the release of Cisco HyperFlex and hyperconverged servers, large storage data stores are not included with the UCS solution.

&nbsp;

Cisco UCS B-series blade servers, C-series rack servers, S-series storage servers, UCS Mini, and Cisco HyperFlex hyperconverged servers can all be managed through one interface:  ***UCS Manager***.

UCS Manager provides unified, embedded management of all software and hardware components of Cisco UCS.  Cisco UCS Manager software runs on a pair of hardware appliances called ***fabric interconnects***.  The two fabric interconnects form an active/standby cluster that provides high availability.

The UCS infrastructure that is being managed by UCS Manager forms a UCS fabric that can include up to 160 servers.  The system can scale to thousands of server by integrating individual UCS Manager instances with ***Cisco UCS Central*** in a multidomain Cisco UCS environment.

&nbsp;

UCS Manager participates in the complete server lifecycle, including:

-   server provisioning
-   device discovery
-   inventory
-   configuration
-   diagnostics
-   monitoring
-   fault detection
-   auditing and statistics collection

All infrastructure that is being managed by UCS Manager is either directly connected to the fabric interconnects or connected through ***fabric extenders***.  Fabric extender have the function of offering additional scalability in connecting servers back to the fabric interconnects.

&nbsp;

All Cisco UCS servers support Cisco ***SingleConnect*** technology.

Cisco SingleConnect is technology that supports all traffic from the servers (LAN, SAN, management, and so on) over a single physical link.

&nbsp;

Cisco UCS Manager provides an HTML 5 graphical user interface (GUI), a command-line interface (CLI), and a comprehensive API.

All Cisco UCS fabric functions and managed objects are available over the UCS API.

&nbsp;

With Cisco UCS Manager, the data center servers can be managed using an infrastructure-as-code framework.  This is possible through a Cisco UCS solution called the ***service profile***.  

The ***service profile*** is a logical construct in UCS Manager that contains the complete configuration of a physical server.  All the elements of a server configuration - including RAID levels, BIOS settings, firmware revisions and settings, adapter settings, networking and storage settings, and data center connectivity - are included in the service profile.

When a service profile is associated with a server, Cisco UCS Manager automatically configures the server, adapters, fabric extenders, and fabric interconnects to match the configuration specified in the service profile.

&nbsp;

The UCS Manager programmatic interface is the ***XML API***.  The Cisco UCS Manager XML API accepts XML documents over HTTP or HTTPS connections.

The configuration and state information for Cisco UCS is stored in a hierarchical tree structure known as the ***management information tree (MIT)***.

The MIT, which contains all the managed objects in the Cisco UCS system, is accessible through the XML API.

One or more managed objects can be changed with one API call.  When multiple objects are being configured, the API operation stops if any of the MOs cannot be configured, and a full rollback to the state of the system before the change was initiated is done.

API operations are transactional and are done on the single data model that represent the whole system.

Cisco UCS is responsible for all endpoint communications, making UCS Manager the single source of truth.  Users cannot communicate directly with the endpoints, relieving developers from administering isolated, individual component configurations.

All XML requests are asynchronous and terminate on the active Cisco UCS Manager.

&nbsp;

All the physical and logical components that make up Cisco UCS are represented in a hierarchical ***management information tree (MIT)***, also known as the ***Management Information Model (MIM)***.

Each node in the tree represents a ***managed object (MO)*** or a group of objects that contain its administrative and operational states.

At the top of the hierarchical structure is the ***sys*** object, which contains all the parent and child nodes in the tree.

Each object in Cisco UCS has a unique ***distinguished name*** that describes the object and its place in the tree.

The information model is centrally stored and managed by a process running on the fabric interconnects that is called the ***Data Management Engine (DME)***.  When an administrative change is initiated to a Cisco UCS component, the DME first applies the change to the information model and then applies the changes to the actual management endpoint.  This approach is referred to as ***model-driven framework***.

&nbsp;

A specific managed object in the MIT can be identified by its ***distinguished name (DN)*** or by its ***relative name (RN)***.  *The DN specifies the exact managed object on which the API call is operating and consists of a series of relative names*:

```DN = {RN}/{RN}/{RN}/{RN}...```

*A relative name identifies an object in the context of its parent object.*

&nbsp;

The Cisco UCS Manager XML API model includes the following pragmatic entities:

-   **Classes**:  Classes define the properties and state of objects in the MIT.
-   **Methods**:  Methods define the actions that the API performs on one or more objects.
-   **Types**:  Types are object properties that map values to the object state.

&nbsp;

Several types of ***methods*** are available with the XML API:

-   **Authentication methods**:  These methods, which include the following, are used to authenticate and maintain a session:
    -   **aaaLogin**:  Login method
    -   **aaaRefresh**:  Refreshes the authentication cookie
    -   **aaaLogout**:  Exits the session and deactivates the corresponding authentication cookie
-   **Query methods**:  These methods, which include the following, are used to obtain information on the current configuration state of an object.
    -   **configResolveDn**:  Retrieves objects by DN
    -   **configResolveClass**:  Retrieves objects of a given class
    -   **configResolveParent**:  Retrieves the parent object of an object
-   **Configuration methods**:  These methods, which include the following, are used to make configuration changes to managed objects:
    -   **configConfMo**:  Affects a single MO
    -   **configConfMos**:  Affects multiple subtrees

&nbsp;

Since the query methods available with the XML API can return large sets of data, filters are supported to limit this output to subsets of information.  Four types of filters are available.

-   **Simple filters**:  These true/false filters limits the result set of objects with the Boolean value of True or False.
-   **Property filters**:  These filters use the values of an object's properties as the inclusion criteria in a result set (for example, equal filter, not equal filter, greater than filter)
-   **Composite filters**:  These filters are composed of two or more component filters (for example, AND filter, OR filter)
-   **Modifier filter**:  This filter changes the results of a contained filter.  Currently only the NOT filter is supported.  This filter negates the result of a contained filter

&nbsp;

External applications can get Cisco UCS Manager state change information either by regular polling or by event subscription.  Full event subscription is supported with the API and is the preferred method of notification since polling usually consumes a lot of resources and should be used only in limited situations.

&nbsp;

Cisco UCS Manager provides a managed object browser called ***Visore***.  Visore can be accessed by navigating to ```https://<UCS-Manager-IP>/visore.html```

&nbsp;

***Cisco UCS Platform Emulator*** is the Cisco UCS Manager application bundled into a virtual machine (VM).  The VM includes software that emulates hardware communications for the Cisco UCS system.  The UCS Platform Emulator can be used to create and test a supported Cisco UCS configuration or to duplicate an existing Cisco UCS environment for troubleshooting and development.  

The Cisco UCS Platform Emulator is delivered as an **.ova** file and can run in nearly any virtual environment.

&nbsp;

Example of how to authenticate and get an authentication using **curl**:

```curl
curl -k -X https://10.10.20.11/nuova \
    -H 'Content-Type: application/xml' \
    -d '<aaaLogin inName="ucspe" inPassword="ucspe"></aaaLogin>'
```

Example response:

```xml
<aaaLogin cookie="" response="yes" outCookie="1573019916/7c901636-
c461-487e-bbd0-c74cd68c27be" outRefreshPeriod="600"
outPriv="aaa,admin,ext-lan-config,ext-lan-policy,ext-lan-
qos,ext-lan-security,ext-san-config,ext-san-policy,ext-san-
security,fault,operations,pod-config,pod-policy,pod-qos,pod-
security,read-only" outDomains="org-root" outChannel="noencssl"
outEvtChannel="noencssl" outSessionId="" outVersion="3.2(2.5)"
outName="" />
```

**aaaLogin** specifies the method used to login, **"yes"** confirmed that this is a response, **outCookie** provides the session cookie, **outRefreshPeriod** specifies the recommended cookie refresh period (default of 600 seconds), and **outPriv** specifies the privilege level associated with the account.

Example of using the cookie received to list all objects that are part of the compute class and are being managed by this instance of Cisco UCS Manager using the **configFindDnsByClassId** method:

```curl
curl -k -X POST https://0.10.20.11/nuova \
    -H 'Content-Type: application/xml' \
    -d '<configFindDnsByClassId classId="computeItem" cookie="1573019916/7c901636-c461-487e-bbd0-c74cd68c27be"/>'
```

&nbsp;

The preferred way of working with the XML API is either through Cisco UCS PowerTool suite or the Cisco UCS Python SDK.

*The **Cisco UCS PowerTool** suite is a PowerShell module that helps automate all aspects of Cisco UCS Manager.*

&nbsp;

***Cisco UCS Python SDK*** is a Python module that helps automate all aspects of Cisco UCS management, including server, network, storage, and hypervisor.  

*The Cisco UCS Python SDK works on the Cisco UCS Manager MIT, performing create, read, modify, or delete actions on the managed objects in the tree.*

The Cisco UCS Python module for UCS Manager is called **ucsmsdk** and is available for Python version 2.7 and higher and version 3.5 and higher.  

**ucsmsdk** can be installed by issuing the following command: ```pip install ucsmsdk```

The Cisco UCS Python SDK provides a utility called **convert_to_ucs_python** that gives administrators and developers the option of recording all the interactions with the Cisco UCS Manager GUI and saving them into an XML file.  Running this XML file through the **convert_to_ucs_python** tool automatically generates Python code corresponding to the actions that were performed in the GUI.

&nbsp;

### ***Using ucsmsdk Python SDK***

First, the **UseHandle** class is imported.  An instance of this class is used to connect to Cisco UCS Manager.  the Cisco UCS Manager IP address, username, and password are passed in as parameters to the instance of the **UseHandle** class that is called **HANDLE**.  Several methods are available with the **UseHandle** class.  In this script, only three are used:

-   HANDLE.login():  This method is used to log in to Cisco UCS Manager.
-   HANDLE.query_classid():  This method is used to query the MIT for objects with a specific class ID.
-   HANDLE.logout():  This method is used to log out from the Cisco UCS Manager

The BLADES variable contains a dictionary of all the compute blades that are being managed by the 10.10.20.11 instance of Cisco UCS Manager.  Within a **for** loop, specific information regarding the DN, serial number, administrative state, model number, and total amount of memory for each blade is extracted and displayed to the console.  The Python script using the Cisco UCS Manager SDK that accomplishes all of these tasks looks as shown in Example 9-11

**Example 9-11** *ucsmsdk Python Example*

```python
#! /usr/bin/env python
from ucsmsdkucshandle import UcsHandle

HANDLE = UcsHandle("10.10.20.110", "ucspe", "ucspe")

# Login to Cisco UCS Manager
HANDLE.login()

# Retrieve all the compute blades
BLADES = HANDLE.query_classid("ComputeBlade")

print('{0:23s}{1:8s}{2:12s}{3:14s}{4:6s}'.format(
    "DN",
    "SERIAL",
    "ADMIN STATE",
    "MODEL",
    "TOTAL MEMORY"))
print('-'*70)

# Extract DN, serial number, admin state, model, and total memory for each blade
for BLADE in BLADES:
    print('{0:23s}{1:8s}{2:12s}{3:14s}{4:6s}'.format(
        BLADE.dn,
        BLADE.serial,
        BLADE.admin_state,
        BLADE.model,
        BLADE.total_memory
    ))

HANDLE.logout()
```

&nbsp;

#   Cisco UCS Director

&nbsp;

***Cisco UCS Director*** replaces manual configuration and provisioning processes with orchestration in order to optimize and simplify delivery of data center resources.

Cisco UCS Director is an open private-cloud platform that delivers on-premises infrastructure as a service (IaaS) from the core to the edge of the data center.

&nbsp;

Cisco UCS Director provides comprehensive visibility and management of data center infrastructure components.  From a data center management perspective, the following are some of the tasks that can be performed using Cisco UCS Director:

-   Create, clone, and deploy service profiles and templates for all Cisco UCS servers and compute applications.
-   Manage, monitor, and report on data center components such as Cisco UCS domains or Cisco Nexus devices.
-   Monitor usage, trends, and capacity across a converged infrastructure on a continuous basis.
-   Deploy and add capacity to converged infrastructures in a consistent, repeatable manner.

&nbsp;

Cisco UCS Director also enables the creation of workflows that provide automation services.  This automation workflows can be published and made available to the end users of the data center resources through on-demand portals.

&nbsp;

Cisco UCS Director supports Cisco ACI by offering automation workflows that orchestrate the APIC configuration and management tasks.  It also supports multitenancy and the ability to define contracts between different container tiers.

&nbsp;

Cisco UCS Director can be managed using Cisco ***Intersight***, which is covered later in this chapter.  Cisco UCS Director is a 64-bit appliance that uses the standard templates Open Virtualization Format (OVF) for VMware vSphere and Virtual Hard Disk (VHD) for Microsoft Hyper-V.

&nbsp;

### ***Essential Concepts of Cisco UCS Director orchestrator***

A ***task*** is an atomic unit of work in Cisco UCS Director; it cannot be decomposed into smaller actions and represents a single action with inputs and outputs.  Cisco UCS Director has a task library that contains hundred of predefined tasks.  In the event that there is no suitable predefined task, the system offers the option of creating custom tasks.

&nbsp;

A ***workflow*** is a series of tasks arranged to automate a complex operation.  The simplest workflow contains a single task, but workflows can contain any number of tasks.  

Workflows are built using the ***Workflow Designer***, which is a drag-and-drop interface.  

Every time a workflow is executed, a ***service request*** is generated.  A service request can have one of several states, depending on its execution status:

-   scheduled
-   running
-   blocked
-   completed
-   failed

&nbsp;

***Libraries*** and ***catalogs*** are collections of predefined tasks and workflows that can be used as building blocks for more advanced workflows.

&nbsp;

### ***Programmability and extensibility of Cisco UCS Director***

The Cisco UCS Director SDK is a collection of technologies that enable developers to:

-   expand the capabilities of Cisco UCS Director
-   access Cisco UCS Director data
-   invoke Cisco UCS Director's automation and orchestration operations

The Cisco UCS Director SDK includes the ***Open Automation*** component.  Scripting technologies include the Cisco ***UCS Director PowerShell API***, ***custom tasks*** bundled in Cisco UCS Director ***script modules***, and the ability to write custom tasks using CloupiaScript, a server-side JavaScript implementation.

&nbsp;

The Cisco UCS Director SDK makes the following possible:

-   Accessing Cisco UCS Director programmatically by using the Cisco UCS Director REST API
-   Customizing the Cisco UCS Director by creating custom workflow tasks
-   Extending Cisco UCS Director by using Cisco UCS Director Open Automation to build connectors that support additional devices and systems.

&nbsp;

Cisco UCS Director provides the Cisco UCS Director ***Open Automation module*** to enable developers to enhance the functionality of the Cisco UCS Director appliance.  Open Automation can be used to add more modules to Cisco UCS Director.  

A ***module*** is the topmost logical entry point into Cisco UCS Director.  In order to add or extend the functionality of the system, a new module must be developed and deployed on Cisco UCS Director.

Open Automation is a Java SDK and framework that contains all the resources needed to develop new modules.

Some of the use cases for Open Automation:

-   Adding the ability to control a new type of device with Cisco UCS Director
-   Designing custom menus for displaying new devices or components
-   Taking inventory of new devices
-   Developing custom Cisco UCS Director reports and report actions
-   Developing tasks that can be used in workflows

&nbsp;

***Custom tasks*** enable developer to perform customized operations on Cisco UCS Director resources.  

Custom tasks are written using CloupiaScript.  

&nbsp;

***Script modules*** are used to integrate third-party JARs (Java Archives) and custom libraries with Cisco UCS Director to add custom functionality to the Cisco UCS Director user interface.

***Script modules*** have very different roles than ***script bundles***.  Script bundles are packaged collections of workflow tasks that are released with Cisco UCS Director, whereas script modules make it possible to add custom functionality to Cisco UCS Director.

&nbsp;

Cisco ***UCS Director PowerShell*** console is a Cisco-developed application that provides a PowerShell interface to Cisco UCS Director REST API.  The console provides a set of PowerShell cmdlets wrapped in a module to internally invoke the REST APIs over HTTP.  Each cmdlet performs a single operations.  Cmdlets can be chained together to accomplish more advanced automation and data center management tasks.

&nbsp;

### ***Cisco UCS Director REST API***
Cisco UCS Director offers a REST API that enables applications to consume or manipulate the data stored in Cisco UCS Director.  Applications use HTTP or HTTPS requests from the REST API to perform Create/Read/Update/Delete (CRUD) operations on Cisco UCS Director resources.  

The API accepts and returns HTTP messages that contain JavaScript Object Notation (JSON) or Extensible Markup Language (XML) documents.

To access the Cisco UCS Director REST API, a valid user account and an API access key are needed.  Cisco UCS Director uses the API access key to authenticate an API request.  The access key is a unique security access code that is associated with a specific Cisco UCS Director user account.  In order to retrieve the API access key for a specific user, you must first log in to Cisco UCS Director with a specific user account, then however the mouse over the user icon in the top-right corner and select **Edit My Profile** from the drop-down list.  On the **Edit My Profile** page, select **Show Advanced Settings** and retrieve the API access key from the **REST API Access Key** area.  There is also an option to regenerate the key, if necessary.

&nbsp;

Each REST API request must be associated with an HTTP header called **X-Cloupia-Request-Key**, with its value set to the REST API access key retrieved previously.  The REST API request must contain a valid URL of the following format:  

```https://Cisco_UCS_Director/app/api/rest?formatType=json&opName=operationName=operationName&opData=operationaData```

-   **Cisco_UCS_Director**:  This is the IP address or hostname of the Cisco UCS Director VM
-   **formatType**:  This can be either JSON or XML; it is JSON in this case.  (Only JSON is discussed throughout the rest of this chapter.)
-   **opName**:  This is the API operation name that is associated with the request (for example, userAPIGetMyLoginProfile).
-   **opData**:  This contains the parameters or the arguments associated with the operation.  Cisco UCS Director uses JSON encoding for the parameters.  If an operation doesn't require any parameters, the empty set {} should be used.  When building the URL, escape characters should be encoded as appropriate.

&nbsp;

**Example 9-12** ***curl** Command to Retrieve the User Profile in Cisco UCS Director*

```curl
curl -k -L -X GET \
    -g 'https://10.10.10.66/app/api/rest?formatType=json&opName=userAPIGetMyLoginProfile&opData={}' \
    -H 'X-Cloupia-Request-Key: 8187C34017C3479089C66678F32775FE'
```

For this request, the **-g** parameter disables the **curl** check for nested braces **{}**, the **-k** or **-insecure** parameter allows **curl** to proceed and operate even if the server uses self-signed SSL certificates, and the **-L** parameter allows curl to follow the redirects sent by the server.

The URL for the request follows the requirements using the **/app/api/rest** endpoint to access the REST API and then passes the **formatType**, **opName**, and **opData** as parameters.  The HTTP header for authentication is named **X-Cloupia-Request-Key** and contains the value of the access key for the admin user.

**Example 9-13** *REST API Response Containing User Profile Information*

```json
{
   "opName" : "userAPIGetMyLoginProfile",
   "serviceName" : "InfraMgr",
   "serviceResult" : {
      "email" : null,
      "groupName" : null,
      "role" : "Admin",
      "userId" : "admin",
      "groupId" : 0,
      "firstName" : null,
      "lastName" : null
   },
   "serviceError" : null
}
```

The operation name is contained in the response and is indeed **userAPIGetMyLoginProfile**, **serviceName** specifies the name of the back-end service (which is in the most cases **InfraMgr**), **serviceResult** contains a set of name/value pairs or a JSON object if the request was successful, and **serviceError** contains the error message.  If the request succeeds, the **serviceError** value is set to null, and if the operation fails, **serviceError** contains the error message.

&nbsp;

#   Cisco Intersight

&nbsp;

The Cisco Intersight platform provides intelligent cloud-powered infrastructure management for Cisco UCS and Cisco HyperFlex platforms.  Cisco UCS and Cisco HyperFlex use model-based management to provision servers and the associated storage and networking automatically.  Cisco Intersight works with Cisco UCS Manager and Cisco ***Integration Management Controller (IMC)*** to bring the model-based management of Cisco compute solutions into one unified management solution.  Cisco Intersight offers deployment options as either software as a service (SaaS) on https://intersight.com or running on a Cisco Intersight virtual appliance on premesis.

Some of the benefits of using Cisco Intersight:

-   It simplifies Cisco UCS and Cisco HyperFlex management with a single management platform.
-   It makes it possible to scale across data center and remote locations without additional complexity.
-   It automates the generation and forwarding of technically support files to the Cisco Technical Assistance Center to accelerate the troubleshooting process.
-   Full programmability and automation capabilities are available through a REST API interface.
-   A streamlined upgrade process is available for standalone Cisco UCS servers.

&nbsp;

Getting started with Cisco Intersight involves the following steps:

-   Step1.  Log in to https://intersight.com with a Cisco ID account.
-   Step 2.  Claim a device for the account.  Endpoint devices connect to the Cisco Intersight portal through a device connector that is embedded in the management controller of each system.
-   Step 3.  (Optional) Add additional users to the new account.  Several roles are available, including read-only and admin roles.  Custom roles can be created, if needed.

&nbsp;

Cisco Intersight includes a REST API interface built on top of the OpenAPI specifications.

The API accepts and returns messages that are encapsulated in JSON documents and are sent over HTTPS.

The Intersight API is a programmatic interface to the Management Information Model (MIM) that is similar to Cisco ACI and Cisco UCS Manager.  Similar to those the Cisco Intersight MIM is composed of managed objects (MOs).  Managed objects or REST API resources are uniquely identified by URI (uniform resource identifier) or distinguished name (DN).

Cisco Intersight managed objects are represented using a class hierarchy specified in the OpenAPI specification  All the API resources are descendant of the **mo.MO** class.

**Table 9-2** Common Properties for All Managed Objects in Cisco Intersight

| Property Name | Description |
| -- | -- |
| Moid | A unique identifier of the managed object instance. |
| ObjectType | The fully qualified class name of the managed object. |
| AccountMoid | The Intersight account ID for the managed object | 
| CreateTime | The time when the managed object was created. |
| ModTime | The time when the managed object was last modified.  **ModTime** is automatically update whenever at least one property of the managed object is modified. |
| Owners | An array of owners, which represents effective ownership of the object. |
| Tags | Any array of tags that allow the addition of key/value metadata to managed objects. |
| Ancestors | An array containing the MO references of the ancestors in the object containment hierarchy. |
| Parent | The direct ancestor of the managed object in the containment hierarchy. |

Every managed object has a unique **Moid** identifier assigned when the resource is created.  The **Moid** is used to uniquely distinguish a Cisco Intersight resource from all the other resources.  The **Moid** is a 12-byte string set when a resource is created.

&nbsp;

Each managed object can be addressed using a unique uniform resource identifier (URI) that includes the **Moid**.  The URI can be used in any HTTPS request to address the managed object.  A generic Cisco Intersight URI is of the following form:

```https://intersight.com/path[?query]```

&nbsp;

The URI of a managed object includes the following:

-   **https**:  The HTTPS protocol
-   **intersight.com**:  The Cisco Intersight hostname
-   *path*:  The path, organized in hierarchical form.
-   *query*:  An optional query after the question mark and typically used to limit the output of the response to only specific parameters.

For example, the URI of an object with Moid 48601f85ae74b80001aee589 could be:

```https://intersight.com/api/v1/asset/DeviceRegistrations/48601f85ae74b80001aee589```

&nbsp;

Every managed object in the Cisco Intersight information model supports ***tagging***.  Tagging is used to categorize objects by a certain common property, such as owner, geographic location, or environment.  Tags can be set and queried through the Intersight API.  Each tag consists of a key and an optional value.  Both the key and the value are of type string.

&nbsp;

Managed objects may include object relationships, which are dynamic links to REST API resources.  Cisco Intersight uses ***Hypermedia as the Engine of Application State (HATEOAS)***.

&nbsp;

Intersight provides a rich query language based on the OData standard.  The query language is represented using URL query parameters for GET results.  Several types of data are supported with Intersight queries, including:

-   string
-   number
-   duration
-   date and time
-   time of day

&nbsp;

When a client sends an API request, the Intersight web service must identify and authenticate the client.  The Intersight web server supports two authentication methods:

-   **API Keys**
-   **Session cookies**

&nbsp;

An Intersight API key is composed of a ***keyId*** and a ***keySecret***.  The API client uses the API key to cryptographically sign each HTTP request sent to the Intersight web service.  The "**signature**" parameter is a based 64-encoded digital signature of the HTTP headers and message content.  API keys are generated in the **Settings > API** section of the Intersight web service.  Best practice recommends to generate a separate API key for each client application that needs access to the API.

&nbsp;

***Cookies*** are used primarily by the Intersight GUI client running in a browser.  When accessing the Intersight web service, end users must first authenticate to **https://sso.cisco.com**.  When authentication is successful, sso.cisco.com sends a signed SAML assertion to the Intersight web service, and Intersight generates a session cookie with limited time span validity.  The client must send the session cookie in each API request.

&nbsp;

**Example 9-16** *Intersight Python Module Example*

```python
#! /usr/bin/env python
from intersight.intersight_api_client import IntersightApiClient
from intersight.apis import equipment_device_summary_api

# Create an Intersight API Client instance
API_INSTANCE = IntersightApiClient(
    host="https://intersight.com/api/v1",\
        private_key="/Path_to/SecretKey.txt",\
            api_key_ip="your_own_api_key_ip"
)

# Create an equipment deviceh andle
D_HANDLE = equipment_device_summary_api.EquipmentDeviceSummaryApi(API_INSTANCE)
DEVICES = D_HANDLE.equipment_device_summaries_get().results

print('{0:35s}{1:40s}{2:13s}{3:14s}'.format(
    "DN",
    "MODEL",
    "SERIAL",
    "OBJECT TYPE"))
print('-'*105)

# Loop through devices and extract data
for DEVICE in DEVICES:
    print('{0:35s}{1:40s}{2:13s}{3:14s}'.format(
        DEVICE.dn,
        DEVICE.model,
        DEVICE.serial,
        DEVICE.source_object_type
    ))
```

&nbsp;

The first two lines of Example 9-16 use the **import** keyword to bring in and make available for later consumptions t
he **IntersightApiClient** Python class that will be used to create a connection to the cisco Intersight platform and the **equipment_device_summary_api** file, which contains Python objects that are useful for retrieving equipment that is being managed by Intersight.  Every Cisco Intersight REST API endpoint has a corresponding Python file containing classes and methods that can be used to programmatically process those REST API endpoints.  Next, an instance of the **IntersightApiClient** class is created in order to establish a correction and have a hook back to the Cisco Intersight platform.  Three parameters need to be passed in to instantiate the class:

-   **host**:  This parameter specifies the Cisco REST API base URL.
-   **private_key**:  This parameter specifies the path to the file that contains the keySecret of the Intersight account that will be used to sign in.
-   **api_key_id**:  This parameter contains the keyId of the same Intersight account.  As mentioned previously, both the keyId and keySecret are generated int he Intersight web interface, under Settings > API keys.

Next an instance of the **EquipmentDeviceSummaryApi** class is created and stored in the **D_HANDLE** variable.  This Python class maps into the **/api/v1/equipment/DeviceSummaries** REST API resource.  The **equipment_device_summaries_get** method that is available with the **EquipmentDeviceSummaryApi** class is invoked next, and the results are stored in the **DEVICES** variable, which contains a complete list of all the equipment that is being managed by Cisco Intersight for the user account that the keyId and keySecret with which the initial connection was established.  The **for** loop iterates over the devices in the list and extracts for each one of the distinguished name, model, serial number, and object type and displays this information to the console.