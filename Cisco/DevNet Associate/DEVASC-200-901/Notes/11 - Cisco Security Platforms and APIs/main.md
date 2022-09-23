# Cisco's Security Portfolio

&nbsp;

Cisco's security portfolio is vast.  This chapter provides an introduction to some of its critical security products.  In addition, it cover the APIs that each of these products supports. 

&nbsp;

As shown in Figure 10-1, the Cisco security portfolio focuses on three areas: visibility, segmentation, and protection.  Visibility is essentially the ability to "see" everything that is happening in the network.  Segmentation is the ability of the network to reduce the surface attack to contain the spread.  Protection is the ability to stop any breaches from happening.

&nbsp;

**Figure 11-1** *Cisco's Security Portfolio: Visibility, Segmentation, and Protection*

![Figure 11-1 Cisco's Security Portfolio: Visibility, Segmentation, and Protection](assets/images/Figure%2011-1%20Cisco's%20Security%20Portfolio%20Visibility%20Segmentation%20and%20Protection.jpeg)

&nbsp;

## Potential Threats and Vulnerabilities

&nbsp;

Anything we are trying to protect against - whether it is code or a person - is known as a threat.  A threat tries to get access to an asset in order to control or damage the asset.

&nbsp;

A vulnerability is a weakness or gap in protection efforts.  It can be exploited by threats to gain unauthorized aggress to an asset.

&nbsp;

Cybersecurity threats comprise a wide range of potentially illegal activities on the Internet.  At a very high level, certain activities may be classified into two categories:

-   **Malicious activities that target networks or devices directly**:  Examples include malware, viruses, and denial-of-service attacks.
-   **Malicious activities aided by computer networks or devices**:  Examples include fraud, identity, theft, phishing scams, information warfare, and cyberstalking.

&nbsp;

## Most Common Threats

&nbsp;

Table 11-2 describes some of the most common threats that can be posed to an entity due to lack of security awareness.

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

# Cisco Umbrella

&nbsp;

>   ***`Key Topic`***

&nbsp;

Cisco Umbrella is a cloud-based secure gateway that helps protect and defend against threats that arise on the Internet.  Cisco Umbrella is the first line of defense for users who may be trying to connect to the Internet from anywhere.  A device trying to connect to the Internet needs a DNS (Domain Name System) lookup to translate the name of the site or the service to the IP address that it needs to connect to.

&nbsp;

Cisco Umbrella processes billions of DNS requests per de, analyzing and learning about various activities and blocking requests to unwanted and malicious destinations before a connection is even established.  Cisco Umbrella incorporates the following security services in its offering, regardless of where the user is located:

-   It blocks malware, ransomware, and phishing attempts from malicious or fraudulent sites.
-   It can be integrated with Cisco AMP and other antivirus engines
-   It maintains content categories and custom-defined whitelists and blacklists to comply with any organization policy.

&nbsp;

## Understanding Umbrella 

&nbsp;

Cisco Umbrella processes DNS requests retrieved from users or devices on the networks.  It not only works on HTTP or HTTPs but supports other protocols as well.

&nbsp;

Let's look at a simple flow using the network shown in Figure 11-2.  Say that a user wants to access a site and makes a request to the site.  This results in a DNS request being sent to Cisco Umbrella.  The following steps occur:

-   **Step 1.**  Umbrella analyzes the DNS request to check whether the domain is malicious or safe.
-   **Step 2.**  Umbrella checks to see if any of the policies are triggered, such as content filtering policies or blacklisted domains.
-   **Step 3.**  If all is well, the IP address is sent to the requesting user.  In the case of stanford.edu, Umbrella returns the correct IP address.
-   **Step 4.**  When a DNS request is sent for domain.xyz, Umbrella checks whether any policies are triggered or whether this is a known malicious domain.
-   **Step 5.**  Umbrella response with a "blocked page" message, informing the user that the domain is either malicious or on the blocked list.

&nbsp;

**Figure 11-2 Cisco** *Umbrella: Blocking a Malicious Domain Lookup*

![Figure 11-2 Cisco Umbrella: Blocking a Malicious Domain Lookup](assets/images/Figure%2011-2%20Cisco%20Umbrella%20Blocking%20a%20Malicious%20Domain%20Lookup.jpeg)

&nbsp;

## Cisco Umbrella APIs

&nbsp;

Cisco Umbrella supports various APIs for different functions.  Table 11-3 describes these APIs.

&nbsp;

**Table 11-3** Umbrella APIs

| API | Description |
| -- | -- |
| Management API | This API directs customers to manage organizations, networks, network devices, users, and roaming computers and integrate actions in those areas into workflows. |
| Reporting API | This API for organizations consists of the following endpoints: <li>Destinations:  Most recent requests<li>Destinations:  Top identities<li>Security activity report |
| Console Reporting API | This API is for managed service providers and multiple-organization console administrators.  It displays summary information that is available only in those consoles.  <br>The Console Reporting API has two endpoints:<li>**/security-summary**:  This is the security summary, which provides the total requests and the total requests blocked for all child organizations in aggregate, as well as the same information for each child organization.<li>**/detailed-summary**:  This is the deployment summary, which provides the overall deployment status for all customers of the console, as well as deployment details about each child organization of the console. |
| Network Device Management API | A network device identity is any hardware device that can route DNS traffic to the Cisco Umbrella recursive DNS servers.  The first step is registering the device with Cisco Umbrella.  Once the traffic from a device reaches the DNS servers, the organization with which the device is registered is identified, and policies for that organization cab be applied to the traffic. |
| Enforcement API | This API enables organizations to manage security-related blocked domain lists. |
| Investigate API | The RESTful API allows the querying of the Umbrella DNS database and to show security events and correlations related to the domain queried. |

&nbsp;

## Authentication 

&nbsp;

All Cisco Umbrella APIs use HTTP-basic authentication.  The key and secret values need to be Base64 encoded and sent as part of a standard HTTP basic Authorization header.  API requests are sent over HTTPS.  APIs require the credentials to be sent in the Authorization header.  The credentials are the username and password, separated by a colon (:), within a Base64-encoded string.  For example, the Authorization header would contain the following string:

`
"Basic ZGV2YXNjOnN0cm9uZ3Bhc3N3b3Jk"
`

&nbsp;

In this case, **ZGV2YXNjOnN0cm9uZ3Bhc3N3b3Jk** is the Base64-encoded string *devasc:strongpassword* (where *devasc* is the username, and *strongpassword* is the password).  Exmaple 11-1 shows three liens of code that do Base64 encoding to plug the value into the Authorization header.

&nbsp;

**Example 11-1** *Python Code to GEnerate Base64 Encoding*

```python
""" Generate Base64 Encoding using the base64 library """

import base64

encoded = base64.b64encode('devasc:strongpassword'.encode('UTF-8')).decode('ASCII')

print(encoded)
```

&nbsp;

## The Management API

&nbsp;

The Umbrella Management API enables direct customers, service providers (SPs), managed service providers (MSPs), and managed security service providers (MSSPs) to manage organizations, networks, network devices, users, and roaming computers and integrate actions in their everyday workflows.

&nbsp;

The Management API can use the ISP and MSSP endpoints passing the Base64-encoded authorization in the header (see Example 11-2).

&nbsp;

Example 11-2 Python Code to Get Customer Details Using the Management API

