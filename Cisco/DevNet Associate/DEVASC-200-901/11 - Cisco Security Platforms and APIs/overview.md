#   Cisco's Security Portfolio

Cisco's security portfolio focuses on three areas:

-   ***Visibility***:  The ability to "see" everything that is happening in the network.
-   ***Segmentation***:  The ability of the network to reduce the surface attack to contain the spread.
-   ***Protection***:  The ability to stop any breaches from happening.

&nbsp;

##  **Potential Threats and Vulnerabilities**

&nbsp;

Anything we are trying to protect again - person or code - is known as a ***threat***.

A ***vulnerability*** is a weakness or gap in protection efforts.

&nbsp;

##  **Most Common Threats**

&nbsp;

**Table 11-2** Common threads

| Threat | Description |
| -- | -- |
| Man-in-the-middle attack | Attackers insert themselves between two endpoints (such as a browser and a web server) and intercept or modify communications between the two.  The attackers can then collect information as well as impersonate either of the two agents.  In addition to websites, these attackers can target email communications, DNS lookups, and public Wi-Fi networks. |
| Denial-of-service (Dos) attack | An attacker sends multiple requests that flood the server on networks with traffic to exhaust resources and bandwidth.  As the system continues with degraded performance, the system becomes more and more nonresponsive, and real requests are left unfulfilled.  A DooS attack can be coordinated so that multiple devices launch the attack at the same time.  This is known as a distributed denial of service (DDoS) attack. |
| Cross-site scripting (XSS) | Cross-site scripting is an exploit in which the attacker attaches code to a legitimate website that executes when the victim loads that website.  Typically, a web page is loaded, and malicious code copies the user's cookies.  The system then sends an HTTP request to an attacker's web server, with the stolen cookies in the body of the request.  The attacker can then use cookies to access sensitive data. |
| Phishing | This type of exploit involves using emails or web pages to procure sensitive information, such as usernames and passwords. | 
| Malware | Malware is a piece of malicious code, such as spyware, ransomware, a virus or a worm.  Malware is usually triggered when someone clicks a link or an email attachment, which then installs malicious software. |
| Structured Query Language (SQL) injection | SQL injection is a code injection technique used to modify or retrieve data from SQL databases.  By inserting specialized SQL statements into an entry field, an attacker can execute commands that allow for the retrieval of data from the database. |
| Brute-force attack | Brute-force methods, which involve using trial and error to decode data, can be used to crack passwords and crack encryption keys.  Other targets include API keys, SSH logins, and Wi-Fi passwords. |

&nbsp;

#   Cisco Umbrella

&nbsp;

*Cisco **Umbrella** is a cloud-based secure gateway that helps protect and defend against threats.  Cisco **Umbrella** is the first line of defense.*

Cisco Umbrella incorporates the following security services in its offering, regardless of where the user is located:

-   It blocks malware, ransomware, and phishing attempts from malicious or fraudulent sites.
-   It can be integrates with Cisco AMP and other antivirus engines.
-   It maintains content categories and custom-defined whitelists and blacklists to comply with any organization policy.

&nbsp;

##  **Understanding Umbrella**

&nbsp;

***Cisco Umbrella processes DNS requests retrieved from users or devices on the network.  It only works on HTTP or HTTPS but supports other protocols as well.***

&nbsp;

##  **Cisco Umbrella APIs**

&nbsp;

**Table 11-3** Umbrella APIs

| API | Description |
| -- | -- |
| **Management API** | This API directs customers to manage organizations, networks, network devices, users, and roaming computers and integrate actions in those areas into workflows. |
| **Reporting API** | This API for organizations consists of the following endpoints:<br><li>Destinations:  Most recent requests<li>Destinations:  Top identities<li>Security activity report |
| **Console Reporting API** | This API is for managed service providers and multiple-organization console administrators.  It displays summary information that is available only in those consoles.<br><br>The Console Reporting API has two endpoints:<br><li>**/security-summary**:  This is the security summary, which provides the total requests and the total requests blocked for all child organizations in aggregate, as well as the same information for each child organization.<li>**/detailed-summary**:  This is the deployment summary, which provides the overall deployment status for all customers of the console, as well as deployment details about each child organizations of the console. |
| **Network Device Management API** | A network device identity is any hardware device that can route DNS traffic to the Cisco Umbrella recursive DNS servers.<br><br>The first step is registering the device with Cisco Umbrella.  Once the traffic from a device reaches the DNS servers, the organization with which the device is registered is identified, and policies for the organization can be applied to the traffic. |
| **Enforcement API** | This API enables organizations to manage security-related blocked domain lists. |
| **Investigate API** | The RESTful API allows the querying of the Umbrella DNS database and to show security events and correlations related to the domain queried. |

