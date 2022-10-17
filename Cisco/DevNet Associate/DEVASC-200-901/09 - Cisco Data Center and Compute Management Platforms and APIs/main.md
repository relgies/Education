#  Cisco Data Center and Compute Management Platforms and APIs

## Cisco ACI

&nbsp;

Cisco ***Application Centric Infrastructure (ACI)*** is the SDN-based solution from Cisco for data center deployment, management, and monitoring.  The solution is based on two components: the Cisco Nexus family of switches and Cisco ***Application Policy Infrastructure Controller (APIC)***

&nbsp;

> ***`Key topic`***

&nbsp;

The Cisco Nexus 9000 family of switches can run in two separate modes of operation, depending on the software loaded on them.  The first mode is called standalone (or NX-OS) mode, which means the switches act like regular Layer 2 / Layer 3 data center devices that are usually managed individually.  In the second mode, ACI mode, the Cisco Nexus devices are part of an ACI fabric and are managed in a centralized fashion.  The central controller for the ACI fabric is the Cisco Application Policy Infrastructure Controller (APIC).  This controller is the main architectural component of the Cisco ACI solution and provides a single point of automation and management for the Cisco ACI fabric, policy enforcement, and health monitoring.  The Cisco APIC was built on an API-first architecture from its inception.  On top of this API, a command-line interface (CLI) and a graphical user interface (GUI) have been developed.  The API is exposed through a REST interface and is accessible as a northbound interface for users and developer to integrated and develop their own custom solutions on top of the Cisco APIC and Cisco ACI fabric.  The Cisco APIC interacts with and manages the Cisco Nexus switches through the OpFlex protocol, which is exposed as a southbound interface.  From an SDN controller perspective (similar to the Cisco DNA Center controller described in Chapter 8, "Cisco Enterprise Networking Management Platforms and APIs"), a northbound interface specifies the collection of protocols that a user can use to interact with and program the controller, while a southbound interface specifies the protocols and interfaces that the controller uses to interact with the devices it manages.  Some of the features and capabilities of the Cisco APIC are as follows:

*   Application-centric network policy for physical, virtual, and cloud infrastructure
*   Data model-based declarative provisioning 
*   Designed around open standards and open APIs
*   Cisco ACI fabric inventory and configuration
*   Software image management
*   Fault, event, and performance monitoring and management
*   Integration with third-party management systems such as VMware, Microsoft, OpenStack
*   Cloud APIC appliance for Cisco cloud ACI deployments in public cloud environments

A minimum of three APICs in a cluster are needed for high availability.

&nbsp;

> ***`Key Topic`***

&nbsp;

The Cisco ACI fabric is built in a leaf-and-spine architecture.  As the name implies, some of the Cisco Nexus switches that are part of the ACI fabric are called *leaves* and perform a function similar to that of an access switch, to which both physical and virtual endpoint servers are connected, and some of the switches are called *spines* and perform a function similar to that of a distribution switch to which all the access switches are connected.  Figure 9-1 provides a visual representation of how all the Cisco ACI fabric components come together.

&nbsp;

**Figure 9-1** *Cisco ACI Fabric Architecture*

>   Two Spine Nexus 9000 switches both connect to three Leaf Nexus 9000 switches.  The three Leaf Nexus 9000 switches not only connect to each of the Spine Nexus 9000 switches but then also have multiple connections to the ACI Cluster containing three APICs as well as another block of End Points.

&nbsp;

It is very important to choose the right switches for the right functions as not all Cisco Nexus 9000 switches support all functions in a leaf-and-spine architecture.  The leaf switches connect to all the spine switches and to endpoint devices, including the Cisco APICs.  The Cisco APICs never connect to spine switches.  Spine switches can only connect to leaf switches and are never interconnected with each other.  The ACI fabric provides consistent low-latency forwarding across high-bandwidth links (40 Gbps, 100 Gbps, and 400 Gbps).  Data traffic with the source and destination on the same leaf switch is handled locally.  When the traffic source and destination are on separate leaf switches, they are always only one spine switch away.  The whole ACI fabric operates as a single Layer 3 switch, so between a data traffic source and destination, it will always be at most one Layer 3 hop.

&nbsp;

>   ***`Key Topic`***

&nbsp;

The configuration of the ACI fabric is stored in the APIC using an object-oriented schema.  This configuration represents the logical model of the fabric.  The APIC compiles the logical model and renders the policies into a concrete model that runs in the physical infrastructure.

&nbsp;

**Figure 9-2** *Relationship Between the Logical Model, the Concrete Model, and the Operating System*

>  There are three blocks on top of each other.  The top block of the Logical Model block, beneath that is the Concrete Model block, and below that is the NX-OS block.  Beside them are arrows that show that from the Logical Model to the Concrete Model is Policy Element and from the Concrete Model block to the NX-OS block is the NX-OS.

&nbsp;

Each of the switches contains a complete copy of the concrete model.  When a policy that represents a configuration is created in the APIC, the controller updates the logical model.  It then performs the intermediate step of creating a complete policy that it pushes into all the switches, where the concrete model is updated.  The Cisco Nexus 9000 switches can only execute the concrete model when running in ACI mode.  Each switch has a copy of the concrete model.  If by any chance, all the PAIC controllers in a cluster go offline, the fabric keeps functioning, but modifications to the fabric policies are not possible.

&nbsp;

The ACI policy model enables the specification of application requirements.  When a change is initiated to an object in the fabric, the APIC first applies that change to the policy model.  This policy model change triggers a change to the concrete model and the actual managed endpoint.  This management framework is called the ***model-driven framework***.  In this model, the system administrator defines the desired state of the fabric but leaves the implementation up to the APIC.  This means that the data center infrastructure is no longer managed in isolated, individual component configurations but holistically, enabling automation and flexible workload provisioning.  In this type of infrastructure, network-attached services can be easily deployed as the APIC provides an automation framework to manage the complete lifecycle of these services.  As workloads move and changes happen, the controller reconfigures the underlying infrastructure to ensure that the policies are still in place for the end hosts.

&nbsp;

> ***`Key Topic`***

&nbsp;

The Cisco ACI fabric is composed of physical and logical components.  These components are recorded in the ***Management Information Model (MIM)*** and can be represented in a ***hierarchical management information tree (MIT)***.  Each node in the MIT represents a managed object (MO).  An MO can represent a concrete object, such as a switch, an adapter, a power supply, or a logical object, such as an application profile, an endpoint group, or an error message.  All the components of the ACI fabric can be represented as managed objects.  

&nbsp;

The MIT hierarchical structure starts at the top with the root object and contains parent and child nodes.  Each node in the tree is an MO, and each object in the fabric has a distinguished name (DN).  The DN describes the object and specifies its location in the tree.  The following managed objects contain the policies that control the operation of the fabric:

-   **APICs**:  These are the clustered fabric controllers that provide management, application, and policy deployment for the fabric.
-   **Tenants**:  Tenants represent containers for policies that are grouped for a specific access domain.  The following four kinds of tenants are currently supported by the system:
    -   **User**:  User tenants are needed by the fabric administrator to cater to the needs of the fabric users.
    -   **Common**:  The common tenant is provided by the system and can be configured by the fabric administrator.  This tenant contains policies and resources that can be shared by all tenants.  Examples of such resources are firewalls, load balancers, and intrusion detection systems.
    -   **Infra**:  The infra tenant is provided by the system and can be configured by the fabric administrator.  It contains policies that manage the operation of infrastructure resources.
    -   **Management**:  The management tenant is provided by the system and can be configured by the fabric administrator.  This tenant contains policies and resources for in-band and out-of-band configuration of fabric nodes.
-   **Access policies**:  These policies control the operation of leaf switch access ports, which provide fabric connectivity to resources such as virtual machine hypervisors, compute devices, storage devices, and so on.  Several access policies come built in with the ACI fabric by default.  The fabric administrator can tweak these policies or create new ones, as necessary.
-   **Fabric policies**:  These policies control the operation of the switch fabric ports.  Configurations for time synchronization, routing protocol,s and domain name resolution are managed with these policies.
-   **VM domains**:  Virtual machine (VM) domain group virtual machine controllers that require similar networking policies configurations.  The APIC communicates with the VM controller to push network configurations all the way to the VM level.
-   **Integration automation framework**:  The Layer 4 to Layer 7 service integration automation framework enables a system to respond to services coming online or going offline.
-   **AAA policies**:  Access, authentication, and account (AAA) policies control user privileges, roles, and security for the ACI fabric.

&nbsp;

The hierarchical policy model fits very well with the REST API interface.  As the ACI fabric perform its functions, the API reads and writes to objects in the MIT.  The API resources represented by URLs map directly into the distinguished names that identify objects in the IT.

&nbsp;

Next, let's explore the building blocks of the Cisco ACI fabric policies

&nbsp;

>   ***`Key Topic`***

&nbsp;

####  **Building Blocks of Cisco ACI Fabric Policies**

&nbsp;