```python
""" Get Customer details given a customerID """

import requests


url = "https://management.api.umbrella.com/v1/serviceproviders/serviceProviderId/customers/customerId"

headers = {
    'accept': "application/json",
    'authorization': "Basic ZGV2YXNjOnN0cm9uZ3Bhc3N3b3Jk"
}

response = requests.request("GET", url, headers=headers)

print(response.text)
```

&nbsp;

The management API includes the following:

-   **ISP and MSSP endpoints**:  The API returns the service provide IDs and customer IDs.  These endpoints are for Internet service providers (ISPs), managed service providers (MSPs), using the MasteR service license, managed security service providers (MSSPs), and partner console users.  To perform these queries, you must have your service provider ID (SPId) from your console's URL.
-   *MS and multiple-organization endpoints*:  The API creates new MSP customers, returns MSP customer records, and updates and deletes MSP customers.  This endpoint is for MSP and multiple-organization consoles, *not* for MSPs using MSLA.
-   *Networks*.  The API returns network records and deletes networks.  Note that parent organizations do not have networks.  To create and manage networks on behalf of child organizations, use the organizations/customerID/networks endpoints.
-   **Roaming computers**:  The API returns roaming computer records and updates or deletes roaming computers.
-   **Internal networks**:  The API creates, updates, and deletes internal networks and returns internal network records.
-   **Internal domains**:  The API creates, updates, and deletes internal domains and returns internal domain records.
-   **Virtual appliances**:  The API returns virtual appliance (VA) records and updates or deletes VAs.  Note that you cannot create a virtual application through the API.  A VA must be created within your hypervisor and must be registered as an identity within Umbrella before the API can manage it.
-   **Umbrella sites**:  The API creates, updates, and deletes sites and returns site records.
-   **Users**:  The API creates and deletes users and returns user records.
-   **Roles**:  The API returns a list of roles.
-   **Destination lists**:  The API creates, reads, updates, and deletes destination lists.

&nbsp;

## The Enforcement API

&nbsp;

>   ***`Key Topic`***

&nbsp;

The Cisco Umbrella Enforcement API is designed to give technology partners the ability to send security events from their platform/service/appliance within a mutual customer's environment to the Umbrella cloud for enforcement.  With this API, you can list domains or delete individual domains from the list.  

&nbsp;

The API is restricted to HTTPs and is hosted at https://s-platform.api.opendns.com.  A fixed  UUID-v4 customer key handles customer authentication to the API.  A key must be supplied with each request to the API.  To generate or get the customer key, you have to log in to the console and navigate to Policies > Policy Components > Integrations.

&nbsp;

Now let's look at an example of enforcement.  Here are the steps involved when the customer detects a malicious domain and wants to add it to Umbrella:

-   **Step 1.**  The customer identifies a malicious code or a malicious activity as users visit a particular URL or domain.  The detection can occur with third-party software or Cisco AMP or any other mechanism that the customer already has in place.
-   **Step 2.**  This event is sent to the Umbrella Enforcement API via a POST request (see Example 11-3).
-   **Step 3.**  Cisco Umbrella follows the appropriate logic and algorithm before it adds the domain to the blocked list.  It goes through these steps:
    1.  Umbrella checks whether the domain exists in the Umbrella global block list under one of the security categories.
    2.  It runs the Investigate API internally to decide if the domain is benign.
    3.  It checks on the status of the domain (that is, uncategorized or categorized).
    4.  It checks to see if the domain is already present on the customer's allow list within the organization.
-   **Step 4.**  If all the checks are validate,d Umbrella blocks domains in that list per that customer's Umbrella policy security settings.

&nbsp;

**Example 11-3** *Python POST Code to Add a Domain Using the Enforcement API*

```python
""" Add domain using the Enforcement API """

import json
import requests

url = "https://s-platform.api.opendns.com/1.0/events"

querystring = {"customerKey":"XXXXXXX-YYYY-ZZZZ-YYYY-XXXXXXXXXXXX"}
payload = [
    {
        "alertTime": "2020-01-01T09:33:21.0Z",
        "deviceId": "deadbeaf-e692-4724-ba36-c28132c761de",
        "deviceVersion": "13.7a",
        "dstDomain": "looksfake.com",
        "dstUrl": "http://looksfake.com/badurl",
        "eventTime": "2020-01-01T09:33:21.0Z",
        "protocolVersion": "1.0a",
        "providerName": "Security Platform"
    }
]

headers = {
    'Content-Type': "text/plain",
    'Accept': "*/*",
    'Cache-Control': "no-cache",
    'Host': "s-platform.api.opendns.com",
    'Accept-Encoding': "gzip, deflate",
    'Connection': "keep-alive",
    'cache-control': "no-cache"
}

response = requests.request(
    "POST",
    url,
    data=json.loads(payload),
    headers=headers,
    params=querystring
)

print(response.text)
```

&nbsp;

Once domains are placed in the list, a customer can get the list of the domains by using the **GET** method for https://s-platform.api.opendns.com/1.0/domains endpoint.  Example 11-4 shows an example of a simple Python **requests** method.

&nbsp;

**Example 11-4** *Python GET Request to List Domains Using the Enforcement API*

```python
""" List domains using the Enforcement API """

import requests

url = "https://s-platform.api.openns.com/1.0/domains"

querystring = {"customerKey":"XXXXXXX-YYYY-ZZZZ-YYYY-XXXXXXXXXXXX"}

response = requests.request("POST", url, headers=headers, params=querystring)
print(response.text)
```

&nbsp;

Example 11-5 shows the response to the GET from Example 11-4.  The answer is a JSON response with a **meta** tag that describes the page number, and pointers to the previous and next pages.

&nbsp;

**Example 11-5** *Response to the GET Request to List Domains Using the Enforcement API*

```
{
    "meta":{
        "page":1,
        "limit":200,
        "prev":false,
        "next":"https://s-platform.api.opendns.com/1.0/
        domains?customerKey=XXXXXXX-YYYY-ZZZZ-YYYY-XXXXXXXXXXXX&page=2&limit=200"

   },
 "data":[
       {
             "id":1,
             "name":"baddomain1.com"
       },
       {
             "id":2,
             "name":"looksfake.com"
       },
       {
             "id":3,
             "name":"malware.dom"
       }
    ]
}
```

&nbsp;

The final part of the Enforcement API is the **DELETE** call to delete the domain API.  The API helps in unblocking domains that were blocked because of previously injected events.  Example 11-6 shows an example of a simple Python **requests** command to delete a domain using the Enforcement API.  The URL to do this is as follows:
`https://s-platform.api.opendns.com/1.0/domains/looksfake.com?customerKey=XXXXXXX-YYYY-ZZZZ-YYYY-XXXXXXXXXXXX`

&nbsp;

**Example 11-6** *Deleting Domains Using the Enforcement API*

```python
""" Delete domain using the Enforcement API """

import requests

url = "https://s-platform.api.opendns.com/1.0/domains/looksfake.com"

querystring = {"customerKey":"XXXXXXX-YYYY-ZZZZ-YYYY-XXXXXXXXXXXX"}

response = requests.request("DELETE", url, headers=headers, params=querystring)
print(response.text)
```

&nbsp;

## The Investigate API

&nbsp;

>   ***`Key Topic`***

&nbsp;