&nbsp;

##  **Authentication**

&nbsp;

All Cisco Umbrella APIs use ***HTTP-basic*** authentication.  The ***key*** and ***secret*** values need to be ***Base64*** encoded and sent as part of a standard HTTP basic Authorization header.  

API requests are sent over HTTPS and require the credentials to be sent in the Authorization header.  The credentials are the username and password, separated by a colon (:), within a Base64-encoded string.

`"Basic ZGV2YXNjOnN0cm9uZ3Bhc3N3b3Jk"`

&nbsp;

##  **The Management API**

&nbsp;

The Umbrella Management API enables direct customers, service providers (ISPs), managed service providers (MSPs), and managed security service providers (MSSPs) to manage organizations, networks, network devices, users, and roaming computers and integrate actions in their everyday workflow.

The Management API can use the ISP and MSSP endpoints passing the Base64-encoded authorization in the header.

The Management API includes the following:

-   **ISP and MSSP endpoints**:  The API returns the service provider IDs and customer IDs.  These endpoints are for Internet service providers (ISPs), managed service providers (MSPs), using the Master Service license, managed security providers (MSSPs), and partner console users.  To perform these queries, you must have your service provider ID (SPId) from your console's URL.
-   **MSP and multiple-organization endpoints**:  The API creates new MSP customers, returns MSP customer records, and updates and deletes MSP customers.  This endpoint is for MSP and multiple-organization consoles, ***not*** MSPs using MSLA.
-   **Networks**:  The API returns network records and deletes networks.  Note that parent organizations do not have networks.  To create and manage networks on behalf of child organizations, use the organizations/customerID/networks endpoints.
-   **Roaming computers**:  The API returns roaming computer records and updates or deletes roaming computers.
-   **Internal networks**:  The API creates, updates, and deletes internal networks and returns internal network records.
-   **Internal domains**:  The API creates, updates, and deletes internal domains and returns internal domain records.
-   **Virtual appliances**:  The API returns virtual appliance (VA) records and updates or deletes VAs.  Note that you cannot create a virtual application through the API.  A VA must be created within your hypervisor and must be registered as an identity within Umbrella before the API can manage it.
-   **Umbrella sites**:  The API creates, updates, and deletes sites and returns site records.
-   **Users**:  The API creates and deletes users and returns user records.
-   **Roles**:  The API returns a list of roles.
-   **Destination lists**:  The API creates, reads, updates, and deletes destination lists.

&nbsp;

##  **The Enforcement API**

&nbsp;

The Cisco Umbrella Enforcement API is designed to give technology partners the ability to send security events from their platform/service/appliance within a mutual customer's environment to the Umbrella cloud for enforcement.  

With this API, you can list domains or delete individual domains from the list.

The API is restricted to ***HTTPS*** and is hosted at **https://s-platform.api.opendns.com**.  

A ***fixed UUID-v4 customer key*** handles customer authentication to the API.  A key must be supplied with each request to the API.

&nbsp;

##  **The Investigate API**

&nbsp;

The Cisco Umbrella Investigate API is designed to give technology partners the ability to query security events from their platform/service/appliance within  mutual customer's environment to the Umbrella cloud for investigation purposes.

THe Umbrella Investigate API empowers users to query the Umbrella database to deem a domain safe or not safe.

The Investigate API can be accessed via an ***access token***, and the access token can be generated via the ***Umbrella console***.

Developers and customers can use the query Umbrella data via the Investigate API.  Here are a few of the standard categories:

-   **Categorization (shows the status and classification of the domain)**:  This category is often used by developers and customers as the primary classifier to determine whether a domain/IP address is good, bad, or unknown.
-   **Scoring**:  Several scores help rate the potential risk of the domain/IP address.  For example:
    -   **SecureRanks2**:  This score is designed to identify domains that are requested by known infected clients but never requested by clean clients - assuming that these domains are more likely to be bad.  Scores range from -100 (suspicious) to +11 (benign).
    -   **RIP Score**:  This IP reputation score is designed to rate an IP addressed based on the amount of malicious activity hosted at that address.  Scores range from -100 (very suspicious) to 0.
-   **WHOIS record data**:  This category includes the email address used to register the domain, the associated name serve,r historical information, and so on.  It can be used to find out more about the history of the domain and the registrant, including whether the email address was used to register other malicious domains.
-   **Cooccurrences**:  This category depicts other domains that were queried right before or after a given domain and are likely related.  The Investigate API is often used to uncover other domain that may be related to the same attack but are hosted on completely separate networks.
-   **Passive DNS**:  This category depicts the history of domain-to-IP address mapping.  This information is used to see if anything suspicious happened with the domain or IP address.  For example, you might find that the IP address is continually changing or find that the IP address has more domains than previously declared.
-   **Malware file data**:  Information is gathered in the form of malware file analysis and threat intelligence from Cisco AMP Threat Grid.  This kind of information is used to find out if there are any specific malware files associated with a domain and also to query file hashes to see if they're malicious.

There are three return values for domain ***categorization***:

-   **Status**:  The status is -1 if the domain is believed to be malicious, 1 if the domain is believed to be benign, or 0 if it hasn't been classified yet.
-   **Security**:  This field indicates whether there is an Umbrella domain match or whether the domain is associated with one.
-   **Content**:  This field indicates the type of domain (for example, Ecommerce/Shopping, Business Services).

**Table 11-4** Other Umbrella Investigate API Categories:

| API Category | API Endpoint URL |
| -- | -- |
| Classifiers for a domain | `https://investigate.api.umbrella.com/domains/categories/cisco.com.json` |
| Cooccurrences for domain | `http://investigate.api.umbrella.com/recommendations/name/cisco.com.json` |
| Related domains for a domain | `https://investigate.api.umbrella.com/links/name/cisco.com.json` |
| Security information for a domain | `https://investigate.api.umbrella.com/security/name/cisco.com` |
| Domain volume | `https://investigate.api.umbrella.com/domains/volume/cisco.com?start=-2days&stop=now&match=component` |
| Threat Grid sample for a domain, an IP address, or a URL | `https://investigate.api.umbrella.com/samples/cisco.com?limit=100&sortby=score` |

&nbsp;

#   Cisco Firepower

&nbsp;

Cisco Firepower is a ***next-generation firewall (NGFW)***.  NGFWs are part of Cisco's firewall technology, which combines the traditional firewall functionality with an application firewall using an ***intrusion prevention system (IPS)*** with ***deep packet inspection (DPI)*** technology.

Firepower also employs other techniques, such as:

-   Transport Layer Security/Secure Socket Layer (TLS/SSL) encrypted traffic inspection
-   Website filtering
-   Quality of Service (QoS) / bandwidth management
-   Malware inspection

It also has built-in management integration with:

-   Lightweight Directory access Protocol (LDAP)
-   RADIUS
-   Active Directory

NGFWs filter traffic based on the applications or traffic types traversing specific ports.

Firepower provides a combination of firewall and QoS functions in a single application-aware solution.

Characteristic features of most NGFWs:

-   **Standard firewall features**:  These include the traditional (first-generation) firewall functionalities such as a stateful port/protocol inspection, Network address Translation (NAT), and virtual private network (VPN) capabilities.
-   **Application identification and filtering**:  An NGFW identifies and filters traffic based on specific applications rather than just opening ports for all kinds of traffic.  An NGFW prevents malicious apps and activities from using nonstandard ports in order to avoid the firewall.
-   **SSL and SSH inspection**:  NGFWs can inspect SSL- and SSH-encrypted traffic.  An NGFW decrypts traffic, makes sure the applications are allowed, checks other policies, and then re-encrypts the traffic.  This provides additional protection against malicious apps and activities that try to hide by using encryption to avoid the firewall.
-   **Intrusion prevention**:  An NGFW has intelligent capabilities to provide more in-depth traffic inspection to perform intrusion detection and prevention.
-   **ISE integration**:  NGFWs have support of Cisco ISE.  This integration allows authorized users and devices to use specific applications.
-   **Malware filtering**:  NGFWs can provide a reputation-based screening to block applications that have bad reputations.  This functionality can check for phishing, viruses, and other malware sites and apps.

Components of the Firepower solutions:

-   **Firepower Management Center** (a management console that has APIs to control and manage application control, URL filtering, AMP, and so on)
-   **Firepower Threat Defense**

**Figure 11-4** *Firepower Components*

![Figure 11-4 Firepower Components](assets/images/Figure%2011-4%20Firepower%20Components.jpeg)

***Firepower Management Center** provides complete and unified management of firewalls, application control, intrusion prevention, URL filtering, and advanced malware protection.*

&nbsp;

##  **Firepower Management Center API**

&nbsp;

**Figure 11-5** *Firepower Allowing both Northbound and Southbound APIs*

![Figure 11-5 Firepower Allowing both Northbound and Southbound APIs](assets/images/Figure%2011-5%20Firepower%20Allowing%20both%20Northbound%20and%20Southbound%20APIs.jpeg)

&nbsp;

##  **Authentication**

The Firepower APIs are already part of the ***Firepower Management Center (FMC)*** software by default, and the only thing that is required is to enable them via the UI.

The Firepower APIs use ***token-based*** authentication.

The following code uses the Python requests command to make the REST call, the POST method, and the API `https://fmcrestapisandbox.cisco.com/api/fmc_platform/v1/auth/generatetoken`.

**Example 11-9** *Python Code to Generate the Session Token for Firepower Management Center*

```python
""" Generate the session token for FMC """
import requests
import urllib3

urllib3.disable_warnings(urllib3.exceptions.InsecureRequstWarning)

url = "https://fmcrestapisandbox.cisco.com/api/fmc_platform/v1/auth/generatetoken"
headers = {
    'Content-Type': "application/xml",
    'Authorization': "Basic YXNodXRvc2g6V0JVdkE5TXk=",
}
response = requests.request("POST", url, headers=headers)
print(response.headers)
```

The response header contains **'X-auth-access-token': "03d91b3f-eeff-4056-a4a7-e121ddcf8910"**, which needs to be used in all subsequent API calls.

&nbsp;

##  **System Information**

&nbsp;

By using **'X-auth-access-token'** you can now make an API call to get the server version by making a REST call with the GET method and the API `http://fmcrestapisandbox.cisco.com/api/fmc_platform/v1/info/serverversion`.

&nbsp;

##  **Firepower Management Center Object**

&nbsp;

*In Firepower Management Center, a **named object** is a reusable configuration that associates a name with a value.*  When you use that value, you can use the named object instead.

Firepower Management Center (FMC) provides many predefined objects that represent frequently used configuration.  

Group objects reference multiple objects with a single configuration.

Certain predefined objects are groupable, as shown in Table 11-5.

&nbsp;

##  **Object Types**

&nbsp;

**Table 11-5** Firepower Management Center Object Types

| Object Type | Groupable |
| -- | -- |
| Network | Yes |
| Port | Yes |
| Security zone | No |
| Application filter | No |
| VLAN tag | Yes |
| URL | Yes |
| Geolocation | No |
| Variable set | No |
| Security intelligence:  Network, DNS, and URL lists and feeds | No |
| Sinkhole | No |
| File list | No |
| Cipher suite list | No |
| Distinguished name | Yes |
| Public key infrastructure (PKI):  Internal and trusted CA and internal and external certs | Yes |
| Route map | No |
| Community list | No |

&nbsp;

##  **Creating a Network**

&nbsp;

A ***network object*** represents one or more IP addresses. 

&nbsp;