Tenants are top-level MOs that identify and separate administrative control, application policies, and failure domains.  A tenant can represent a customer in a managed service provider environment or an organization in an enterprise environment, or a tenant can be a convenient grouping of objects and policies.  A tenant's sublevel objects can be grouped into two categories: tenant networking and tenant policy.  Figure 9-4 provides a graphical representation of how a tenant is organized and the main networking and policy components.

&nbsp;

**Figure 9-4** *Cisco ACI Tenant Components*

>  Top level bar is Uni.  Below that is a bar named Tenant A.  Beneath Tenant A are two blocks next to each other.  The Networking block on the left has four blocks inside of it: VRFs, Bridge Domains, Subnets, and External Networks.  The Policy block on the right has four blocks inside of it: Application Profiles, EPGs, Contracts, and Filters.

&nbsp;

The tenant networking objects provide Layer 2 and Layer 33 connectivity between the endpoints and consist of the following constructs: VRF (virtual routing and forwarding) instances, bridge domains, subnets, and external networks.  Figure 0-5 displays in more details how the tenant networking constructs are organized.

&nbsp;

**Figure 9-5** *Cisco ACI Tenant Networking Components*

>  There are two examples side by side.  On the left there is a Tenant A block with a VRF A block below it.  Beneath this are two blocks side-by-side.  On the left, there is a Bridge Domain block with a Subnet A block inside of it.  On the right there is a Bridge Domain block with two blocks inside of it: Subnet B and Subnet C.  On the next example is Tenant B with VRF B below it.  Then beneath this is two blocks with the block of the left being Bridge Domain with Subnet A inside of it and the block on the right being Bridge domain with Subnet D inside of it.

&nbsp;

VRF instances, also called ***contexts*** and ***private networks***, are isolated routing tables.  A VRF instance defines a Layer 3 address domain.  A tenant can contain one or multiple VRF instances.  VRF instances exist on any leaf switch that has a host assigned to the VRF instance.  All the endpoints within a Layer 3 domain must have unique IP addresses because traffic can flow between these devices if allowed by the policy.

&nbsp;

Bridge domains represent the Layer 2 forwarding domains within the fabric and define the unique MAC address space and flooding domain for broadcast, unknown unicast, and multicast frames.  Each bridge domain is associated with only one VRF instance, but a VRF instance can be associated with multiple bridge domains.  Bridge domains cna contain multiple subnets, which is different from regular VLANs, which are usually associated with only one subnet each.

&nbsp;

Subnets are the Layer 3 networks that provide IP address space and gateway services for endpoints to be able to connect to the network.  Each subnet is associated with only one bridge domain.  Subnets can be the following:

-   **Public**:  A subnet can be exported to a routed connection.
-   **Private**:  A subnet is confined within its tenant.
-   **Shared**:  A subnet can be shared and exposed in multiple VRF instances in the same tenant or across tenants as part of a shared service.

&nbsp;

External bridged networks connect the ACI fabric to legacy Layer 2/Spanning Tree Protocol networks.  This is usually needed as part of the migration process from a traditional network infrastructure to an ACI network.

&nbsp;

External routed networks create a Layer 3 connection with a network outside the ACI fabric.  Layer 3 external routed networks can be configured using static routes or routing protocols such as BGP, OSPF, and EIGRP.

&nbsp;

The tenant policy objects are focused on the policies and services that the endpoints receive.  The tenant policy consists of application profiles, endpoint groups (EPGs), contracts, and filters.  Figure 9-6 shows how the tenant policy objects, application profiles, and EPGs are organized in different bridge domains.

&nbsp;

**Figure 9-6** *Cisco ACI Tenant Policy Components*

>   Tenant A block at the top, below that is a VRF A block.  Beneath that are two Bridge Domain blocks next to each other.  The Bridge Domain block on the left has a Subnet A block inside of it while the Bridge Domain block on the right has two blocks inside of it:  Subnet B and Subnet C.  Beneath the Bridge Domain block on the left is an Application Profile 1 block, and beneath it are two EPG blocks side by side.  The Bridge Domain block on the right has an Application PRofile 2 block underneath it with two EPG blocks next to each other.

&nbsp;

An application profile defines the policies, services, and relationship between EPGs.  An application profile contains one or more EPGs.  Applications typically contain multiple components, such as a web-based front end, an application logical layer, and one or more databases in the back end.  The application profile contains as many EPGs as necessary, and these EPGs are logically related to providing the capabilities of the application.

&nbsp;

>   ***`Key Topic`***

&nbsp;

The EPG is the most important object in the policy model.  An EPG is a collection of endpoints that have common policy requirements, such as security, virtual machine mobility, QoS, or Layer 4 to Layer 7 services.  In the Cisco ACI fabric, each endpoint has an identity represented by its address, a location, and attributes, and it can be physical or virtual.  Endpoint examples include servers, virtual machines, clients on the internet, and network-attached storage devices.  Rather than configure and manage endpoints individually, you can place them in EPGs and manage them as a group.  Policies apply to EPGs and never to individual endpoints.  Each EPG can only be related to one bridge domain.

&nbsp;

Contracts define the policies and services that get applied to EPGs.  Contracts can be used for redirecting service to a Layer 4 to Layer 7 device, assigning QoS values, and controlling the traffic flow between EPGs.  EPGs can only communicate with other EPGs based on contract rules.  Contracts specify the protocols and ports allowed between EPGs.  EPGs can only communicate with other EPgs based on contract rules.  Contracts specify the protocols and ports allowed between EPGs.  If there is no contract, inter-EPG communication is disabled by default.  For intra-EPG communication, no contract is required as this traffic is always allowed by default.  The relationship between an EPG and a contract can be either a consumer or a provider.  EPG providers expose contracts with which a consumer EPG must comply.  When an EPG consumes a contract, the endpoints in the consuming EPG cna initiate communication with any endpoint from the provider EPG.  Figure 9-7 displays this contractual relationship between providing and consuming EPGs.

&nbsp;

**Figure 9-7** *Cisco ACI Application Profiles and Contracts*

>   Application Profile at the top left.  Beneath it are two boxes.  Box one is EPG Web Consume APP Contract, the other box is EPG DB Consume APP Contract.  Both point to the cisco Contract APP.  To the right of it is a box that says EPG APP Provide APP Contract which is also pointing to the Contract APP.

&nbsp;

Filters are the objects that define protocols and port numbers used in contracts.  Filter objects can contain multiple protocols and ports, and contracts can consume multiple filters.

&nbsp;

### **APIC REST API**

&nbsp;

As mentioned previously, the APIC REST API is a programmatic interface that uses the REST architecture.  The API accepts and returns HTTP or HTTPS messages that contain JSON or XML documents.  Any programming language can be used to generate the messages and the JSON or XML documents that contain the API methods or managed objet (MO) attributes.  Whenever information is retrieved and displayed, it is read through the REST API, and whenever configuration changes are made, they are written through the REST API.  The REST API also provides a way of subscribing to push-based event notifications, so that when a change occurs in the MIT, an event can be sent through a web socket.

&nbsp;

>   ***`Key Topic`***

&nbsp;

The generic APIC REST API URI looks as follows:

&nbsp;

**`https://APIC_Host:port/api/{mo|class}/{dn|classname}.{xml|json}?[options]`**

&nbsp;

Since the REST API matches one to one the MIT, defining the URI to access a certain resource is important.  First, you need to define the protocol (http or https) and the hostname or IP address of the APIC instance.  Next, **/api** indicates that the API is invoked.  After that, the next part of hte URI specifies whether the operation will be for an MO or a class.  The next component defines either the fully qualified domain name for MO-based queries or the class name for class-based queries.  The final mandatory part of the request is the encoding format, which can be either XML or JSON.  (The APIC ignores Content-Type and other headers, so the method just explained is the only one accepted.)  The complete Cisco ACI REST API documentation with information on how to use the API, all of the API endpoints, and operations available can be found at https://developer.cisco.com/docs/aci.

&nbsp;

APIC REST API username- and password-based authentication uses a special URI, including aaaLogin, aaaLogout, and aaaRefresh as the DN targets of a POST operation.  The payloads contain a simple XML or JSON document containing the MO representation of an aaaUser object.  The following example uses the Cisco DevNet always-on APIc instance available at https://sandboxapicdc.disco.com with username value or **admin** and a password of **ciscopsdt** to show how to interact with an ACI fabric using the APIC REST API interface.  Using **curl**, the authentication aPI call should look as show in example 9-1.

&nbsp;

**Example 9-1** ***curl** Command for Cisco APIC Authentication*

```
curl -k - X POST \
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

&nbsp;

The returned information from the APIC should look as shown in Example 9-2

&nbsp;

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

&nbsp;

The response to the POST operation contains an authentication token that will be used in the subsequent API operations as a cookie named **APIC-cookie**.

&nbsp;

Next, let's get a list of all the ACI fabrics that are being managed by this APIc instance.  The URI for this GET operation is `https://sandboxapicdc.cisco.com/api/node/class/fabricPod.json`, and the **APIC-cookie** header, is specified for authentication purposes.

&nbsp;

The **curl** request should look similar to the one shown in Example 9-3.

&nbsp;

**Example 9-3** ***curl** Command to get a List of All ACI Fabric*