The Cisco Umbrella Investigate API is designed to give technology partners the ability to query security events from their platform/service/appliance within a mutual customer's environment to the Umbrella cloud for investigation purposes.  The Umbrella Investigate API empowers users to query the Umbrella database to deem a domain saf or not safe.  It goes beyond traditional DNS results to show security events and correlations.

&nbsp;

The following are some of the tasks that can be done via the Umbrella Investigate REST API:

-   Check the security status ofa domain, IP address, or subset of domains that appears in the logs from your firewall, UTM, or other Internet egress points.
-   Determine whether other related cooccurring domains were accessed at the same time as the domain or IP address you're looking up.
-   Find a historical record for this domain or IP address in the DNS database to see what has changed.
-   Query large numbers of domains quickly to find out whether they're scored as malicious and require further investigation.

&nbsp;

The Investigate API can be accessed via an access token, and the access token can be generated via the Umbrella console.

&nbsp;

Developers and customers can use and query Umbrella data via the Investigate API.  Here are a few of the standard categories:

-   **Categorization (shows the status and classification of the domain)**:  This category is often used by developers and customers as the primary classifier to determine whether a domain/IP address is good, bad, or unknown.
-   **Scoring**:  Several scores help rate the potential risk of the domain/IP address.  For example:
    -   **SecureRanks2**:  This score is designed to identify domains that are requested by known infected clients but never requested by clean clients - assuming that these domains are more likely to be bad.  Scores range from -100 (suspicious) to +11 (benign).
    -   **RIP Score**:  This IP reputation score is designed to rate an IP address based on the amount of malicious activity hosted at that address. Scores range from -100 (very suspicious) to 0.
-   **WHOIS record data**:  This category includes the email address used to register the domain, the associated name server, historical information, and so on.  It can be used to find out more about the history of the domain and the registrant, including whether the email address was used to register other malicious domains.
-   **Cooccurrences**:  This category depicts other domains that were queried right before or after a given domain and are likely related.  The Investigate API is often used to uncover other domains that may be related to the same attack but are hosted on completely separate networks.
-   **Passive DNS**:  This category depicts the history of domain-to-IP address mapping.  This information is used to see if anything suspicious happened with the domain or IP address.  For example, you might find that the IP address ic continually changing or find that the IP address has more domains than previous declared.
-   **Malware file data**:  Information is gathered in the form of malware file analysis and threat intelligence from Cisco AMP Threat Grid.  This kind of information is used to find out if there are any specific malware files associated with a domain and also to query file hashes to see if they're malicious.

&nbsp;

Now let's look at a couple of examples of the Investigate API.  If you query the domain at https://investigate.umbrella.com/domain-view/name/cisco.com/view via the user interface, you see a screen like the one shown in Figure 11-3.

&nbsp;

**Figure 11-3** *Umbrella Investigate API via the UI for cisco.com*

![Figure 11-3 Umbrella Investigate API via the UI for cisco.com](assets/images/Figure%2011-3%20Umbrella%20Investigate%20API%20via%20the%20UI%20for%20cisco.com.jpeg)

&nbsp;

As you can see, the domain cisco.com is classified as being Benign, and thet SecureRank score is 2.  Therefore, ciscio.com is a safe domain.  Now let's look at the same operation but via the Investigate API.  The API to call is `https://investigate.api.umbrella.com/domains/categorization/cisco.com`.  Example 11-7 shows a Python **requests** command that makes an API call with the appropriate API key.

&nbsp;

**Example 11-7** *Getting Domain Categorization by Using the Investigate API*

```python
""" Domains categorization using the Investigate API """

import requests

url = "https://investigate.api.umbrella.com/domains/categorization/cisco.com"

querystring = {"showLabels":""}

headers = {
    'authorization': "Bearer deadbeef-24d7-40e1-a5ce-3b064606166f",
    'cache-control': "no-cache",
    }

response = requests.request("GET", url, headers=headers, params=querystring)
print(response.text)
```

&nbsp;

There are three return values for the categorization:

-   **Status**:  The status is -1 if the domain is believed to be malicious, 1 if the domain is believed to be benign, or 0 if it hasn't been classified yet.
-   **Security**:  This field indicates whether there is an Umbrella domain match or whether this domain is associated with one.
-   **Content**:  This field indicates the type of domain (for example, Ecommerce/Shopping, Business Services).

&nbsp;

Example 11-8 shows the response to the request in Example 11-7.  Note that the query parameter **showLabels** in Example 11-7 gives the more human-readable information in the response.

&nbsp;

**Example 11-8** *JSON Returned for Domain Categorization Using the Investigate API*

```
{
    "cisco.com": {
        "status": 1,
        "security_categories": [],
        "content_categories": [
            "Software/Technology",
            "Business Services"
        ]
    }
}
```

&nbsp;

Table 11-4 lists other Investigate API URLs for the cisco.com domain.

&nbsp;

**Table 11-4** Other Umbrella Investigate API Categories

| API Category | API Endpoint URL |
| -- | -- |
| Classifiers for a domain | `https://investigate.api.umbrella.com/domains/categories/cisco.com.json` |
| Cooccurrences for a domain | `https://investigate.api.umbrella.com/recommendations/name/cisco.com.json` |
| Related domains for a domain | `https://investigate.api.umbrella.com/links/name/cisco.com.json` |
| Security information for a domain | `https://investigate.api.umbrella.com/security/name/cisco.com` |
| Domain volume | `https://investigate.api.umbrella.com/domains/volume/cisco.com?start=-2days&stop=now&match=component` |
| Threat Grid sample for a domain, an IP address, or a URL | `https://investigate.api.umbrella.com/samples/cisco.com?limit=100&sortby=score` |

&nbsp;

# Cisco Firepower

&nbsp;

>   ***`Key Topic`***

&nbsp;

Cisco Firepower is a ***next-generation firewall (NGFW)***.  NGFWs are part of Cisco's leading-edge firewall technology, which combines the traditional firewall functionality with an application firewall using an ***intrusion prevention system (IPS)*** with ***deep packet inspection (DPI)*** technology.

&nbsp;

Firepower also employs other techniques, such as ***Transport Layer Security/Secure Socket Layer (TLS/SSL)*** encrypted traffic inspection, website filtering, ***quality of service (QoS)***/bandwidth management, and malware inspection.  It also has built-in management integration with ***Lightweight Directory access Protocol (LDAP)***, RADIUS, and Activate Directory.

&nbsp;

In the past, stateful firewalls with simple packet filtering capabilities efficiently blocked unwanted unwanted applications because most applications met the port/protocol expectations.  NGFWs filter traffic based on the applications or traffic types traversing specific ports.  For example, you could open up port 80 for only selected HTTP traffic or for particular applications, sites, or services that you allow.  Firepower provides a combination of firewall and QoS functions in a single application-aware solutions.  Here are the characteristic features of most NGFWs:

-   **Standard firewall features**:  These include the traditional (first-generation) firewall functionalities such as a stateful port/protocol inspection, ***Network Address Translation (NAT)***, and ***virtual private network (VPN)*** capabilities.
-   **Application identification and filtering**:  An NGFW identifies and filters traffic based on specific applications rather than just opening ports for all kinds of traffic.  An NGFW prevents malicious apps and activities from using nonstandard ports in order to avoid the firewall.
-   **SSL and SSH inspection**:  NGFWs can inspect SSL- and SSH-encrypted traffic.  An NGFW decrypts traffic, makes sure the applications are allowed, checks other policies, and then re-encrypts the traffic.  This provides additional protection against malicious apps and activities that try to hide by using encryption to avoid the firewall.
-   **Intrusion prevention**:  An NGFW has intelligent capabilities to provide more in-depth traffic inspection to perform intrusion detection and prevention.
-   **ISE integration**:  NGFWs have the support of Cisco ISE.  This integration allows authorized users and devices tot use specific applications.
-   **Malware filtering**:  NGFWs can provide a reputation-based screening to block applications that have bad reputations.  This functionality can check for phishing, viruses, and other malware sites and apps.

&nbsp;

Figure 11-4 shows the components of the Firepower solutions:

-   Firepower Management Center (a management console that has APIs to control and manage application control, URL filtering, AMP, and so on)
-   Firepower Threat Defense

&nbsp;

**Figure 11-4** *Firepower Components*

![Figure 11-4 Firepower Components](assets/images/Figure%2011-4%20Firepower%20Components.jpeg)

&nbsp;

Firepower Management Center provides complete and unified management of firewalls, application control, intrusion prevention, URL filtering, and advanced malware protection.  It can help administrators smoothly go from managing firewalls to controlling applications to investigating and remediating malware attacks.

&nbsp;

## Firepower Management Center API

&nbsp;

DevNet has a dedicated developer center for Firepower at https://developer.cisco.com/firepower/.  This site provides links to various Firepower technologies as well as the DevNet sandboxes.

&nbsp;

The Firepower Management Center REST APIs enable you to program Firepower devices in order to automatically provision devices, discover hosts, perform vulnerability analysis, automate and script firewall configurations, deploy policies and controls, and monitor device health.  Figure 11-5 provides an overview of how Firepower Management Center connects to various Firepower devices as well as how you can build your own applications by using REST APIs.

&nbsp;

**Figure 11-5** *Firepower Allowing both Northbound and Southbound APIs*

![Figure 11-5 Firepower Allowing both Northbound and Southbound APIs](assets/images/Figure%2011-5%20Firepower%20Allowing%20both%20Northbound%20and%20Southbound%20APIs.jpeg)

&nbsp;

## Authentication 

&nbsp;

The Firepower APIs are already part of the FMC software by default, and the only thing that is required is to enable them via the UI.  The Firepower APIs use token-based authentication for API users.  Consider the simple example shown in Example 11-9.  It uses the python **requests** command to make the REST call, the POSt method, and the API `https://fmcrestapisandbox.cisco.com/api/fmc_platform/v1/auth/generatetoken`.

&nbsp;

**Example 11-9** *Python Code to Generate the Session Token for Firepower Management Center*

```python
""" Generate the session token for FMC """
import requests
import urllib3
urllib3.disable_warnings(urllib3.exceptions.InsecureRequestWarning)

url = "https://fmcrestapisandbox.cisco.com/api/fmc_platform/v1/auth/generatetoken"
headers = {
    'Content-Type': "application/xml",
    'Authorization': "Basic YXNodXRvc2g6V0JVdkE5TXk=",
   }
response = requests.request("POST", url, headers=headers)
print(response.headers)
```

&nbsp;

The response header contains **'X-auth-access-token': "03d91b3f-eeff-4056-a4a7-e121ddcf8910"**, which needs to be used in all subsequent API calls.

&nbsp;

## System Information

&nbsp;

By using **'X-auth-access-token'** you can now make an API call to get the server version.  Example 11-10 uses the Python **requests** command to make the REST call, the GET method, and the API `https://fmcrestapisandbox.cisco.com/api/fmc_platform/v1/info/serverversion`.

&nbsp;

**Example 11-10** *Python Code to Get the Server Version via the Firepower Management Center API*

```python
""" Get Server Version """
import requests
url = "https://fmcrestapisandbox.cisco.com/api/fmc_platform/v1/info/serverversion"
headers = {
    'X-auth-access-token': "2abd7bdc-16f8-477f-8022-7f193e71c847",
    }
response = requests.request("GET", url, headers=headers, verify=False)
print(response.text)
```

&nbsp;

Now that you know the basics of accessing the API, you can explore all the APIs that Firepower Management Center has to offer.

&nbsp;

As indicated earlier, Cisco DevNet provides an instance of Firepower Management Center in the sandbox.  The easiest way to figure out specific operations available with any version is by searching for "FMC API Explorer."  You can launch the API Explorer by using the URL https://fmc_url/api/api-explorer/, or if you have reserved the DevNet sandbox, you can simply use https://fmcrestapisandbox.cisco.com/api/api-explorer/#.  Figure 11-6 shows the API Explorer, which allows you to explore all possible FMC APIs.

&nbsp;

**Figure 11-6** *The API Explorer, for Trying Out the Firepower Management Center APIs*

![Figure 11-6 The API Explorer, for Trying Out the Firepower Management Center APIs](assets/images/Figure%2011-6%20The%20API%20Explorer,%20for%20Trying%20Out%20the%20Firepower%20Management%20Center%20APIs.jpeg)

&nbsp;

## Firepower Management Center Objects

&nbsp;

***In Firepower Management Center, a named object is a reusable configuration that associates a name with a value.***  When you want to use that value, you can use the named object instead.  Firepower Management Center provides many predefined objects that represent frequently used configurations.  You can use objects in policies, rules, event searches, reports, and dashboards.  The system offers many predefined objects that represent commonly used configurations.  Group objects reference multiple objects with a single configuration.  Certain predefined objects are groupable as shown in Table 11-5, which explains the various object types that are defined in Firepower Management Center.

&nbsp;

## Object Types

&nbsp;

Table 11-5 lists the objects you can create in the Firepower system and indicates which object types can be grouped.

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
| Security intelligence: Network, DNS, and URL lists and feeds | No |
| Sinkhole | No |
| File list | No |
| Cipher suite list | No |
| Distinguished name | Yes |
| Public key infrastructure (PKI): Internal and trusted CA and internal and external certs | Yes |
| Route map | No |
| Community list | No |

&nbsp;

## Creating a Network

&nbsp;

A network object represents one or more IP address.  We use network objects and groups in other objects, including access control policies, network variables, identity rules, network discovery rules, event searches, and reports.  Example 11-11 shows how to generate a token, assign it in the header, and then create a network object.

&nbsp;