#   Cisco Advanced Malware Protection (AMP)

&nbsp;

***Malware*** is a broad term used to define any malicious activity that aims to infect a network or specific device.  Often, the goal of malware is to steal valuable information, disrupts a user's ability to access data, or cause a device or network to crash.

***Ransomware*** is a common form of malware.  

***Advanced persistent threat (APT)*** is another common form of malware.  APTs allow threat actors to gain access to and control endpoint resources over an extended period in order to steal valuable data without being detected.

***AMP for Endpoints***, which is Cisco's endpoint protection solution, is a cloud-managed tool delivered via the desktop client, mobile devices, and server-based endpoints.  These various endpoints connect to ***AMP Private Cloud***, which has been integrated into the next-generation firewall platform and across network perimeter defense tools such as ESA and WSA.

With Cisco AMP for Endpoints, security teams leverage an integrated solution to proactively and efficiently combat threats in the following ways:

-   **By streamlining incident response process**:  AMP for Endpoints allows security operations teams to have complete visibility into the location and trajectory of malware and automates remediation actions.  It eliminates the arduous incident response process that were necessary in the past.  The incident response typically involves length forensics to check all systems for compromises and to reimage those that have been affected.  Due to resource requirements, many companies have to hire the third-party specialists to manage incident response.  AMP for Endpoints can reduce the time and effort required for incident response and can help companies avoid those engagements.
-   **By consolidating endpoint security tools into a single solution that makes it possible to visualize the environment, patch vulnerabilities, and protectively hunt for malware**:  AMP for Endpoints makes it possible to manage reputation filter, behavior analytics, antivirus engine, exploit prevention, traffic analytics, and more from a single platform.  The AMP for Endpoints management tool also integrates with AMP for Networks.  This integration helps facilitate threat information sharing across network security appliances resulting in comprehensive malware protection and enabling a "see once, block everywhere" architecture.
-   **By automating threat detection and remediation processes**:  Customers can efficiently allocate time and resources and avoid the need to hire additional high-cost employees or sign expensive outsourcing contracts.  This automation also promotes increased job satisfaction on security operations teams, as less time is spent on mundane research tasks.

Automation can be achieved by using the ***AMP for Endpoints API***.

The AMP for Endpoints API enables developers and security teams to do the following:

-   **Ingest events**:  The API stores events in third-party tools, archives extended event histories, and correlates against other logs.
-   **Search**:  The API can find where a file has been, determine if a file has been executed, and capture command-line arguments.
-   **Basic management**:  The API allows you to create groups, move desktop or computers, and manage file lists.

&nbsp;

##  **AMP for Endpoints API Credentials and Authorization**

&nbsp;

The AMP for Endpoints API requires administrators to first set up an API credential.  You can do this via the ***AMP Console*** by navigating to Accounts > API Credentials and then completing the dialog.

Once this is done, an API **client ID/key** pair is generated.  It looks something like this:

-   **Client ID**: deadbeef123448ccc00d
-   **Client key**:  XXXXXXXX-YYYY-ZZZZ-0000-e384ef2dxxxx

Using the API client ID/key , you can now make the API calls as follows:

`https://<clientID>:<clientKEY>@<api_endpoint>`

Also, you can use basic HTTP authentication encoding for the client ID/key and the Authorization header and the credential is Base64 encoded:

`Authorization: Basic ZGVhZGJlZWYxMjM0NDhjY2MwMGQ6WFhYWFhYWFgtWVlZWS1aWlpaLTAwMDAtZTM4NGVmMmR4eHh4`

&nbsp;

##  **Listing All Computers**

&nbsp;

The API **`https://api.amp.cisco.com/v1/computers`** fetches the list of all computers.  It requires ***basic authentication headers*** and uses the ***GET method***.

&nbsp;

##  **List All Vulnerabilities**

&nbsp;

The API **`https://api.amp.cisco.com/v1/vulernabilities`** fetches a list of all vulnerabilities.  The list can be filtered to show only the vulnerable programs detected for a specific time range.  The **start_time** and **end_time** parameters accept the date and time expressed according to ISO 8601.

The list contains a summary of information such as the following on a vulnerability:

-   Application name and version
-   SHA-256 value for the executable file
-   Connectors on which the vulnerable application was observed
-   The most recent CVSS score

The API requires the ***basic authentication headers*** and uses the ***GET method***.

**Table 11-6** AMP for Endpoints API

| Method | API | Description |
| -- | -- | -- |
| GET | `https://api.amp.cisco.com/v1/audit_logs` | Provide audit logs based on the filters specified in the query parameters |
| GET | `https://api.amp.cisco.com/v1/audit_log_types` | Provide a list of all the audit log types supported by the API |
| GET | `https://api.amp.cisco.com/v1/computers` | Fetch the list of computers |
| GET | `https://api.amp.cisco.com/v1/computers/user_activity` | Fetch the list of computers that have observed activity by a given username |
| GET | `https://api.amp.cisco.com/v1/computers/activity` | Search all computers across the organization for any events or activities associated with a file or network operation |
| GET | `https://api.amp.cisco.com/v1/events` | Provide a general query interface for events |
| GET | `https://api.amp.cisco.com/v1/event_types` | Identify and filter events by a unique ID |
| POST | `https://api.amp.cisco.com/v1/event_streams` | Create a new ***Advanced Messaging Queue Protocol (AMQP)*** messaging resource for events information |
| GET | `https://api.amp.cisco.com/v1/file_lists/application_blocking` | Return a list of application-blocking file lists |
| GET/POST | `https://api.amp.cisco.com/v1/groups` | Provide basic information about groups in the organization |
| GET | `https://api.amp.cisco.com/v1/policies` | Return a list of policies |
| GET | `https://api.amp.cisco.com/v1/version` | Fetch the list of versions |
| GET | `https://api.amp.cisco.com/v1/vulnerabilities` | Provide a general query interface for vulnerabilities |

&nbsp;

#   Cisco Identity Service Engine (ISE)

&nbsp;

*Cisco **Identity Services Engine (ISE)** is a network access control and policy enforcement agency platform.*

Cisco ISE provides the following benefits:

-   It identifies every device and every user Id across the network.
-   It enables simple provisioning for devices.
-   It is a simple policy management engine that is centralized and can grant user access.
-   It enables flexible integration with other solutions to spend threat detection, containment, and remediation.

Identification is required in order to access any network resources.  Identification involves using credential.  Credentials are of the form ***passwords***, ***certifications***, ***tokens***, or at the least the ***endpoint's MAC address***.

Cisco ISE determines your level of access, and the moment an endpoint accesses the network access, the network devices generate a ***session ID*** and share it with Cisco ISE.

Once a profile gets associated, various policies can be enforced.  These policies could be the following:

-   **Time-based**:  Policies can allow specific devices only at particular times.
-   **Location-base**d:  Each network element has a piece of location information, devices connected have specific policies attached.
-   **Compliance based**:  Policies can ensure that endpoints have all software patches before they are granted full access.

&nbsp;

##  **ISE REST APIs**

&nbsp;

Cisco ISE has two APIs:

-   **Session API**:  This API allows developers to gather session- and node-specific information by using Cisco ISE to monitor nodes.
-   **External RESTful Services (ERS) API**:  This API enables developers to perform operations on the following types of ISE resources:
    -   Endpoints
    -   Endpoint identity groups
    -   Guest users and internal users
    -   Identity groups
    -   Portals
    -   Profiler policies
    -   Network devices
    -   Network device groups
    -   Security groups

The Cisco ISe administrator must assign special privileges to a user to perform operations using the ERS API.  The Cisco ISE administrator can assign the following two roles to deliver services using the ERS API:

-   **External RESTful Services Admin**:  For full access to all ERS methods (GET, POST, DELETE, PUT).
-   **External RESTful Services Operator**:  For read-only access (GET requests only).

&nbsp;

##  **ERS API Authentication**

&nbsp;

The ***Identity Service Engine (ISE)*** ***External RESTful Services (ERS)*** uses ***HTTP basic authentication***, which requires the credentials to be sent in the ***Authorization header***.  *The credentials are the username and password, separated by a colon (:), within a Base64-encoded string.*  For example:

`"Basic ZGV2YXNjOnN0cm9uZ3Bhc3N3b3Jk"`

All ERS API calls are made to the URL **`https://<IP-of-ISE>:9060/`**.

&nbsp;

##  **Creating an Endpoint Group**

&nbsp;

The API posts the data to create a new endpoint group.  It uses the ***POST method*** and requires ***basic authentication headers***.

**Example 11-16** *Python POST Code to Create a New Endpoint Group*

```python
""" create a new endpointgroup """

import json
import requests

url = "https://ise.devnetsandbox.com/ers/config/endpointgroup"
payload = {
    "EndPointGroup": {
        "name": "DevNet Associate Group",
        "description": "DevNet Associate Group"
    }
}
headers = {
    'content-type': "application/json",
    'accept': "application/json",
    'authorization': "Basic ZGV2YXNjOnN0cm9uZ3Bhc3N3b3JkJw==",
    'cache-control': "no-cache",
}
response = requests.request(
    "POST",
    url,
    data=json.dumps(payload),
    headers=headers
)
print(response.text)
```

The response header contains the newly created group ID:

`Location: https://ise.devnetsandbox.com:9060/ers/config/endpoint
group/00000000-1111-2222-3333-444444444444`

&nbsp;

##  **Creating an Endpoint and Adding it to a Group**

&nbsp;

The API **`https://ise.devnetsandbox.com:9060/ers/config/endpoint** posts the data to create a new endpoint.  It uses the POST method.  

The API uses the **group ID** from the header and requires basic authentication headers.

**Example 11-17** *Python POST Code to Create a New Endpoint*

```python
""" create a new endpoint """
import json
import requests
url = "https://ise.devnetsandbox.com/ers/config/endpoint"
payload = {
    "ERSEndPoint": {
        "name": "DevNet_Endpoint",
        "description": "DevNet Endpoint-1",
        "mac": "FF:EE:DD:03:04:05",
        "groupId": " 00000000-1111-2222-3333-444444444444",
        "staticGroupAssignment": True
    }
}
headers = {
    'content-type': "application/json",
    'accept': "application/json",
    'authorization': "Basic ZGV2YXNjOnN0cm9uZ3Bhc3N3b3JkJw==",
    'cache-control': "no-cache",
}
response = requests.request(
    "POST",
    url,
    data=json.dumps(payload),
    headers=headers
)
print(response.text)
```

The response header contains the newly created endpoint ID:

`Location: https://ise.devnetsandbox.com:9060/ers/config/endpoint/
deadbeef-1111-2222-3333-444444444444`

&nbsp;

##  **Other ISE APIs**

&nbsp;

#   Cisco Threat Grid

&nbsp;

***Threat Grid** is Cisco's unified malware analysis and threat intelligence platform.*

&nbsp;

##  **Threat Grid APIs**

&nbsp;

##  **Threat Grid API Format**

&nbsp;

All Threat Grid API calls are made to the URL **`https://panacea.threatgrid.com/api/`**.

The format of the API is as follows:

**`https://panacea.threatgrid.com/api/<ver>/<api-endpoint>?q=<query>&api_key=apikey`**

where \<ver> could be "v2" or "v3", \<api-endpoint> is the actual API and the apikey is the key associated with the account.

&nbsp;

##  **API Keys**

&nbsp;

You can get the API key from the Threat Grid portal.

This API key is used in every API call that is made to Threat Grid.

&nbsp;

##  **The Data, Sample, and IOC APIs**

&nbsp;

*The **Data API** allows developers to search observables by specific criteria.*  You can do any entity search by using the **/search** endpoint.  You can pivot the Threat Grid data by using the entity lookups **/domains/**, **/urls/**, **/paths/**, and so on.

*The **Sample API** allows developers to submit and retrieve data for analysis.*  You can get the raw observable feeds by using the **samples/feeds/** endpoint.

The ***Indicator of Compromise (IOC) API*** feeds can be accessed via the **/iocs/feeds** endpoint.  With this API, you can see observables in conjunctions with behavior indicators.  Usually, if an item shows up in this feed, it means that there is at least some degree of suspicious behavior associated with the item.  