```
curl -k -X GET \
  https://sandboxapicdc.cisco.com/api/node/class/fabricPod.json \
  -H 'Cookie: APIC-cookie=pRgAAAAAAAAAAAAAAAAAAGNPf39fZd71fV6DJWidJoqxJmHt1Fephmw6Q0
  I5byoafVMZ29a6pL+4u5krJ0G2Jdrvl0l2l9cMx/o0ciIbVRfFZruCEgqsPg8+dbjb8kWX02FJLcw9Qpsg
  98s5QfOaMDQWHSyqwOObKOGxxglLeQbkgxM8/fgOAFZxbKHMw0+09ihdiu7jTb7AAJVZEzYzXA=='
```

&nbsp;

The response received from this instance of the APIC should look like the one in Example 9-4.

&nbsp;

**Example 9-4** ***curl** Command Response with a List of All ACI Fabrics*

```
{
   "totalCount" : "1",
   "imdata" : [
      {
         "fabricPod" : {
            "attributes" : {
               "id" : "1",
               "monPolDn" : "uni/fabric/monfab-default",
               "dn" : "topology/pod-1",
               "status" : "",
               "childAction" : "",
               "modTs" : "2019-10-26T18:01:13.491+00:00",
               "podType" : "physical",
               "lcOwn" : "local"
            }
         }
      }
   ]
}
```

&nbsp;

From this response, we can see that the always-on Cisco DevNet Sandbox APIC instance manages only one ACI fabric, called pod-1.  Next, let's find out more information about pod-1 and discover how many devices are part of this fabric.  The API URI link for the resource that will return this information is `https://sandboxapicdc.cisco.com/api/node/class/topology/pod-1/topSystem.json`.  We specify again the **APIC-cookie**, and the **GET** request should look like the one in Example 9-5.

&nbsp;

**Example 9-5** ***curl** Command to Get ACI Pod Information*

```
curl -k -X GET \
  https://sandboxapicdc.cisco.com/api/node/class/topology/pod-1/topSystem.json \
  -H 'Cookie: APIC-cookie=pRgAAAAAAAAAAAAAAAAAAGNPf39fZd71fV6DJWidJoqxJmHt1Fephmw6Q0
  I5byoafVMZ29a6pL+4u5krJ0G2Jdrvl0l2l9cMx/o0ciIbVRfFZruCEgqsPg8+dbjb8kWX02FJLcw9Qpsg
  98s5QfOaMDQWHSyqwOObKOGxxglLeQbkgxM8/fgOAFZxbKHMw0+09ihdiu7jTb7AAJVZEzYzXA=='
```

&nbsp;

The redacted response from the APIC should look similar to the one shown in Example 9-6.

&nbsp;

**Example 9-6** *REST API Response Containing Details About the Cisco ACI Pod*

```
{
   "imdata" : [
      {
         "topSystem" : {
            "attributes" : {
               "role" : "controller",
               "name" : "apic1",
               "fabricId" : "1",
               "inbMgmtAddr" : "192.168.11.1",
               "oobMgmtAddr" : "10.10.20.14",
               "systemUpTime" : "00:04:33:38.000",
               "siteId" : "0",
               "state" : "in-service",
               "fabricDomain" : "ACI Fabric1",
               "dn" : "topology/pod-1/node-1/sys",
               "podId" : "1"
            }
         }
      },
      {
         "topSystem" : {
            "attributes" : {
               "state" : "in-service",
               "siteId" : "0",
               "address" : "10.0.80.64",
               "fabricDomain" : "ACI Fabric1",
               "dn" : "topology/pod-1/node-101/sys",
               "id" : "101",
               "podId" : "1",
               "role" : "leaf",
               "fabricId" : "1",
               "name" : "leaf-1"
            }
         }
     },
      {
         "topSystem" : {
            "attributes" : {
               "podId" : "1",
               "id" : "102",
               "dn" : "topology/pod-1/node-102/sys",
               "address" : "10.0.80.66",
               "fabricDomain" : "ACI Fabric1",
               "siteId" : "0",
               "state" : "in-service",
 
               "role" : "leaf",
               "name" : "leaf-2",
               "fabricId" : "1"
            }
         }
      },
      {
         "topSystem" : {
            "attributes" : {
               "fabricId" : "1",
               "name" : "spine-1",
               "role" : "spine",
               "podId" : "1",
               "id" : "201",
               "dn" : "topology/pod-1/node-201/sys",
               "state" : "in-service",
               "siteId" : "0",
               "fabricDomain" : "ACI Fabric1",
               "address" : "10.0.80.65"
            }
         }
      }
   ],
   "totalCount" : "4"
}
```

&nbsp;

From the response, we can see that this ACI fabric is made up of four devices: an APIC, two leaf switches, adn one spine switch.  Extensive information is returned about each device in this response, but it was modified to extract and display just a subset of that information.  You are encouraged to perform the same steps and explore the APIC REST API either using the Cisco DevNet sandbox resources or your own instance of APIC.

&nbsp;

>   ***`Key Topic`***

&nbsp;

Asa of this writing, there are several tools and libraries available for Cisco ACI automation.  An ACI Python SDK called Cobra can be used for advanced development.  For basic day-to-day configuration and monitoring tasks and for getting started with ACI automation, there is also a Python library called **acitoolkit**.  The acitoolkit library exposes a subset of the APIC object model that covers the most common ACI workflows.

&nbsp;

Next, we will use acitoolkit to build a Python script that retrieves all the endpoints from an ACI fabric.  Additional information about the endpoints - such as the EPGs they are members of, application profiles that are applied to those EPGs, and the tenant membership, encapsulation, MAC, and IP addresses - will be displayed for each endpoint.  A Python script that uses acitoolkit and accomplishes these tasks might look as the one shown in Example 9-7.

&nbsp;

**Example 9-7** *acitoolkit Exmaple*

```python
#! /usr/bin/env python
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
print('{0:19s}{1:14s}{2:10s}{3:8s}{4:17s}{5:10s}'.format(
    "MAC ADDRESS",
    "IP ADDRESS",
    "ENCAP",
    "TENANT",
    "APP PROFILE",
    "EPG"))
print('-'*80)

for EP in ENDPOINTS:
    epg = EP.get_parent()
    app_profile = epg.get_parent()
    tenant = app_profile.get_parent()
    print('{0:19s}{1:14s}{2:10s}{3:8s}{4:17s}{5:10s}'.format(
        EP.mac,
        EP.ip,
        EP.encap,
        tenant.name,
 
        app_profile.name,
        epg.name))
```

&nbsp;

The latest version of acitoolkit can be found at https://github.com/datacenter/acitoolkit.  Follow the steps at this link to install acitoolkit.  The acitoolkit library supports Python 3, and version 0.4 of the library is used in Example 9-7.  The script was tested successfully with Python 3.7.4.

&nbsp;

First, the acitoolkit library is imported; it will be referenced in the script using the short name **acl**.  Three variables are defined next: **APIC_URL** contains the URL for the APIC instance that will be queried (in this case, the Cisco DevNet always-on APIC sandbox), and **USERNAME** and **PASSWORD** contain the login credentials for the APIC instance.  Next, using the **Session** method takes as input the three variables defined previously: the **APIC_URL**, **USERNAME**, and **PASSWORD**.  Next, the success of the login action is verified.  If the response to the login action is not okay, a message is displayed to the console ("Could not login to APIC"), and the script execution ends.  If the login was successful was successful, all the endpoints in the ACI fabric instance are stored in the **ENDPOINTS** variable.  This is done by using the **get** method of the **aci.Endpoint** class and passing in the current session object.  Next, the headers of the table - with the information that will be extracted - are displayed to the console.  As mentioned previously, the MAC address, the IP address, the encapsulation, the tenant, the application profile, and the EPG will be retrieved from the APIC for all the endpoints in the fabric.  The **for** iterative loop will go over one endpoint at a time and, using the **get_parent()** method, will go one level up in the MIT and retrieve the parent MO of the endpoint, which is the EPG.  recall that all endpoints in the ACI fabric are organized in EPG.s  The parent object for an endpoint is hence the EPG of which that endpoint is a member.  Going one level up in the MIT, the parent object of the EPG is the application profile and going one more level up, the parent object of the application profile is the tenant object.  The **epg.app_profile**, and the **tenant** variables contain the respective EPG, application profile, and tenant values for each endpoint in the fabric.  The last line of code in the script displays to the console the required information for each endpoint.

&nbsp;

## UCS Manager

&nbsp;

Cisco ***Unified Computing System (UCS)*** encompasses most of the Cisco compute products.  The first UCS products were released in 2009, and they quickly established themselves as leaders in the data center compute and server market.  Cisco UCS provides a unified server solution that brings together compute, storage, and networking into one system.  While initially the UCS solution took advantage of network-attached storage (NAS) or storage area networks (SANs) in order to support requirements for large data stores, with the release of Cisco HyperFlex and hyperconverged servers, large storage data stores are now included with the UCS solution.

&nbsp;