Note that the Firepower Management Center instance in Example 11-11 uses the DevNet Sandbox instance (https://fmcrestapisandbox.cisco.com/) of the FMC, which requires reservation.  If you use this example, make sure that you modify the definition of the network object; otherwise the object creation may fail because the object will be already present.  Example 11-11 uses the POST method and the API `/api/fmc_config/v1/domain/" + uuid + "/object/networks`.

&nbsp;

**Example 11-11** *Generating a Session Token and Creating a New Network Object*

```python
""" generate a session token and create a new network object """

import json
import requests

## Globals used in this file
url = "https://fmcrestapisandbox.cisco.com/api/fmc_platform/v1/auth/generatetoken"
server = "https://fmcrestapisandbox.cisco.com"
username = "johnsmith"
password = "pwgDvQt3"
domain = "Global"
token = ""
headers = {
    'Content-Type': "application/json",
}

## Definition of Lab Network (10.10.10.0)

network_lab = {
    "name": "labnetwork-1",
    "value": "10.10.10.0/24",
    "overridable": False,
    "description": "Lab Network Object",
    "type": "Network"
}

def networkOject(network, uuid):
    """ Create a new Network object """

    netpath = "/api/fmc_config/v1/domain/" + uuid + "/object/networks"
    url = server + netpath
    print("-------------------")
    print(headers)
    try:
        response = requests.post(url, data=json.dumps(network), headers=headers,
        verify=False)
        status_code = response.status_code
        resp = response.text
        json_response = json.loads(resp)
        print("status code is: " + str(status_code))
        if status_code == 201 or status_code == 202:
            print("Successfully network created")
        else:
            response.raise_for_status()
        return json_response["name"], json_response["id"]
    except requests.exceptions.HTTPError as err:
        print("Reason Code: " + str(err))
    finally:
        if response:
            response.close()

def generateSessionToken():
    """ Generate a new session token using the username and password """
    global uuid
    global headers
    tokenurl = "/api/fmc_platform/v1/auth/generatetoken"
    url = server + tokenurl
    response = requests.request(
        "POST",
        url,
        headers=headers,
        auth=requests.auth.HTTPBasicAuth(username, password),
        verify=False
    )
    print(response.headers)
    status_code = response.status_code
    if status_code == 201 or status_code == 202:
        print("Successfully network created")
    else:
        response.raise_for_status()

    auth_headers = response.headers
    token = auth_headers.get('X-auth-access-token', default=None)
    headers['X-auth-access-token'] = token
    domains = auth_headers.get('DOMAINS', default=None)
    domains = json.loads("{\"domains\":" + domains + "}")
    for item in domains["domains"]:
        if item["name"] == domain:
            uuid = item["uuid"]
        else:
            print("no UUID for the domain found!")

    print(domains)
    print(uuid)
    print(headers)

## Main - Entry point - Invoke generate token and create network object
if __name__ == "__main__":
    generateSessionToken()
    networkOject(network_lab, uuid)
```

&nbsp;

# Cisco Advanced Malware Protection (AMP)

&nbsp;

This section provides the information you need to understand Cisco's ***Advanced Malware Protection (AMP)*** solution.

&nbsp;

*Malware* is a broad term used to define any malicious activity that aims to infect a network or specific device.  Often, the goal of malware is to steal valuable information, disrupt a user's ability to access data, or cause a device or network to crash.  Ransomware is a common form of malware that has become particularly challenging for many companies.  A threat actor uses ransomware to encrypt files on an endpoint and extort the owner of the information into paying a ransom to receive the decryption key.

&nbsp;

Another common form of malware is an ***advanced persistent threat (APT)***.  APTs allow threat actors to gain access to and control endpoint resources over an extended period in order to steal valuable data without being detected.  In the past, the malware was deployed using malicious files to carry the payload.  Today, malware is being delivered "file-lessly," by being embedded in endpoint memory or operating system functions.  These new malware techniques can be difficult to detect with traditional defense mechanisms.  AMP for Endpoints is useful with such techniques as it provides deep visibility to identify malware in a system, context to understand what is being affected, and control to protect against attack.  AMP for Endpoints, which is Cisco's endpoint protection solution, is a cloud-managed tool delivered via the desktop client, mobile devices, and server-based endpoints.  Figure 11-7 shows how these various endpoints connect to AMP Private Cloud, which has been integrated into the next-generation firewall platform and across network perimeter defense tools such as ESA and WSA.  Cisco has also incorporated this tool into its industry-leading router platforms.

&nbsp;

**Figure 11-7** *AMP Cloud and Endpoints*

![Figure 11-7 AMP Cloud and Endpoints](assets/images/Figure%2011-7%20AMP%20Cloud%20and%20Endpoints.jpeg)

&nbsp;

You can sign up for a free trial account at https://www.cisco.com/c/en/us/products/security/amp-for-endpoints/index.html.  If you already have an account, you can log in into the AMP Private Cloud portal at https://amp.cisco.com.

&nbsp;

With Cisco AMP for Endpoints, security teams leverage an integrated solution to proactively and efficiently combat threats in the following ways:

-   **By streamlining incident response processes**:  AMP for Endpoints allows security operations teams to have complete visibility into the location and trajectory of malware and automates remediation actions.  It eliminates the arduous incident response processes that were necessary in the past.  The incident response typically involves length forensics to check all systems for compromises and to reimage those that have been affected.  Due to resource requirements, many companies have to hire third-party specialists to manage incident response.  AMP for Endpoints can reduce the time and effort required for incident response and can help companies avoid those engagements.
-   **By consolidating endpoint security tools into a single solution that makes it possible to visualize the environment, patch vulnerabilities, and proactively hunt for malware**:  AMP for Endpoints makes it possible to manage reputation filter, behavior analytics, antivirus engine, exploit prevention, traffic analytics, and more from a single platform.  The AMP for Endpoints management tool also integrates with AMP for Networks.  This integration helps facilitate threat information sharing across network security appliances, resulting in comprehensive malware protection and enabling a "see once, block everywhere" architecture.
-   **By automating threat detection and remediation processes**:  Customers can efficiently allocate time and resources and avoid the need to hire additional high-cost employees or sign expensive outsourcing contracts.  This automation also promotes increased job satisfaction on security operations teams, as less time is spent on mundane research tasks.

&nbsp;

Automation can be achieved by using the AMP for Endpoints API, which allows users to exploit their investigations by identifying which endpoints have seen a file, create custom file lists, and move endpoints in and out of triage groups.  The API also makes it possible to collect and archive all events generated in an environment, which in turn makes possible extended historical data correlation.  The AMP for Endpoints API enables developer and security teams to do the following:

-   **Ingest events**:  The API stores events in third-party tool,s archives extended event histories, and correlates against other logs.
-   **Search**:  The API can find where a file has been, determine if a file has been executed, and capture command-line arguments.
-   **Basic management**:  The API allows you to create groups, move desktop or computers, and manage file lists.

&nbsp;

## AMP for Endpoints API Credentials and Authorization

&nbsp;

The AMP for Endpoints API requires administrators to first set up an API credential.  You can do this via the AMP Console by navigating to Accounts > API Credentials and then completing the dialog shown in Figure 11-8.

&nbsp;

**Figure 11-8** *AMP Console: Creating API Credentials*

![Figure 11-8 AMP Console: Creating API Credentials](assets/images/Figure%2011-8%20AMP%20Console%20Creating%20API%20Credentials.jpeg)

&nbsp;

Once this is done, an API client ID/key pair is generated.  It looks something like this:

-   **Client ID**:  deadbeef123448ccc00d
-   **Client key**:  XXXXXXXX-YYYY-ZZZZ-0000-e384ef2dxxxx

&nbsp;

Using the API client ID and key, you can now make the API calls as follows:

`https://<clientID>:<clientKEY>@<api_endpoint>`

&nbsp;

Also, you can use basic HTTP authentication encoding for the client ID and key and the Authorization header.  For the client ID and key generated, the credential is Base64 encoded as "ZGVhZGJlZWYxMjM0NDhjY2MwMGQ6WFhYWFhYWFgtWVlZWS1aWlpaLTAwMDAtZTM4NGVmMmR4eHh4", and the header looks as follows:

`Authorization: Basic ZGVhZGJlZWYxMjM0NDhjY2MwMGQ6WFhYWFhYWFgt
WVlZWS1aWlpaLTAwMDAtZTM4NGVmMmR4eHh4`

&nbsp;

Now let's look at a couple of examples of the AMP for Endpoints API.

&nbsp;

## Listing All Computers

&nbsp;

The API `https://api.amp.cisco.com/v1/computers` fetches the list of all computers.  It requires basic authentication headers and uses the GET method.  example 11-12 shows a Python **requests** command that uses this API.

&nbsp;

**Example 11-12** *Python Code to Get a List of All Computers via API*

```python
"""  GET list of all computers via API """

import requests

url = "https://api.amp.cisco.com/v1/computers"
headers = {
    'authorization': "Basic ZGVhZGJlZWYxMjM0NDhjY2MwMGQ6WFhYWFhYWFgtWVlZWS1aWlpaLTAwMDAtZTM4NGVmMmR4eHh4",
    'cache-control': "no-cache",
    }

response = requests.request("GET", url, headers=headers)
print(response.text)
```

&nbsp;

## Listing All Vulnerabilities

&nbsp;

The API `https://api.amp.cisco.com/v1/vulnerabilities` fetches a list of all vulnerabilities.  The list can be filtered to show only the vulnerable programs detected for a specific time range.  The **start_time** and **end_time** parameters accept the date and time expressed according to ISO 8601.

&nbsp;

The list contains a summary of information such as the following on a vulnerability:

-   Application name and version
-   SHA-256 value for the executable file
-   Connectors on which the vulnerable application was observed
-   The most recent CVSS score

&nbsp;

This API requires the basic authentication headers and uses the GET method.  Example 11-13 shows a Python **requests** command that uses this API.

&nbsp;

**Example 11-13** *Python Code to Get a List of All Vulnerabilities via API*

```python
"""  GET list of all vulnerabilities via API """

import requests

url = "https://api.amp.cisco.com/v1/vulnerabilities"
querystring = {"offset":"0","limit":"1"}
headers = {
    'authorization': "Basic ZGVhZGJlZWYxMjM0NDhjY2MwMGQ6WFhYWFhYWFgtWVlZWS1aWlpaLTAwMDAtZTM4NGVmMmR4eHh4",
    'cache-control': "no-cache",
    }

response = requests.request("GET", url, headers=headers, params=querystring)
print(response.text)
```

&nbsp;

Example 11-14 shows a sample response to the request in Example 11-13

&nbsp;

**Example 11-14** *JSON Response Showing Vulnerabilities*

```
{
  "version": "v1.2.0",
  "metadata": {
    "links": {
      "self": "https://api.amp.cisco.com/v1/vulnerabilities?offset=0&limit=1"
    },
    "results": {
      "total": 1,
      "current_item_count": 1,
      "index": 0,
      "items_per_page": 1
    }
  },
  "data": [
    {
      "application": "Adobe Flash Player",
      "version": "11.5.502.146",
      "file": {
        "filename": "FlashPlayerApp.exe",
        "identity": {
          "sha256": "c1219f0799e60ff48a9705b63c14168684aed911610fec68548ea08f
          605cc42b"
        }
      },
      "cves": [
        {
          "id": "CVE-2013-3333",
          "link": "https://web.nvd.nist.gov/view/vuln/detail?vulnId=CVE-2013-3333",
          "cvss": 10
        },
        {
          "id": "CVE-2014-0502",
          "link": "https://web.nvd.nist.gov/view/vuln/detail?vulnId=CVE-2014-0502",
          "cvss": 10
        }
      ],
      "latest_timestamp": 1574442349,
      "latest_date": "2019-11-22T17:05:49+00:00",
      "groups": [
        {
          "name": "Triage",
          "description": "Triage Group for FireAMP API Docs",
          "guid": "68665863-74d5-4bc1-ac7f-5477b2b6406e"
        }
      ],
      "computers_total_count": 1,
      "computers": [
        {
          "connector_guid": "17d71471-805b-4183-9121-3924b8982fac",
          "hostname": "Demo_ZAccess",
          "active": true,
          "links": {
            "computer": "https://api.amp.cisco.com/v1/
            computers/17d71471-805b-4183-9121-3924b8982fac",
            "trajectory": "https://api.amp.cisco.com/v1/
            computers/17d71471-805b-4183-9121-3924b8982fac/trajectory",
            "group": "https://api.amp.cisco.com/v1/
            groups/68665863-74d5-4bc1-ac7f-5477b2b6406e"
          }
        }
      ]
    }
```

&nbsp;

Table 11-6 shows all other APIs that AMP for Endpoints has to offer.

&nbsp;

**Table 11-6** AMP for Endpoints API

| Method | API | Description |
| -- | -- | -- |
| GET | `https://api.amp.cisco.com/v1/audit_logs` | Provide audit logs based on the filters specified in the query parameters |
| GET | `https://api.amp.cisco.com/v1/audit_log_types` | Provide a list of all the audit log types supported by the API |
| GET | `https://api.amp.cisco.com/v1/computers` | Fetch the list of computers |
| GET | `https://api.cmp.cisco.com/v1/computers/user_activity` | Fetch the list of computers that have observed activity by a given username |
| GET | `https://api.amp.cisco.com/v1/computers/activity` | Search all computers across the organization for any events or activities associated with a file or network operation |
| GET | `https://api.amp.cisco.com/v1/events` | Provide a general query interface for events |
| GET | `https://api.amp.cisoc.com/v1/event_types` | Identify and filter events by a unique ID |
| POST | `https://api.amp.cisco.com/v1/event_streams` | Create a new ***Advanced Messaging Queue Protocol (AMQP)*** messaging resource for events information |
| GET | `https://api.amp.cisoc.com/v1/file_lists/application_blocking` | Return a list of application-blocking file lists |
| GET/POST | `https://api.amp.cisco.com/v1/groups` | Provide basic information about groups in the organization |
| GET | `https://api.amp.cisco.com/v1/policies` | Return a list of policies |
| GET | `https://api.amp.cisco.com/v1/version` | Fetch the list of versions |
| GET | `https://api.amp.cisco.com/v1/vulnerabilities` | Provide a general query interface for vulnerabilities |

&nbsp;

# Cisco Identity Services Engine (ISE)

&nbsp;

>   ***`Key Topic`***

&nbsp;

Cisco ***Identity Services Engine (ISE)*** is a network access control and policy enforcement platform.  Cisco ISE simplifies the delivery of secure access control across wired and wireless multivendor networks and remote VPN connections.  With intelligent sensor and profiling capabilities, ISE penetrates deep to deliver visibility into who and what is accessing your networks and resources.

&nbsp;

Cisco ISE provides the following benefits:

-   It identifies every device and every user ID across the network.
-   It enables simple provisioning for devices.
-   It is a simple policy management engine that is centralized and can grant user access.
-   It enables flexible integration with other solutions to spend threat detection, containment, and remediation.

&nbsp;

Identification is required in order to access any network resources.  Identification involves using credentials.  Credentials are of the form passwords, certificates, tokens, or at the least the endpoint's MAC address.

&nbsp;

Credentials reach Cisco ISE in a process called authentication.  An enterprise can use various authentication protocols, depending on the type of network and the type of endpoints.  With authentication, you basically tell Cisco ISE who you are.

&nbsp;

Authentication typically results in authorization.  After you reveal your identity to Cisco ISE, Cisco ISE determines your level of access. The moment an endpoint accesses the network access, the network devices generate a session ID and share it with Cisco ISE.  Cisco ISE centrally knows what all the endpoints in the network are and where they are connected.

&nbsp;

Today, enterprises already have some kind of identity services such as Microsoft Active Directory or LDAP; in addition, there could be other ODBC servers hosting some user and device accounts.  A PKI infrastructure may already exist to manage certificates, and there might be some mobile device managements and identity providers for single sign-on.  ISE can seamlessly integrate with all such external identity stores and deliver network access control.

Figure 11-9 shows how Cisco ISE integrates with endpoints, networking devices, and external services.

&nbsp;

**Figure 11-9** *ISE: Components and Deployment*

![Figure 11-9 ISE: Components and Deployment](assets/images/Figure%2011-9%20ISE%20Components%20and%20Deployment.jpeg)

&nbsp;

Once a profile gets associate, various policies can be enforce.  These policies could be the following:

-   **Time-based**:  Policies can allow specific devices only at particular times.
-   **Location-based**:  Each network element has a piece of location information, and devices connected have specific policies attached.
-   **Compliance based**:  Policies can ensure that endpoints have all software patches before they are granted full access.

&nbsp;

## ISE REST APIs

&nbsp;

The Cisco DevNet site https://developer.cisco.com/site/security/ provides details of all API docs located at https://developer.cisco.com/docs/identity-services-engine/.  In addition, you can find other resources within the DevNet Sandbox, and you can reserve and use Cisco ISE there.

&nbsp;

Cisco ISE has two APIs:

-   **Session API**:  This API allows developers to gather session- and node-specific information by using Cisco ISE to monitor nodes.
-   ***External RESTful Services (ERS)* API**:  This API enables developers to perform operations on the following types of ISE resources:
    -   Endpoints
    -   Endpoint identity groups
    -   Guest users and internal users
    -   Identity groups
    -   Portals
    -   Profiler policies
    -   Network devices
    -   Network device groups
    -   Security groups

&nbsp;

The cisco ISE administrator must assign special privileges to a user to perform operations using the ERS API.  The Cisco ISE administrator can assign the following two roles to deliver services using the ERS API (see Figure 11-10):

-   External RESTful Services Admin:  For full access to all ERS methods (GET, POST, DELETE, PUT).
-   External RESTful Services Operator:  For read-only access (GET requests only).

&nbsp;

**Figure 11-10** *ISE ERS: Enabling API Access*

![Figure 11-10 ISE ERS: Enabling API Access](assets/images/Figure%2011-10%20ISE%20ERS%20Enabling%20API%20Access.jpeg)

&nbsp;

## ERS API Authentication

&nbsp;

The ISE ERS API uses HTTP basic authentication, which requires the credentials to be sent in the Authorization header.  The credentials are the username and password, separated by a colon (**:**), within a Base64-encoded string.  For example, the Authorization header would contain the following string:

`"Basic ZGV2YXNjOnN0cm9uZ3Bhc3N3b3Jk"`

&nbsp;

In this case, **ZGV2YXNjOnN0cm9uZ3Bhc3N3b3Jk** is the Base64-encoded string *devasc:strongpassword* (where *devasc* is the username and *strongpassword* is the password).  Example 11-15 shows three lines of code that do Base64 encoding to plug the value into the Authorization headers.

&nbsp;

**Example 11-15** *Python Code to Generate Base64 Encoding*

```python
import base64

encoded = base64.b64encode('devasc:strongpassword'.encode('UTF-8')).decode('ASCII')

print(encoded)
```

&nbsp;

All ERS API calls are made to the URL `https://<IP-of-ISE>:9060/`.

&nbsp;

## Creating an Endpoint Group 

&nbsp;

The API posts the data to create a new endpoint group.  It uses the POST method and requires basic authentication headers.  The following shows the payload that is needed to create an Endpoint Group called 'DevNet Associate Group':

&nbsp;

```
Data - {

    "EndPointGroup" : {

    "name" : "DevNet Associate Group",
    "description" : "DevNet Associate Group"  

  }

}
```

&nbsp;

Example 11-16 shows a Python **requests** command using this API.

&nbsp;

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

&nbsp;

The response header contains the newly created group ID:

`Location: https://ise.devnetsandbox.com:9060/ers/config/endpoint
group/00000000-1111-2222-3333-444444444444`

&nbsp;

## Creating an Endpoint and Adding it to a Group

&nbsp;

The API `https://ise.devnetsandbox.com:9060/ers/config/endpoint` posts the data to create a new endpoint.  It uses the POSt method.  the following shows the payload that is needed to create an Endpoint called 'DevNet Endpoint' with a specified groupId.

&nbsp;

Method: POST

URL: 

```

Data - {
  "ERSEndPoint" : {
    "name" : "DevNet_Endpoint",
    "description" : "DevNet Endpoint-1",
    "mac" : "FF:EE:DD:03:04:05",
    "groupId" : " 00000000-1111-2222-3333-444444444444",
    "staticGroupAssignment" : true
  }
}
```

&nbsp;

This API uses the group ID from the header and requires basic authentication headers.  Example 11-17 shows a Python **request** script.

&nbsp;

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

&nbsp;

The response header contains the newly created endpoint ID:

`Location: https://ise.devnetsandbox.com:9060/ers/config/endpoint/
deadbeef-1111-2222-3333-444444444444`

&nbsp;

## Other ISE APIs

&nbsp;

For a complete list of all Cisco ISE APIs, see https://developer.cisco.com/docs/identity-services-engine/.

&nbsp;

# Cisco Threat Grid

&nbsp;

>   ***`Key Topic`***

&nbsp;

Threat Grid is Cisco's unified malware analysis and threat intelligence platform.  The idea behind Threat Grid is to present a combined analysis engine that can leverage and unify multiple capabilities and multiple infrastructures within an organization.  It does this by performing static and dynamic analysis and producing reports and indicators that are human readable.  File records are uploaded typically via the portal or API, and the output or results are usually consumed also via content-rich threat intelligence feeds.  Figure 11-11 shows the various functions that Cisco Threat Grid performs.

&nbsp;

**Figure 11-11** *Threat Grid in a Nutshell*

![Figure 11-11 Threat Grid in a Nutshell](assets/images/Figure%2011-11%20Threat%20Grid%20in%20a%20Nutshell.jpeg)

&nbsp;

Threat Grid integrates real-time behavioral analysis and up-to-the-minute threat intelligence feeds with existing security technologies to protect a network from both known and unknown attacks.  Threat Grid analyzes suspicious files against more than 1000 behavioral indicators and a malware knowledge base sourced from around the world to provide more accurate, context-rich threat analytics than ever before.

&nbsp;

Figure 11-12 shows the Cisco Threat Grid solution architecture.

&nbsp;

Figure 11-12 Threat Grid Solution Architecture

![Figure 11-12 Threat Grid Solution Architecture](assets/images/Figure%2011-12%20Threat%20Grid%20Solution%20Architecture.jpeg)

&nbsp;

On the left side of Figure 11-12 is the Cisco portfolio, and on the right are the non-Cisco or integration partners.  The numbers in the figure correspond with the following details:

1.  The solution can be integrates across the Cisco security portfolio, including AMP for Endpoints, AMP for Networks, ASA with Firepower, ESA, WSA, and Meraki.
2.  Threat Grid can be deployed as either a cloud-based software-as-a-service product or an on-premises appliance.
3.  A subscription to Threat Grid provides threat intelligence through the API.
4.  Threat intelligence is automatically delivered to security-monitoring platforms.
5.  Third-party integrations automatically submit samples and consume threat intelligence.
6.  Context-rich analysis empowers junior analysts to make more accurate decisions more quickly.

&nbsp;

## Threat Grid APIs

&nbsp;

The Threat Grid APIs offer a broad range of functionality, including user and organization account management, samples (file/malware/signature management), sample analysis data collection, and threat intelligence harvesting.  The Cisco DevNet site https://developer.cisco.com/treat-grid/ provides details, API documentation, and a lot of other information.  You can sign up for a free trial account at https://www.cisco.com/c/en/us/products/security/promotions-free-trials.html#~trials.  Once oyu have access, you can download all the APIs.

&nbsp;

## Threat Grid API Format

&nbsp;

All Threat Grid API calls are made to the URL `https://panacea.threatgrid.com/api/`.  The format of the API is as follows:

`https://panacea.threatgrid.com/api/<ver>/<api-endpoint>?q=<query>&api_key=apikey`

where \<ver> could be "v2" or "v3", \<api-endpoint> is the actual API and the apikey is the key associated with the account.

&nbsp;

## API Keys

&nbsp;

To get the API key from the Threat Grid portal UI, follow these steps:

-   **Step 1.**  Go to the Threat Grid portal UI.
-   **Step 2.**  From the Welcome menu in the upper-right corner of the navigation bar, select Manage Users
-   **Step 3.**  Navigate (use Search if necessary) to the User Details page for the integration's user account and copy the API key.

&nbsp;

This API key is used in every API call that is made to Threat Grid.

&nbsp;

The following sections provide some examples of working with the Threat Grid APIs.

&nbsp;

## Who Am I 

&nbsp;

To see if the API key is working, you can use the GET method and the API `https://panacea.threatgrid.com/api/v3/session/whoami`.  You need to pass the API key as a query parameter, as shown in Example 11-18.

&nbsp;

**Example 11-18** *Threat Grid: Who Am I*

```python
""" Threat Grid - who am I """
import requests
url = "https://panacea.threatgrid.com/api/v3/session/whoami"
querystring = {"api_key":"deadbeefelcpgib9ec0909"}
headers = {
    'cache-control': "no-cache",
}
response = requests.request(
    "GET",
    url,
    headers=headers,
    params=querystring
)
print(response.text)
```

&nbsp;

Example 11-19 shows the JSON response to the request in Example 11-18

&nbsp;

**Example 11-19** *Threat Grid Response*

&nbsp;

```
{
    "api_version": 3,
    "id": 1234567,
    "data": {
        "role": "user",
        "properties": {},
        "integration_id": "z1ci",
       "email": "devasc@student.com",
        "organization_id": 666777,
        "name": "devasc",
        "login": "devasc",
        "title": "DevNet Associate",
        "api_key": " deadbeefelcpgib9ec0909",
        "device": false
    }
}
```

&nbsp;

## The Data, SAmple, and IOC APIs

&nbsp;

The DATA API allows developers to search observables by specific criteria.  You can do an entity search by using the /search/ endpoint.  You can pivot the Threat Grid data by using the entity lookups /domains/, /urls/, /paths/, and so on.

&nbsp;

The Sample API allows developers to submit and retrieve data for analysis.  You can get the raw observable feeds by using the /samples/feeds/ endpoint.  The data is usually harvested from all sample activity, suspicious or not, and therefore has a very large footprint.  You can use this API to query feeds to look at the sample for your organization only.

&nbsp;

The ***Indicator of Compromise (IOC)*** API feeds can be accessed via the /iocs/feeds endpoint.  With this API, you can see observables in conjunction with behavior indicators.  Usually, if an item shows up in this feed, it means that there is at least some degree of suspicious behavior associated with the item.  Also, filters can be applied to see only samples from your organization.

&nbsp;

Let's look at an example.  In this example, we will search for all records that have a sha1 value equal to **"8fbb3bd96b80e28ea41107728ce8c073cbadb0dd"**.  To do so, we use the GET method and the API `https://panacea.threatgrid.com/api/v2/search/submissions`, and we need to pass the API key as a query parameter.  Example 11-20 shows the Python **requests** scripts to use in this case.

&nbsp;

**Example 11-20** *Threat Grid: Searching Submissions*

```python
""" Threat Grid - search submissions API """
import requests

url = "https://panacea.threatgrid.com/api/v2/search/submissions"
querystring = {
    "q": "8fbb3bd96b80e28ea41107728ce8c073cbadb0dd",
    "api_key": "deadbeefelcpgib9ec0909"
}
headers = {
    'cache-control': "no-cache",
}
response = requests.request(
         "GET",
         url,
         headers=headers,
         params=querystring
)
print(response.text)
```

&nbsp;

Example 11-21 shows the JSON response to the request in Example 11-20.

&nbsp;

**Example 11-21** *Threat Grid Search Response*

```
{
    "api_version": 2,
    "id": 4482656,
    "data": {
        "index": 0,
        "total": 1,
        "took": 3956,
        "timed_out": false,
        "items_per_page": 100,
        "current_item_count": 1,
        "items": [
            {
                "item": {
                    "properties": {
                        "metadata": null
                    },
                    "tags": [],
                    "vm_runtime": 300,
                    "md5": "b5c26cab57c41208bd6bf92d495ee1f0",
                    "state": "succ",
                    "sha1": "8fbb3bd96b80e28ea41107728ce8c073cbadb0dd",
                    "sample": "b7d3dd2a6d47ea640f719cc76c2122f8",
                    "filename": "FlashPlayer.exe",
....cut
```

&nbsp;

## Feeds

&nbsp;

Threat Grid supports three different types of feeds:

-   **Sample feeds**:  These are all observables seen.
-   ***Indicator of Compromise (IOC)* feeds**:  These are observables seen via business intelligence.  IOCs are used to indicate that the system has been affected by some form of malware.
-   **Curated feeds**:  These are highly accurate and high-confidence feeds.

&nbsp;

Table 11-7 shows the difference between these feeds.

&nbsp;

**Table 11-7** Threat Grid Feeds

| | Sample Feeds | IOC Feeds | Curated Feeds |
| -- | -- | -- | -- |
| Version | /v2 | /v2 | /v3 |
| Endpoint | /samples/feeds/ | /iocs/feeds/ | /feeds/ |
| Content | All observables are seen | Observables are seen in all BIs | Observables are seen as part of a trusted high-confidence BI triggering |
| Pre-whitelisted | No | No | Yes |
| Filterable to only you/org? | Yes | Yes | No |
| Output Formats | JSON | JSON | JSON/CSV/Snort/STIX |

&nbsp;

Say that you want to retrieve all the curated feeds via API.  The curated feed types are shown in Table 11-8.

&nbsp;

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

&nbsp;

Now let's look at an example of going through all the feed types and printing out the feed if any data exists.  In this case, you can use the GET method and the API `https://panacea.threatgrid.com/api/v2/search/submissions`.  the API key must be passed as a query parameter.  Example 11-22 shows the Python **requests** script you use in this case.

&nbsp;

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