&nbsp;

##  **Feeds**

Threat Grid supports three different types of feeds:

-   **Sample feeds**:  These are all observables seen.
-   **Indicator of Compromise (IOC) feeds**:  These are observables seen via business intelligence.  IOCs are used to indicate that the system has been affected by some form of malware.
-   **Curated feeds**:  These are highly accurate and high-confidence feeds.

**Table 11-7** Threat Grid Feeds

| | Sample Feeds | IOC Feeds | Curated Feeds |
| -- | -- | -- | -- |
| Version | /v2 | /v2 | /v3 |
| Endpoint | /samples/feeds/ | /iocs/feeds/ | /feeds/ |
| Content | All observables are seen | Observables are seen in all BIs | Observables are seen as part of a trusted high-confidence BI triggering |
| Pre-whitelisted | No | No | Yes |
| Filterable to only you/org? | Yes | Yes | No |
| Output Formats | JSON | JSON | JSON/CSV/Snort/STIX |

**Table 11-8** Curated Feed Types

| Feed Name | Description |
| -- | -- |
| autorun-registry | Registry entry data derived from querying registry changes known for persistence |
| banking-dns | Banking Trojan network communications |
| dga-dns | DGA domains with pseudo-randomly generated names |
| dll-hijacking-dns | Domains communicated to by samples leveraging DLL sideloading and hijacking techniques |
| doc-net-com-dns | Document (PDF, Office) network communications |
| downloaded-pe-dns | Samples downloading executables network communications |
| dynamic-dns | Samples leveraging dynamic DNS providers |
| irc-dns | Internet Relay Chat (IRC) network communications |
| modified-hosts-dns | Modified Windows hosts file network communications |
| parked-dns | Parked domains resolving to RFC 1918 localhost and broadcast addresses |
| public-ip-check-dns | Public IP address network communications |
| ransomware-dns | Samples communicating with ransomware servers |
| rat-dns | Remote Access Trojan (RAT) network communications |
| scheduled-tasks | Scheduled task data observed during sample execution |
| sinkholed-ip-dns | DNS entries for samples communicating with a known DNS sinkhole |
| stolen-cert-dns | DNS entries observed from samples signed with a stolen certificate |

Now let's look at an example of going through all the feed types and printing out the feed if any data exists.  In this case, you can use the GET method and the API `https://panacea.threatgrid.com/api/v2/search/submissions`.  the API key must be passed as a query parameter.  Example 11-22 shows the Python **requests** script you use in this case.

**Example 11-22** *Threat Grid: Listing Details for Each Curated Feed Type*

```python
""" Threat Grid - List details for each curated feed type """
import requests
FEED_URL = "https://panacea.threatgrid.com/api/v3/feeds"
FEEDS_NAME = {
    "autorun-registry": "Autorun Registry Malware",
    "banking-dns": "Banking Trojans",
    "dga-dns": "Domain Generation Algorithm Destinations",
    "dll-hijacking-dns": "DLL Hijackers / Sideloaders",
    "doc-net-com-dns": "Document File Network Communication",
    "downloaded-pe-dns": "Dropper Communication",
    "dynamic-dns": "Dynamic DNS Communication",
    "irc-dns": "IRC Communication",
    "modified-hosts-dns": "Modified HOSTS File Communication",
    "public-ip-check-dns": "Public IP Checkers",
    "ransomware-dns": "Ransomware Communication",
    "rat-dns": "Remote Access Trojans",
    "scheduled-tasks": "Scheduled Task Communication",
    "sinkholed-ip-dns": "Sinkholed IPs",
    "stolen-cert-dns": "Stolen Certificates",
}
for name, desc in FEEDS_NAME.items():
    url = "{}/{}.json".format(FEED_URL, name)
    querystring = {"api_key":"2kdn3muq7uafelcpgib9eccua7"}

    headers = {
        'cache-control': "no-cache",
        'Content-type': 'application/json',
        'Accept': 'application/json'
        }

    response = requests.request("GET", url, headers=headers, params=querystring)

    print(response.text)
```