Cisco UCS B-series blade servers, C-series rack servers, S-series storage servers, UCS Mini, and Cisco HyperFlex hyperconverged servers can all be managed through one interface: UCS Manager.  UCS Manager provides unified, embedded management of all software and hardware components of Cisco UCS.  Cisco UCS Manager software runs on a pair of hardware appliances called ***fabric interconnets***.  The two fabric interconnects from an active/standby cluster that provides high availability.  The UCS infrastructure that is being managed by UCS Manager forms a UCS fabric that can include up to 160 servers.  The system can scale to thousands of servers by integration individual UCS Manager instances with Cisco UCS Central in a multidomain Cisco UCS environment.

&nbsp;

>   ***`Key Topic`***

&nbsp;

UCS Manager participates in the complete server lifecycle, including server provisioning, device discovery, inventory, configuration, diagnostics, monitoring, fault detection, and auditing and statistics collection.  All infrastructure that is being managed by UCS Manager is either directly connected to the fabric interconnects or connected through fabric extenders.  Fabric extenders, as the name implies, have the function of offering additional scalability in connecting servers back to the fabric interconnects.  They are zero-management, low-cost, and low-power devices that eliminate the need for expensive top-of-rack Ethernet and Fibre Channel switches.

&nbsp;

All cisco UCS servers support Cisco SingleConnect technology.  Cisco SingleConnect is a revolutionary technology that supports all traffic from the servers (LAN, SAN, management, and so on) over a single physical link.  The savings that this technology brings only as part of the cabling simplification is orders of magnitude higher than competing products.

&nbsp;

Cisco UCS Manager provides an HTML 5 graphical user interface (GUI), a command-line interface (CLI), and a comprehensive API.  All Cisco UCS fabric functions and managed objects are available over the UCS API.  Developers can take advantage of the extensive API and can enhance the UCS platform according to their unique requirements.  Tools and software integrations with solutions from third-party vendors like VMware, Microsoft, and Splunk are already publicly available.  We will briefly see later in this chapter how the Cisco UCS PowerTool for UCS Manager and the Python software development kit (SDK) can be used to automate and programmatically manage Cisco UCS Manager.

&nbsp;

With Cisco UCS Manager, the data center servers can be managed using an infrastructure-as-code framework.  This is possible through another innovation that is included with the Cisco UCS solution: the service profile.  The service profile is a logical construct in UCS Manager that contains the complete configuration of a physical server.  All the elements of a server configuration - including RAID levels, BIOS settings, firmware revisions and settings, adapter settings, networking and storage settings, and data center connectivity - are included in the service profile.  When a service profile is associated with a server, Cisco UCS Manager automatically configures the server, adapters, fabric extenders, and fabric interconnects to match the configuration specified in the service profile.  With service profiles, infrastructure can be provisioned in minutes instead of days.  With service profiles, you can even pre-provision servers and have their configurations ready before the servers are even connected to the network.  Once the servers come online and get discovered by UCS Manager, the service profiles can be automatically deployed to the server.

&nbsp;

>   ***`Key Topic`***

&nbsp;

The UCS Manager programmatic interface is the XML API.  The Cisco UCS Manager XML API accepts XML documents over HTTP or HTTPS connections.  Much as with Cisco ACI, the configuration and state information for Cisco UCS is stored in a hierarchical tree structure known as the management information tree (MIT).  The MIT, which contains all the managed objects in the Cisco UCS system, is accessible through the XML API.  Any programming language can be used to generate XML documents that contain the API methods.  One or more managed objects can be changed with one API call.  When multiple objects are being configured, the API operation stops if any of the MOs cannot be configured, and a full rollback to the state of the system before the change was initiated is done.  API operations are transactional and are done on the single data model that represents the whole system.  Cisco UCS is responsible for all endpoint communications, making UCS Manager the single source of truth.  Users cannot communicate directly with the endpoints, relieving developers from administering isolated, individual component configurations.  All XML requests are asynchronous and terminate on the active Cisco UCS Manager.

&nbsp;

All the physical and logical components that make up Cisco UCS are represented in a hierarchical management information tree 9MIT), also known as the Management Information Model (MIM).  Each node in the tree represents a managed object (MO) or a group of objects that contain its administrative and operational states.  At the top of the hierarchical structure is the **sys** object, which contains all the parent and child nodes in the tree.  Each object in Cisco UCS has a unique distinguished name that describes the object and its place in the tree.  The information mode lis centrally stored and managed by a process running on the fabric interconnects that is called the ***Data Management Engine (DME)***.  When an administrative change is initiated to a Cisco UCS component, the DME first applies that change to the information mode and then applies the change to the actual management endpoint.  This approach is referred to as a ***model-drive framework***.

&nbsp;

A specific managed object in the MIT can be identified by its distinguished name (DN) or by its relative name (RN).  The DN specifies the exact managed object on which the API call is operating and consists of a series of relative names:

`DN = {RN}/{RN}/{RN}/{RN}...`

&nbsp;

A relative name identifies an object in the context of its parent object.

&nbsp;

The Cisco UCS Manager XML API model includes the following programmatic entities:

-   **Classes**:  Classes define the properties and state of objects in the MIT.
-   **Methods**:  Methods define the actions that the API performs on one or more objects.
-   **Types**:  Types are object properties that map values to the object state.

&nbsp;

Several types of methods are available with the XML API:

-   **Authentication methods**:  These methods, which include the following, are used to authenticate and maintain a session:
    -   **aaaLogin**:  Login method
    -   **aaaRefresh**:  Refreshes the authentication cookie
    -   **aaaLogin**:  Exits the session and deactivates the corresponding authentication cookie
-   **Query methods**:  These methods, which include the following, are used to obtain information on the current configuration state of an object:
    -   **configResolveDn**:  Retrieves objects by DN
    -   **configResolveClass**:  Retrieves objects of a given class.
    -   **configResolveParent**:  Retrieves the parent object of an object
-   **Configuration methods**:  These methods, which include the following, are used to make configuration changes to managed objects:
    -   **configConfMo**:  Affects a single MO
    -   **configConfMos**:  Affects multiple subtrees

&nbsp;

Since the query methods available with the XML API can return large sets of data, filters are supported to limit this output to subsets of information.  Four types of filters are available:

-   **Simple filters**:  These true/false filters limit the result set of objects with the Boolean value of True or False.
-   **Property filters**:  These filters use the values of an object's properties as the inclusion criteria in a result set (for example, equal filter, not equal filter, greater than filter)
-   **Composite filters**:  These filters are composed of two or more component filters (for example, AND filter, OR filter)
-   **Modifier filter**:  This filter changes the results of a contained filter.  Currently only the NOT filter is supported.  This filter negates the result of a contained filter.

&nbsp;

External applications can get cisco UCS Manager state change information either by regular polling or by event subscription.  Full event subscription is supported with the API and is the preferred method of notification.  Polling usually consumes a lot of resources and should be used only in limited situations.

&nbsp;

Cisco UCS Manager provides a managed object browser called Visore.  Visore can be accessed by navigating to `https://<UCS-Manager-IP>/visore.html`.

&nbsp;

The whole MIT tree can be explored, and also queries for specific DNs can be run from this interface.  Additional developer resources regarding Cisco UCS Manager can be found on the Cisco DevNet website, at https://developer.cisco.com/site/ucs-dev-center/.

&nbsp;

Next, let's explore the Cisco UCS Manager XML API.  The complete documentation of the Cisco UCS Manager information model for different releases can be found at https://developer.cisco.com/site/ucs-mim-ref-api-picker/.  At this site, you can find all the managed objects, all the methods, all the types, all the fault and FSM rules, and extensive documentation for each of them.

&nbsp;

>   ***`Key Topic`***

&nbsp;

In order for data center administrators and developers to become more familiar with the Cisco UCS system, Cisco has released a software emulator.  Cisco UCS Platform Emulator is the Cisco UCS Manager application bundled into a virtual machine (VM).  The VM includes software that emulates hardware communications for the Cisco UCS system.  The Cisco UCS Platform Emulator can be used to create and test a supported Cisco UCS configuration or to duplicate an existing Cisco UCS environment for troubleshooting and development purposes.  The Cisco UCS Platform Emulator is delivered as an .ova file and can run in nearly any virtual environment.  The complete cisco UCS Manager information model documentation is also bundled within the UCS Platform Emulator.

&nbsp;

As usual, the Cisco DevNet team makes available to the larger DevNet community a series of sandboxes for easier product discovery and development.  So far in this chapter we have used always-on sandboxes.  In this example, we will use a reservable sandbox.  As the name suggests, reservable sandboxes can be reserved up to 7 days and are available only to the person who makes the reservation.  At this writing, there is a Cisco UCS Manager sandbox that can be used to explore the XML API.  It is called **UCS Management** and can be found at https://develoepr.cisco.com/sandbox.  This sandbox takes advantage of the Cisco UCS Platform Emulator versions 3.2(2.5).

&nbsp;

At this point, to authenticate and get an authentication cookie, we can use the **curl** command as follows:

```
curl -k -X https://10.10.20.110/nuova \ 
    -H 'Content-Type: application/xlm' \
    -d '<aaaLogin inName="ucspe" inPassword="ucspe"></aaaLogin>'
```

&nbsp;

The IP address of the Cisco UCS Manager is **10.10.20.110**, the XML API resource is **/nuova**, and the authentication method used is **aaaLogin***.  The username and password are passed in an XML document within the **inName** and **inPassword** variables.  In this case, both the username and password are **ucspe**.  The **Content-Type** header specifies the type of data that the **POST** call will send to the XML API (which is, of course, **XML** in this case).

&nbsp;

The response should be similar to the following one:

&nbsp;

```
<aaaLogin cookie="" response="yes" outCookie="1573019916/7c901636-
c461-487e-bbd0-c74cd68c27be" outRefreshPeriod="600"
outPriv="aaa,admin,ext-lan-config,ext-lan-policy,ext-lan-
qos,ext-lan-security,ext-san-config,ext-san-policy,ext-san-
security,fault,operations,pod-config,pod-policy,pod-qos,pod-
security,read-only" outDomains="org-root" outChannel="noencssl"
outEvtChannel="noencssl" outSessionId="" outVersion="3.2(2.5)"
outName="" />
```

&nbsp;

**aaaLogin** specifies the method used to log in, the **"yes"** value confirmed that this is a response, **outCookie** provides the session cookie, **outRefreshPeriod** specifies the recommended cookie refreshed period (where the default is 600 seconds), and the **outPriv** value specifies the privilege level associated with the account.

&nbsp;

Next, let's get a list of all the objects that are part of the compute class and are being managed by this instance of Cisco UCS Manager.  In order to accomplish this, we can use the **configFindDnsByClassId** method.  This method finds distinguished names and returns them sorted by class ID.  The **curl** command should look similar to the following one:

&nbsp;

```
curl -k -X POST https://10.10.20.110/nuova \
  -H 'Content-Type: application/xml' \
  -d '<configFindDnsByClassId
    classId="computeItem"
    cookie="1573019916/7c901636-c461-487e-bbd0-c74cd68c27be" />'
```

&nbsp;

The XML API endpoint, `https://10.10.20.110/nuova`, and the **Content-Type** header, **application/xml**, stay the same.  The XML data that is being sent to the Cisco UCS Manager server is different.  First, the **configFindDnsByClassId** method is specified, and then the two mandatory variables for **classId** and the **cookie** are passed in.  The **classId** specifies the object class that in this case is the **computeItem** class, and the **cookie** is being populated with the value of the authentication cookie obtained previously.

&nbsp;

The response in this case, as shown in Example 9-8, contains a complete list of all the compute items that area being managed by the 10.10.20.11 instance of Cisco UCS Manager.

&nbsp;

**Example 9-8** *List of Compute Items That Are Being Managed by Cisco UCS Manager*

```
<configFindDnsByClassId cookie="1573019916/7c901636-c461-487e-bbd0-c74cd68c27be"
response="yes" classId="computeItem">
         <outDns>
                 <dn value="sys/chassis-4/blade-8"/>
                 <dn value="sys/chassis-5/blade-8"/>
                 <dn value="sys/chassis-6/blade-8"/>
                 <dn value="sys/chassis-6/blade-1"/>
                 <dn value="sys/chassis-3/blade-1"/>
                 ... omitted output
                 <dn value="sys/rack-unit-9"/>
                 <dn value="sys/rack-unit-8"/>
                 <dn value="sys/rack-unit-7"/>
                 <dn value="sys/rack-unit-6"/>
                 <dn value="sys/rack-unit-5"/>
                 <dn value="sys/rack-unit-4"/>
                 <dn value="sys/rack-unit-3"/>
                 <dn value="sys/rack-unit-2"/>
                 <dn value="sys/rack-unit-1"/>
         </outDns>
</configFindDnsByClassId>
```

&nbsp;

In our exploration of the Cisco UCS Manager XML API, let's now get more information about a specific compute object.  The method to retrieve a single managed object for a specified DN is **configResolveDn**.  The **curl** command for this API request should look as shown in Example 9-9.

&nbsp;

**Example 9-9** *Using a **curl** Command to Retrieve Information About a Compute Object*

```
curl -k -X POST https://10.10.20.110/nuova \
  -H 'Content-Type: application/xml' \
  -d '<configResolveDn
    cookie="1573019916/7c901636-c461-487e-bbd0-c74cd68c27be"
    dn="sys/chassis-4/blade-8" />'
```

&nbsp;

Much as in the previous call, the API endpoint and **Content-Type** header stay the same.  The XML data that is being sent with the request contains the method, **configResolveDn**, the authentication cookie, and the DN for which additional information is requested, which in this case is the blade number 8 in chassis number 4: **sys/chassis-4/blade-8**.

&nbsp;

The response contains extensive information about the blade server in slot 8 from the chassis with number 4, as as shown in Example 9-10.  

&nbsp;

**Example 9-10** ***curl** Command Response Containing Information About a Compute Object*

```
<configResolveDn dn="sys/chassis-4/blade-8" cookie="1573019916/7c901636-c461-487e-bbd0-
c74cd68c27be" response="yes">
         <outConfig>
                 <computeBlade adminPower="policy" adminState="in-service" assetTag=""
                 assignedToDn=""
                 association="none" availability="available" availableMemory="49152"
                 chassisId="4"
                 checkPoint="discovered" connPath="A,B" connStatus="A,B" descr=""
                 discovery="complete"
                 discoveryStatus="" dn="sys/chassis-4/blade-8" fltAggr="0" fsmDescr=""
                 fsmFlags=""
                 fsmPrev="DiscoverSuccess" fsmProgr="100" fsmRmtInvErrCode="none"
                 fsmRmtInvErrDescr=""
                 fsmRmtInvRslt="" fsmStageDescr="" fsmStamp="2019-11-06T04:02:03.896"
                 fsmStatus="nop"
                 fsmTry="0" intId="64508" kmipFault="no" kmipFaultDescription=""
                 lc="undiscovered"
                 lcTs="1970-01-01T00:00:00.000" localId="" lowVoltageMemory="not-applicable"
                 managingInst="A" memorySpeed="not-applicable" mfgTime="not-applicable"
                 model="UCSB-
                 B200-M4" name="" numOf40GAdaptorsWithOldFw="0"
                 numOf40GAdaptorsWithUnknownFw="0"
                 numOfAdaptors="1" numOfCores="8" numOfCoresEnabled="8" numOfCpus="2"
                 numOfEthHostIfs="0" numOfFcHostIfs="0" numOfThreads="16" operPower="off"
                 operPwrTransSrc="unknown" operQualifier="" operSolutionStackType="none"
                 operState="unassociated" operability="operable"
                 originalUuid="1b4e28ba-2fa1-11d2-
                 0408-b9a761bde3fb" partNumber="" policyLevel="0" policyOwner="local"
                 presence="equipped" revision="0" scaledMode="none" serial="SRV137"
                 serverId="4/8"
                 slotId="8" totalMemory="49152" usrLbl=""
                 uuid="1b4e28ba-2fa1-11d2-0408-b9a761bde3fb"
                 vendor="Cisco Systems Inc" vid=""/>
           </outConfig>
</configResolveDn>
```

&nbsp;

While interacting with the Cisco UCS Manager XML API this way is possible, you can see that it becomes cumbersome very quickly.  the preferred way of working with the XML API is either through Cisco UCS PowerTool suite or the Cisco UCS Python SDK.

&nbsp;

The Cisco UCS PowerTool suite is a PowerShell module that helps automate all aspects of Cisco UCS Manager.  The PowerTool cmdlets work on the Cisco UCS MIT.  The cmdlets can be used to execute read, create, modify, and delete operations on all the managed objects in the MIT.  The Cisco UCS PowerTool suite enables easy integration with existing IT management processes and tools.  The PowerTool suite can be downloaded for Windows via PS Gallery and for Linux from https://community.cisco.com/t5/cisco-developed-ucs-integrations/cisco-ucs-powertool-core-suite-for-powershell-core-modules-for/ta-p/3985798.

&nbsp;

Cisco UCS Python sDK is a Python module that helps automate all aspects of Cisco UCS management, including server, network, storage, and hypervisor management.  The Cisco UCS Python SDK works on the Cisco UCS Manager MIT, performing create, read, modify, or delete actions on the managed objects in the tree.  Python versions 2.7 and higher and version 3.5 and higher are supported.  The Cisco UCS Python module for UCS Manager is called **ucsmsdk** and can be installed using pip by issuing the following command at the command prompt: **pip install ucsmsdk**.  As of this writing, the current version of the ucsmsdk module is 0.9.8.

&nbsp;

The Cisco UCS Python SDK provides a utility called convert_to_ucs_python that gives administrators and developers the option of recording all the interactions with the Cisco UCS Manager GUI and saving them into an XML file.  Running this XML file through the convert_to_ucs_python tool automatically generates Python code corresponding to the actions that were performed in the GUI.  Using this process, data center automation efforts can be sped up orders of magnitude, and simple tasks such as creating a new VLAN or complex tasks such as configuring a service policy template can be automated within seconds.

&nbsp;

Next, let's explore the Cisco UCS Python SDK and see how to connect to a Cisco UCS Manager instance, retrieve a list of all the compute blades in the system, and extract specific information from the returned data.  The sample Python code is built in Python 3.7.4 using version 0.9.8 of the ucsmsdk module.

&nbsp;

First, the **UseHandle** class is imported.  An instance of this class is used to connect to Cisco UCS Manager.  The Cisco UCS Manager IP address, username, and password are passed in as parameters to the instance of the UseHandle class that is called **HANDLE**.  Several methods aer available with the UseHandle class.  In this script only three are used:

-   **HANDLE.login()**:  This method is used to log in to Cisco UCS Manager.
-   **HANDLE.query_classid()**:  This method is used to query the MIT for objects with a specific class ID.
-   **HANDLE.logout()**:  This method is used to log out from the Cisco UCS MAnager.


The BLADES variable contains a dictionary of all the compute blades that are being managed by the 10.10.20.11 instance of Cisco UCS Manager.  Within a **for** loop, specific information regarding the DN, serial number, administrative state, model number, and total amount of memory for each blade is extracted and displayed to the console.  The Python script using the Cisco UCS Manager SDK that accomplishes all of these tasks looks as shown in Example 9-11.

&nbsp;

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
        BLADE.total_memory))

HANDLE.logout()
```

&nbsp;

## Cisco UCS Director

&nbsp;

Automation delivers the essential scale, speed, and repeatable accuracy needed to increase productivity and respond quickly to business requirements in a data center environment.  Cisco UCS Director replaces manual configuration and provisioning processes with orchestration in order to optimize and simplify delivery of data center resources.

&nbsp;

This open private-cloud platform delivers on-premises infrastructure as a service (IaaS) from the core to the edge of the data center.  Automated workflows configure, deploy, and manage infrastructure resources across Cisco and third-party computing, network, and storage resources and converged and hyperconverged infrastructure solutions.  Cisco UCS Director supports the industry's leading converged infrastructure solutions, including NetApp FlexPod and FlexPod Express, EMC VSPEX, EMC VPLEX, and VCE Block.  It delivers unified management and orchestration for a variety of hypervisors across bare-metal and virtualized environments.

&nbsp;

A self-service portal, a modern service catalog, and more than 2500 multivendor tasks enable on-demand access to integrated service across data center resources.  Cisco UCS Director allows IT professionals and development teams to order and manage infrastructure services on demand.

&nbsp;

Cisco UCS Director is supported by a broad ecosystem.  Third-party hardware and solution vendors can use the southbound APIs and the SDKs provided with them to develop integrations into the Cisco UCS Director management model.  Northbound APIs can be used by DevOps and IT operations management tools to interact with Cisco UCS Director and perform all the functions provided by the solution in a programable and automated fashion.

&nbsp;

>   ***`Key Topic`***

&nbsp;

Cisco UCS Director provides comprehensive visibility and management of data center infrastructure components.  From a data center management perspective, the following are some of the tasks that can be performed using Cisco UCS Director:

-   Create, clone, and deploy service profiles and templates for all Cisco UCS servers and compute applications.
-   Manage, monitor, and report on data center components such as Cisco UCS domains or Cisco Nexus devices.
-   Monitor usage, trends, and capacity across a converged infrastructure on a continuous basis.
-   Deploy and add capacity to converged infrastructures in a consistent, repeatable manner.

&nbsp;

Cisco UCS Director also enables the creation of workflows that provide automation services.  These automation workflows can be published and made available to the end users of the data center resources through on-demand portals.  Once built and validated, these workflows perform the same way every time, no matter who triggers them.  A data center administrator can run them, or role-based access control can be implemented to enable users and customers to run these workflows on a self-service basis.  From an infrastructure automation perspective, some of the user cases that Cisco UCS Director can help automate include the following:

-   Virtual machine provisioning and lifecycle management.
-   Compute, network, and storage resources configuration and lifecycle management.
-   Bare-metal server provisioning, including operating system installation.

&nbsp;

Cisco UCS Director supports Cisco ACI by offering automation workflows that orchestrate the APIC configuration and management tasks.  It also supports multitenancy and the ability to define contracts between different container tiers.

&nbsp;

Cisco UCS Director can be managed using Cisco Intersight, which is covered later in this chapter.  Cisco UCS Director is a 64-bit appliance that uses the standard templates Open Virtualization Format (OVF) for VMware vSphere and Virtual Hard Disk (VHD) for Microsoft Hyper-V and can be downloaded from www.cisco.com.

&nbsp;

>   ***`Key Topic`***

&nbsp;

Next, let's go over some essential concepts needed to understand how the Cisco UCS Director orchestrator works.  First, there is the concept of a task.  A ***task*** is an atomic unit of work in Cisco UCS Director; it cannot be decomposed into smaller actions and represents a single action with inputs and outputs.  Cisco UCS Director has a task library that contains hundreds of predefined tasks, such as an SSH command task (executing a command in a Secure Shell session), an inventory collection task (gathering information about available devices), a new VM provisioning task (creating a new virtual machine), and many more.  In the event that there is no suitable predefined task, the system offers the option of creating custom tasks, as described later in this section.

&nbsp;

The second concept is the workflow.  A ***workflow*** is a series of tasks arranged to automate a complex operation.  The simplest workflow contains a single task, but workflows can contain any number of tasks.  Workflows are at the heart of Cisco UCS Director orchestration.  They automate processes of any level of complexity.  Workflows are built using the Workflow Designer, which is a drag-and-drop interface.  In Workflow Designer, the tasks are arranged in sequence and define inputs and outputs to those tasks.  Loops and conditionals can be implemented using flow of control tasks.  Every time a workflow is executed, a service requested is generated.  Workflows can be scheduled for later execution, and Cisco UCS Director stores details of completed service requests.  A service request can have one of several states, depending on its execution status: scheduled, running, blocked, completed, or failed.

&nbsp;

Finally, libraries and catalogs are collections of predefined tasks and workflows that can be used as building blocks for more advanced workflows.

&nbsp;

>   ***`Key Topic`***

&nbsp;

Let's now explore the programmability and extensibility of Cisco UCS Director.  The Cisco UCS Director SDK is a collection of technologies that enable developers to expend the capabilities of Cisco UCS Director, access Cisco UCS Director data, and invoke Cisco UCS Director's automation and orchestration operations from any application.  The Cisco UCS Director SDK includes the Open Automation component.  Scripting technologies include the Cisco UCS Director PowerShell API, custom tasks bundled in Cisco UCS Director script modules, and the ability to write custom tasks using CloupiaScript, a server-side JavaScript implementation.

&nbsp;

The cisco UCS Director SDK makes the following possible:

-   Accessing Cisco UCS Director programmatically by using the Cisco UCS Director REST API
-   Customizing Cisco UCS Director by creating custom workflow tasks
-   Extending Cisco UCS Director by using Cisco UCS Director Open Automation to build connectors that support additional devices and systems

&nbsp;

Cisco UCS Director provides the Cisco UCS Director Open Automation module to enable developers to enhance the functionality of the Cisco UCS Director appliance.  Open Automation can be used to add modules to Cisco UCS Director.  A module is the topmost logical entry point into Cisco UCS Director.  In order to add or extend the functionality of the system, a new module must be developed and deployed on Cisco UCS Director.  A module developed using Open Automation behave the same way as any Cisco UCS Director built-in feature or module.  Open Automation is a Java SDK and framework that contains all the resources needed to develop new modules.  Some of the use cases for Open Automation are the following:

-   Adding the ability to control a new type of device with Cisco UCS Director
-   Designing custom menus for displaying new devices or components
-   Taking inventory of new devices
-   Developing custom Cisco UCS Director reports and report actions
-   Developing tasks that can be used in workflows

&nbsp;

Custom tasks enable developers to perform customized operations on Cisco UCS Director resources.  Custom tasks are written using CloupiaScript, a language similar to JavaScript.  Custom tasks can be used like any other task, including in workflows that orchestrate how the system works.  Script bundles are collections of custom tasks that are included with each Cisco UCS Director release and are used for a variety of specific applications.  Script bundles can be downloaded, and the custom tasks that are contained in a bundle can be imported into Cisco UCS Director.  The main goal with custom tasks is to expand the range of tasks that is available for use in orchestration workflows.

&nbsp;

Script modules are used to integrate third-party JARs (Java Archives) and custom libraries with Cisco UCS Director to add custom functionality to the Cisco UCS Director user interface.  Some script module operations are already defined in Cisco UCS Director, such as creating advanced controls to collect user input in workflows and context workflow mapping, which enables an administrator to attach workflows to custom actions in a report in Cisco UCS Director.  Script modules can be exported and reused in different instances of Cisco UCS Director.  Script modules, although named similarly to script bundles, have in fact a very different role.  Script bundles, as we've seen previously, are packaged collections of workflow tasks that are released with Cisco UCS Director.  Script modules, on the other hand, make it possible to add custom functionality to Cisco UCS Director.

&nbsp;

Cisco UCS Director PowerShell console is a Cisco-developed application that provides a PowerShell interface to the Cisco UCS Director REST API.  The console provides a set of PowerShell cmdlets wrapped in a module to internally invoke the REST APIs over HTTP.  Each cmdlet performs a single operations.  Cmdlets can be chained together to accomplish more advanced automation and data center management tasks.  Figure 9-12 shows the relationship between the PowerShell console, Cisco UCS Director, and the infrastructure that is being managed by it.

&nbsp;

Figure 9-12 Cisco UCS Director PowerShell Console

>  Cisco UCS Director Powershell Console:  On the left there is a box with two checkmarks.  Checkmark one is "Contains Cmdlets Wrapped in a Module" and checkmark two is "Used for Communicating with Cisco UCSD to Manage Various Operations".  This box has an arrow staying "Northbound PowerShell Script" pointing towards the Cisco UCS Director, which projects a light stating "Orchestration and Lifecycle Management" on top as well as "Policy-Driven Provisioning" beneath.  This light shines on four boxes, going from top to bottom they are "VMs", "Compute", "Network", and "Storage".

&nbsp;

Cisco UCS Director offers a REST API that enables applications to consume or manipulate the data stored in Cisco UCS Director.  Applications use HTTP or HTTPS requests from the REST API to perform Create/Read/Update/Delete (CRUD) operations on Cisco UCS Director resources.  With an API call, a developer can execute Cisco UCS Director workflows and change the configuration of switches, adapters, policies, and any other hardware and software components.  The API accepts and returns HTTP messages that contain JavaScript Object Notation (JSON) or Extensible Markup Language (XML) documents.

&nbsp;

>   ***`Key Topic`***

&nbsp;

To access the Cisco UCS Director REST API, a valid user account and an API access key are needed.  Cisco UCS Director uses the API access key to authenticate an API request.  The access key is a unique security access code that is associated with a specific Cisco UCS Director user account.  In order to retrieve the API access key for a specific user, you first log in to Cisco UCS Director with that specific user account.  Then hover the mouse over the user icon in the top-right corner and select Edit My Profile from the drop-down list.  On the Edit My Profile page, select Show Advanced Settings and retrieve the API access key from the REST API Access Key area.  There is also an option to regenerate the access key, if necessary.

&nbsp;

Within the user advanced settings is an option to enable the developer menu.  By enabling the developer enu, access to the REST API browser and the Report Metadata features is turned on.  The REST API browser becomes visible under the Orchestration tab of Cisco UCS Director and provides API information and API code generation capabilities for all available APIs.  The Report Metadata option becomes available on all the pages of the Cisco UCS Director GUI; when selected, it returns the API code that the GUI is using to retrieve the information that is displayed to the user in that specific page.  This code includes a complete URL that is ready tot paste into a browser to send the request to Cisco UCS Director.  Both the REST API browser and the Report Metadata features are extremely valuable to developers as they provide ready-to-use sample code and API calls to all the resources available in Cisco UCS Director.

&nbsp;

>   ***`Key Topic`***

&nbsp;

Each REST API request must be associated with an HTTP header called **X-Cloupia-Request-Key**, with its value set to the REST API access key retrieved previously.  The REST API request must contain a valid URL of the following format: `https://Cisco_UCS_Director/app/api/rest?formatType=json&opName=operationName&opData=operationData` where

-   **Cisco_UCS_Director**:  This is the IP address or hostname of the Cisco UCS Director VM.
-   **formatType**:  This can be either JSON or XML; it is JSON in this case.  (Only JSON is discussed throughout the rest of this chapter.)
-   **opName**:  This is the API operation name that is associated with the request (for example, userAPIGetMyLoginProfile), as explored later in this chapter.
-   **opData**:  This contains the parameters or the arguments associated with the operation.  cisco UCS Director uses JSON encoding for the parameters.  If an operation doesn't require any parameters, the empty set {} should be used.  When building the URL, escape characters should be encoded as appropriate.

&nbsp;

Next, let's explore the Cisco UCS Director REST API by using **curl** to construct API calls.  Programming guides and complete documentation of the Cisco UCS REST API can be found at the following link:  https://www.cisco.com/c/en/us/support/servers-unified-computer/ucs/director/products-programming-reference-guides-list.html.  The Cisco DevNet team makes available a reservable sandbox called "UCS Management" for learning purposes.  This sandbox contains an installation of Cisco UCS Director and is available at https://developer.cisco.com/sandbox.  Cisco UCS Director version 6.7 has been used in the following interactions with the REST API.  The operation with the name **userAPIGetMyLoginProfile** is used to retrieve the profile of the user with the specific access key that is passed in the request in order to identify the group to which the user belongs.  The **curl** command for this operation looks as shown in Example 9-12.

&nbsp;

**Example 9-12** ***curl** Command to Retrieve the User Profile in Cisco UCS Director*

```
curl -k -L -X GET \
  -g 'https://10.10.10.66/app/api/rest?formatType=json&opName=userAPIGetMyLoginProfi
  le&opData={}' \
  -H 'X-Cloupia-Request-Key: 8187C34017C3479089C66678F32775FE'
```

&nbsp;

For this request, the **-g** parameter disables the **curl** check for nested braces **{}**, the **-k** or **-insecure** parameter allows **curl** to proceed nad operate even if the server uses self-signed SSL certificates, and the **-L** parameter allows **curl** to follow the redirects sent by the server.  The URL for the request follows the requirements discussed previously ,using the **/app/api/rest** endpoint to access the REST API and then passing the **formatType**, **opName**, and **opData** as parameters.  The HTTP header for authentication is named **X-Cloupia-Request-Key** and contains the value of the access key for the admin user for the Cisco UCS Director instance that runs on the server with IP address **10.10.10.66**.  The response from the instance of Cisco UCS Director looks as shown in Example 9-13. 

&nbsp;

The operation name is contained in the response and is indeed **userAPIGetMyLoginProfile**, **serviceName** specifies the name of the back-end service (which is in most cases **InfraMgr**), **serviceResult** contains a set of name/value pairs or a JSON object if the request was successful, and **serviceError** contains the error message.  If the request succeeds, the **serviceError** value is set to null, and if the operation fails, **serviceError** contains the error message.

&nbsp;

**Example 9-13** *REST API Response Containing User Profile Information*

```
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
   "serviceError" : null}
```

&nbsp;

As mentioned previously, Cisco UCS Director tasks and workflows can have any number of input and output variables.  In order to retrieve the inputs for a specific workflow, the **userAPIGetWorkflowInputs** operation can be used with the name of the desired workflow in the **param0** field.  Cisco UCS Director comes by default with a large number of predefined workflows.  One of them is the "VMware OVF Deployment," which, as the name implies, can deploy new VMware virtual machines based on OVF images.  The **curl** command in Example 9-14 contains the API call to retrieve all the inputs for this workflow.

&nbsp;

**Example 9-14** ***curl** Command to Retrieve Workflow Inputs in Cisco UCS Director*

```
curl -k -L -X GET \
  -g 'http://10.10.10.66/app/api/rest?formatType=json&opName=userAPIGetWorkflowInput
  s&opData={param0:%22VMware%20OVF%20Deployment%22}' \
  -H 'X-Cloupia-Request-Key: 8187C34017C3479089C66678F32775FE'
```

&nbsp;

Notice that the name of the workflow is passed in the API call in the **param0** parameter and also that VMware OVF Deployment is encoded, using single quotation marks and spaces between the word.  Example 9-15 shows a snippet of the response.

&nbsp;

The response contains similar fields to the response in Example 9-14.  **opName** is confirmed as **userAPIGetWorkflowInputs**, the back-end service that responded to the request is once again **InfraMgr**, **serviceError** is **null** (indicating that there were no errors in processing the request), and **serviceResult** contains a list called **details**, which includes all the inputs and their properties for **VMware OVF Deployment** workflow.

&nbsp;

**Example 9-15** ***curl** Command Response Containing Workflow Inputs in Cisco UCS Directory*

```
{
   "serviceResult" : {
      "details" : [
         {
            "inputFieldValidator" : "VdcValidator",
            "label" : "vDC",
            "type" : "vDC",
            "inputFieldType" : "embedded-lov",
            "catalogType" : null,
            "isOptional" : false,
            "name" : "input_0_vDC728",
            "isMultiSelect" : false,
            "description" : "",
            "isAdminInput" : false
         },
         {
            "isAdminInput" : false,
            "description" : "",
            "label" : "OVF URL",
            "type" : "gen_text_input",
            "isMultiSelect" : false,
            "isOptional" : false,
            "inputFieldType" : "text",
            "catalogType" : null,
            "name" : "input_1_OVF_URL465",
            "inputFieldValidator" : null
         },
         ...omitted output
      ]
   },
   "serviceName" : "InfraMgr",
   "opName" : "userAPIGetWorkflowInputs",
   "serviceError" : null}
```

&nbsp;

## Cisco Intersight

&nbsp;

The Cisco Intersight platform provides intelligent cloud-powered infrastructure management for Cisco UCS and Cisco HyperFlex platforms.  Cisco UCS and Cisco HyperFlex use model-based management to provision servers and the associated storage and networking automatically.  Cisco Intersight works with Cisco UCS Manager and Cisco Integrated Management Controller (IMC) to bring the model-based management of Cisco compute solutions into one unified management solution.  Cisco Intersight offers flexible deployment options either as software as a service (SaaS) on https://intersight.com or running a Cisco Intersight virtual appliance on premises.  Some of the benefits of using Cisco Intersight are the following:

-   It simplifies Cisco UCS and Cisco HyperFlex management with a single management platform.
-   It makes it possible to scale across data center and remote locations without additional complexity.
-   It automates the generation and forwarding of technical support files to the Cisco Technical Assistance CEnter to accelerate the troubleshooting process.
-   Full programmability and automation capabilities are available through a REST API interface.
-   A streamlined upgrade process is available for standalone Cisco UCS servers.

&nbsp;

Getting started with Cisco Intersight involves the following steps:

-   **Step 1**.  Log in to https://intersight.com with a Cisco ID account.
-   **Step 2**.  Claim a device for the account.  Endpoint devices connect to the Cisco Intersight portal through a device connector that is embedded in the management controller of each system.
-   **Step 3**.  (Optional)  Add additional users to the new account.  Several roles are available, including read-only and admin roles.  Custom roles can be created, if needed.

&nbsp;

>   ***`Key Topic`***

&nbsp;

Cisco Intersight includes a REST API interface built on top of the OpenAPI specification.  The API documentation, API schemas, and SDKs can be found at https://intersight.com/apidocs.  At this writing, Python and PowerShell SDKs are available for download at the previous link.  The API accepts and returns messages that are encapsulated in JSON documents and are sent over HTTPS.  The Intersight API is a programmatic interface to the Management Information Model that is similar to Cisco ACI and Cisco UCS Manager.  Just like Cisco ACI and Cisco UCS Manager MIMs, the Cisco Intersight MIM is composed of managed objects.  Managed objects or REST API resources are uniquely identified by URI (uniform resource identifier) or, as seen earlier in this chapter, distinguished name (DN).  Example of managed objects include cisco UCS servers; Cisco UCS fabric interconnects; Cisco HyperFlex nodes and clusters; server, network, and storage policies; alarms; statistics; users; and roles.  Cisco Intersight managed objects are represented using a class hierarchy specified in the OpenAPI specification.  All the API resources are descendent of the **mo.MO** class.  Table 9-2 shows the properties that are common to all managed objects.

&nbsp;

**Table 9-2** Common Properties for All Managed Objects in Cisco Intersight

| Property Name | Description |
| -- | -- |
| **Moid** | A unique identifier of the managed object instance. |
| **ObjectType** | The fully qualified class name of the managed object. |
| **AccountMoid** | The Intersight account ID for the managed object. |
| **CreateTime** | The time when the managedo bject was created. |
| **ModTime** | The time when the managed object was last modified.  **ModTime** is autmatically updated whenever at least one property of the managed object is modified. |
| **Owners** | An array of owners, which represents effective ownership of the object. |
| **Tags** | An array of tags that allow the addition of key/value metadata to managed objets. |
| **Ancestors** | An array containing the MO references of the ancestors in the object containment hierarhcy. |
| **Parent** | The direct ancestor of the managed object in the containment hierarchy. |

&nbsp;

Every managed object has a unique **Moid** identifier assigned when the resource is created.  The **Moid** is used to uniquely distinguish a Cisco Intersight resource from all other resources.  The **Moid** is a 12-byte string set when a resource is created.

&nbsp;

Each managed object can be addressed using a unique uniform resource identifier (URI) that includes the **Moid**.  The URI can be used in any HTTPs request to address the managed object.  A generic Cisco Intersight URI is of the following form:

`https://intersight.com/path[?query]`

&nbsp;

The URI of a managed object includes the following:

-   **https**:  The HTTPS protocol
-   **intersight.com**:  The Cisco Intersight hostname
-   *path*:  The path, organized in hierarchical form
-   *query*:  An optional query after the question mark and typically used to limit the output of the response to only specific parameters

&nbsp;

For example, the URI of an object with **Moid** **48601f85ae74b80001aee589** could be:

`https://intersight.com/api/v1/asset/DeviceRegistrations/48601f85ae74b80001aee589`

&nbsp;

Every managed object in the Cisco Intersight information model supports tagging.  Tagging is used to categorize objects by a certain common property, such as owner, geographic location, or environment.  Tags can be set and queried through the Intersight API.  Each tag consists of a key and an optional value.  Both the key and the value are of type string.

&nbsp;

MAnaged objects may include object relationships, where dynamic links to REST resources.  Cisco Itnersight uses Hypermedia as the Engine of Application State (HATEOAS) conventions to represent objection relationships.  Object relaitonships can be links to self or links to other managedo bjects, which, taken as a whole, form a graph of objects.  By using relationships as a first-class attribute in the object model, many classes of graphs can be represented, including trees and cyclic or bipartite grpahs.

&nbsp;

Intersight provides a rich query language based on the OData standard.  The query language is represented using URL query parameters for **GET** results.  Several types of data are supported with Intergsight queries, including string, number, duraiton, date and time, and time of day.

&nbsp;

>   ***`Key Topic`***

&nbsp;

When a client sends an API request , the Intersight web service must identify and authenticate the client.  The intersight web service supports two authentication methods:

-   API keys
-   Session cookies

&nbsp;

An Intersight API key is composed of a keyId and a keySecret.  The API client uses the API key to cryptographically sign each HTTP request sent to the Intersight web service.  The "**signature**" parameter is a base 64-encoded digital signature of the message HTTP headers and mssage content.  API keys are generated in the Settings > API section of the Intersight web interface.  As a best practice, it is recommended to generate separate API keys for each client application that needs access to the API.  

&nbsp;

Cookies are used primarily by the Intersight UGI client running in a browser.  When accessing the Intersight web service, end users must first authenticate to https://sso.cisco.com.  When authentication is successful, sso.cisco.com sends a signed SAML assertion to thte Intersight web service, and Itnersighte generates a session cookie with limited time span validity.  The client must send the session cookie in each API request.

&nbsp;

>   ***`Key Topic`***

&nbsp;

Included with the Cisco Intersight REST API documentation at https://intersight.com/apidocs are the API reference documentation and an embedded REST API client.  Figure 9-14 shows the web interface for the Cisco Intersight API reference documentation.  In this figure, the **Get a list of 'equipmentDeviceSummary' instances** API call is selected.  The query parametrs that this specific API call supports are displayed, as are the API URI for the endpoint that will return the list of all the devices that are being managed by Cisco Intersight for this specific account.  Much as wit Postman, if the Send button is clicked, the API call is triggered, and the response is displayed in the Response Text window.

&nbsp;

**Figure 9-14** *Cisco Intersight REST API Reference Documentation*

>   Not much of note, although it is a key topic so I suggest going to the API docs and seeing how it will generate code for you.

&nbsp;

Under the Downloads section of https://intersight.com/apidocs, the Cisco Intersight Python and PowerShell SDKs can be downloaded.  The Python SDK covers all the functionality of the REST API and offers Python classes and methods that can be used to simpify Cisco Intersight automation projects.  The Python sample code in Example 9-16 was developed using the Intersight module version 1.0 and ython 3.7.4.  This Python code replicates the earlier REST API call **equipmentDeviceSummary**, which returns a list of all the devices that are being managed by Cisco Intersight for a specific account.  

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
    api_key_id="your_own_api_key_id")

# Create an equipment device handle
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
        DEVICE.source_object_type))
```

&nbsp;

The first two lines of Example 9-16 use the **import** keyword to bring in and make available for later consumptions the **IntersightApiClient** Python class that will be used to create a connection to the Cisco Intersight platform and the **equipment_device_summary_api** file, which contains Python objects that are useful for retrieving equipment that is being managed by Intersight.  Every cisco Intersight REST API endpoint has a corersponding Python file containing classes and methods that can be used to programmatically process those REST API endpoints.  Next, an instance of the **IntersightApiClient** class is created in order to establish a connection and have a hook back to the Cisco Intersight platform.  Three parameters need to be passed in to instantiate the class:

-   **host**:  This parameter specifies the Cisco REST API base URL.
-   **private_key**:  This parameter specifies the path to the file that contains the keySecret of the Intersight account that will be used to sign in.
-   **api_key_id**:  This parameter contains the keyId of the same Intersight account.  As mentioned previously, both the keyId and keySecret are generated in the Intersight web interface, under Settings > API keys.

&nbsp;

Next, an instance of the **EquipmentDeviceSummaryApi** class is created and stored in the **D_HANDLE** variable.  This Python class maps into the **/api/v1/equipment/DeviceSummaries** REST APi resource.  The **D_HANDLE** variable contains the handle to that REST API resource.  The **equipment_device_summaries_get** method that is available with the **EquipmentDeviceSummaryApi** class is invoked next, and the results are stored in the **DEVICES** variable, which contains a complete list of all the equipment that is being managed by Cisco Intersight for the user account with the keyId and keySecret with which the initial connection was established.  The **for** loop iterates over the devices in the list and extracts for each one of the distinguished name, model, serial number, and object type and displays this information to the console.