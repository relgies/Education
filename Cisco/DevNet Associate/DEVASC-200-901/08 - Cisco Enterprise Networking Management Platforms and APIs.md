#  Cisco Enterprise Networking Management Platforms and APIs

&nbsp;

##  "Do I Know This Already?"  Quiz

&nbsp;

-   What are some of the features of a good SDK?  (Choose three.)
    -   Is easy to use
    -   Is well documented
    -   Integrates well with other SDKs
    -   Impacts hardware resources

&nbsp;

-   What are the advantages of using an SDK?  (Choose two.)
    -   Quicker integration
    -   Faster development
    -   Advanced customization
    -   Error handling

&nbsp;

-   What APIs does the Cisco Meraki platform provide to developers?  (Choose two.)
    -   Captive Portal API
    -   Scanning API
    -   Access Point API
    -   Infrastructure API

&nbsp;

-   What is the name of the Cisco Meraki Dashboard API authentication header?
    -   X-Cisco-Meraki-API-Key
    -   X-Cisco-Meraki-Token
    -   X-Cisco-Meraki-Session-key
    -   Bearer

&nbsp;

-   What is the base URL for the Cisco Meraki Dashboard API?
    -   <div style="display: inline">https://api.meraki.com/api/v0</div>
    -   <div style="display: inline">https://api.meraki.com/v1/api</div>
    -   <div style="display: inline">https://api.meraki.cisco.com/api/v0</div>
    -   <div style="display: inline">https://api.meraki.cisco.com/v1/api</div>

&nbsp;

-   What type of authentication do the Cisco DNA Center platform APIs use?
    -   No auth
    -   API key
    -   Basic auth
    -   Hash-based message authentication

&nbsp;

-   When specifying the timestamp parameters with the Cisco DNA Center APIs, what format should the time be in?
    -   UNIX time
    -   OS/2
    -   OpenVMS
    -   SYSTEMTIME

&nbsp;

-   What is the output of the multivendor SDK for Cisco DNA Center platform?
    -   Device driver
    -   Device package
    -   Software driver
    -   Software package

&nbsp;

-   Which components of the Cisco SD-WAN fabric exposes a public REST API interface?
    -   vSmart
    -   vBond
    -   vManage
    -   vEdge

&nbsp;

-   When initially authenticating to the Cisco SD-WAN REST API how are the username and password encoded?
    -   application/postscript
    -   application/xml
    -   application/json
    -   application/x-www-form-urlencoded

&nbsp;

## What is an SDK?

&nbsp;

An SDK (software development kit) or devkit is a set of software development tools that developers can use to create software or applications for a certain platform, operating system, computer system, or device.  An SDK typically contains a set of libraries, APIs, documentation, tools, sample code, and processes that make it easier for developers to integrate, develop, and extend the platform.  An SDK is created for a specific programming language, and it is very common to have the same functionality exposed through SDKs in different programming languages.

&nbsp;

Chapter 6 "Application Programming Interfaces (APIs)," describes what an API is, and Chapter 7 covers the most common API framework these days, the REST API framework.  As a quick reminder, an application programming interface (API) is, as the name implies, a programming interface that implements a set of rules developers and other software systems can use to interact with a specific application.

&nbsp;

As you will see in this chapter and throughout this book, where there is an API, there is usually also an SDK.  Software developers can, of course, implement and spend time on developing code to interact with an API (for example, building their own Python classes and methods to authenticate, get data from the API, or create new objects in the API), or they can take advantage of the SDK, which makes all these objects already available.  

&nbsp;

Besides offering libraries, tools, documentation, and sample code, some SDKs also offer their own integrated development environments (IDEs).  For example, the SDK available for mobile application development on Google Android and Apple iOS also make available an IDE to give developers a complete solution to create, test, debug, and troubleshoot their applications.

&nbsp;

>  ***`Key Topic`***

&nbsp;

A good SDK has these qualities:

-   Is easy to use
-   Is well documented
-   Has value-added functionality
-   Integrates well with other SDKs
-   Has minimal impact on hardware resources

&nbsp;

In order to be used by developers, an SDK should be easy to use and follow best practices for software development in the programming language for which the SDK was developed.  For example, for Python development, there are Python Enhancement Proposals (PEPs), which are documents that provide guidance and spell out best practices for how PYthon code should be organized, packaged, released, deprecated, and so on.  PEP8 is a popular standard for styling Python code and is extensively used in the developer community.  Documenting the SDK inline as well as having external documentation is critical to developer adoption and the overall quality of the SDK.  Having good, up-to-date documentation of the SDK makes the adoption and understanding of the code and how to use it much easier.  A good SDK also adds value by saving development time and providing useful features.  Integrating with other SDKs and development tools should be easy and scalable, and the code should be optimized for minimal hardware resource utilization as well as execution time.

&nbsp;

>  ***`Key Topic`***

&nbsp;

SDKs provide the following advantage:

-   Quicker integration
-   Faster and more efficient development
-   Brand control
-   Increased security
-   Metrics

&nbsp;

As mentioned previously, there are significant development time savings when adopting SDKs, as the functionality and features provided by an SDK don't have to be developed in house.  This leads to quicker integration with the API and quicker time to market.  In addition, brand control can be enforced with the SDK.  The look and feel of applications developed using the SDK can be uniform and in line with the overall brand design.  For example, applications developed for iOS using the Apple SDK have a familiar and uniform look and feel because they use the building blocks provided by the SDK.  Application security best practices can be enforced through SDKs.  When you develop using a security-conscious SDK, the applications developed have the SDK's security features integrated automatically.  Sets of metrics and logging information can be included with an SDK to provide better insights into how the SDK is being used and for troubleshooting and performance tweaking.

&nbsp;

It is critical to ensure a great experience for all developers when interacting with an API.  In addition, offering a great SDK with an API is mandatory for success.

&nbsp;

Cisco has been developing applications and software since its inception.  As the requirements for integrations with other applications and systems have grown, APIs have been developed to make it easier for developers and integrators to create and develop their own solutions and integrations.  Throughout the years, software architectures have evolved, and currently all Cisco solutions provide some type of API.  As mentioned earlier, where there is an API, there is usually also an SDK.

&nbsp;

The starting point in exploring all the SDKs that Cisco has to offer is https://developer.cisco.com.  As you will see in the following sections of this chapter and throughout this book, there are several SDKs developed by Cisco and third parties that take advantage of the APIs that currently exist with all Cisco products.

&nbsp;

##  Cisco Meraki

&nbsp;

Meraki became part of Cisco following its acquisition in 2012.  The Meraki portfolio is large, comprising wireless, switching, security, and video surveillance products.  The differentiating factor for Meraki, compared to similar products from Cisco and other vendors, is that management is cloud based.  Explore all the current Cisco Meraki products and offerings at https://meraki.cisco.com.

&nbsp;

>  ***`Key Topic`***

&nbsp;

From a programmability perspective, the Meraki cloud platform provides several APIs:

-   Captive Portal API
-   Scanning API
-   MV Sense Camera API
-   Dashboard API

&nbsp;

The Cisco Meraki cloud platform also provides webhooks, which offer a powerful and lightweight way to subscribe to alerts sent from the Meraki cloud when an event occurs.  (For more about webhooks, see Chapter 7.)  A Meraki alert includes a JSON-formatted message that can be configured to be sent to a unique URL, where it can be further processed, stored, and acted upon to enable powerful automation workflow and use cases.

&nbsp;

The Captive Portal API extends the power of the built-in Meraki splash page functionality by providing complete control of the content and authentication process that a user interacts with when connecting to a Meraki wireless network.  This means Meraki network administrators can completely customize the portal, including the onboarding experience for clients connecting to the network, how the web page looks and feels, and then authentication and billing processes.

&nbsp;

The Scanning API takes advantage of Meraki smart devices equipped with wireless and BLE (Bluetooth Low Energy) functionality to provide location analytics and report on user behavior.  This can be especially useful in retail, healthcare, and enterprise environments, where business intelligence and information can be extracted about trends and user engagement behavior.  The Scanning API delivers data in real time and can be used to detect Wi-Fi and BLE devices and clients.  The data is exported to a specified destination server through the HTTP POST and JSON documents.  At the destination server, this data can then be further processed and applications can be built on top of the received data.  Taking into consideration the physical placement of the access points on the floor map, the Meraki cloud can estimate the location of the clients connected to the network.  The geolocation coordinates of this data vary based on a number of factors and should be considered as a best-effort estimate.

&nbsp;

The MV Sense Camera API takes advantage of the powerful onboard processor and a unique architecture to run machine learning workloads at the edge.  Through the MV Sense API, object detection, classification, and tracking are exposed and become available for application integration.  You can, for example, extract business insight from video feeds at the edge without the high cost of compute infrastructure that is typically needed with computer imaging and video analytics.  Both REST and MQTT API endpoints are provided, and information is available in a request or subscribe model.  MQ Telemetry Transport (MQTT) is a client/server publish/subscribe messaging transport protocol.  It is lightweight, simple, open, and easy to implement.  MQTT is ideal for use in constrained environments such as Internet of Things (IoT) and machine-to-machine communication where a small code footprint is required.

&nbsp;

The Meraki APIs covered so far are mostly used to extra data from the cloud platform and build integrations and applications with that data.  The Dashboard API, covered next, provides endpoints and resources for configuration, management, and monitoring automation of the Meraki cloud platform.  The Dashboard API is meant to be open ended and can be used for many purposes and use cases.  Some of hte most common use case for the Dashboard API are as follows:

-   Provisioning new organizations, administrators, networks, devices, and more
-   Configuring networks at scale
-   Onboarding and decommissioning of clients
-   Building custom dashboards and applications

&nbsp;

To get access to the Dashboard API, you first need to enable it.  Begin by logging into the Cisco Meraki dashboard at https://dashobaord.meraki.com using your favorite web browser and navigating to Organization > Settings.  From there, scroll down and locate the section named Dashboard API Access and make sure you select Enable Access and save the configuration changes at the bottom of the page.  Once you have enabled the API, select your username at the top-right corner of the web page and select My Profile.  In your profile, scroll down and locate the section named Dashboard API Access and select Generate New API Key.  The API key you generate is associated with your account.  You can generate, revoke, and regenerate your API key in your profile.  Make sure you copy and store your API key in a safe place, as whoever has this key can impersonate you and get access through the Dashboard API to all the information your account has access to.  For security reasons, the API key is not stored in plaintext in your profile, so if you lose the key, you will have to revoke the old one and generate a new one.  If you believe that your API key has been compromised, you can generate a new one to automatically revoke the existing API key.  

&nbsp;

Every Dashboard API request must specify an API key within the request header.  If a missing or incorrect API key is specified, the API returns a 404 HTTP error message.  Recall from Chapter 7 that HTTP error code 404 means that the API resource you were trying to reach could not be found on the server.  This error code prevents information leakage and unauthorized discovery of API resources.

&nbsp;

The key for the authentication request header is **X-Cisco-Meraki-API-Key**, and the value is the API key oyu obtained previously.

&nbsp;

In order to mitigate abuse and denial-of-service attacks, the Cisco Meraki Dashboard API is limited to 5 API calls per second per organization.  In the first second, a burst of an additional 5 calls is allowed, for a maximum of 15 API calls in the first 2 seconds per organization.  If the rate limit has been exceeded, an error message with HTTP status code 429 is returned.  The rate-limiting technique that the Dashboard API implements is based on the token bucket model.  The token bucket is an algorithm used to check that the data that is transmitted in a certain amount of time complies with set limits for bandwidth and burstiness.  Based on this model, if the number of API requests crosses the set threshold for a certain amount of time, you have to wait a set amount of time until you can make another request to the API.  The time you have to wait depends on how many more requests you have performed above the allowed limit; the more requests you performed, the more time you have to wait.

&nbsp;

The Cisco Meraki Dashboard API uses the base URL **https://api.meraki.com/api/v0**.  Keep in mind that the API will evolve and different versions will likely be available in the future.  Always check the API documentation for the latest information on all Cisco APIs, including the Meraki APIs, at https//developer.cisco.com.

&nbsp;

To make it easier for people to become comfortable with the Meraki platform, the Dashboard API is organized to mirror the structure of the Meraki dashboard.  WHen you become familiar with either the API or the GUI, it should be easy to switch between them.  The hierarchy of the Dashboard API looks as follows:

-   Organizations
    -   Networks
        -   Devices
            -   Uplink

&nbsp;

Most Dashboard API calls require either the organization ID or the network ID as part of the endpoint.  (You will see later in this chapter how to obtain these IDs and how to make Dashboard API calls.)  When you have these IDs, you can build and make more advanced calls to collect data, create and update new resources, and configure and make changes to the network.  Remember that all API calls require an API key.

&nbsp;

If your Meraki dashboard contains a large number of organizations, networks, and devices, you might have to consider pagination when making API calls.  Recall from Chapter 7 that pagination is used when the data returned from an API call is too large and needs to be limited to a subset of the results.  The Meraki Dashboard API supports three special query parameters for pagination:

-   **perPage**:  The number of entries to be returned in the current request
-   **startingAfter**:  A value used to indicate that the returned data will start immediately after this value
-   **endingBefore**:  A value used to indicate that the returned data will end immediately before this value

While the types of the **startingAfter** and **endingBefore** values differ based on API endpoints, they generally are either timestamps specifying windows in time for which the data should be returned or integer values specifying IDs and ranges of IDs.

&nbsp;

The Dashboard API also supports action batches, which make it possible to submit multiple configuration requests in a single transaction and are ideal for initial provisioning of a large number of devices or performing large configuration changes through the whole network.  Action batches also provide a mechanism to avoid hitting the rate limitations implemented in the API for high-scale configuration changes as you can implement all the changes with one or a small number of transactions instead of a large number of individual API requests.  Action batch transactions can be run either synchronously, waiting for the API call return before continuing, or asynchronously, in which case the API call does not wait for a return as the call is placed in a queue for processing.  (In Chapter 7 you saw the advantages and disadvantages of both synchronous and asynchronous APIs.)  With action batches, you can be confident that all the updates contained in the transaction were submitted successfully before being committed because batches are run in an atomic fashion: all or nothing.

&nbsp;

After you have enabled the Meraki Dashboard API, generated the API key key, and saved it in a safe place, you are ready to interact with the API.  For the rest of this chapter, you will use the always-on Cisco DevNet Meraki Sandbox, which can be found at https://developer.cisco.com/sandbox.  The API key for this sandbox is 15da0c6ffff295f16267f88f98694cf29a86ed87.

&nbsp;

>  ***Personal Note**:  These credentials didn't work.  I followed the instructions from earlier about generating an API key and did that.  Also it was using v1 instead of v0.*

&nbsp;

At this point, you need to obtain the organization ID for this account.  As you saw in Chapter 7, there are several ways you can interact with the API:  You can use tools like curl and Postman, or you can interact with the API through programming languages and the libraries that they provide.  In this case, you will use curl and Postman to get the organization ID for the Cisco DevNet Sandbox account and then the Cisco Meraki Python SDK.

&nbsp;

As mentioned earlier, the base URL for the Dashboard api is https://api.meraki.com/api/v0.  In order to get the organizations for the account with the API key mentioned previously, you have to append the /organizations resources to the base URL.  The resulting endpoint becomes https://api.meraki.com/api/v0/organizations.  You also need to include the X-Cisco-Meraki-API-Key header for authentication purposes.  This header will contain the API key for the DevNet Sandbox Meraki account.  The **curl** command should look as follows in this case:

&nbsp;

```
curl -I -X GET \
   --url 'https://api.meraki.com/api/v0/organizations' \
   -H 'X-Cisco-Meraki-API-Key: 6bec40cf957de430a6f1f2baa056b99a4fac9ea0'
```

&nbsp;

The response should look as shown in Example 8-1.

&nbsp;


**Example 8-1** *Headers of the GET Organizations REST API Call*

```
HTTP/1.1 302 Found
Server: nginx
Date: Sat, 17 Aug 2019 19:05:25 GMT
Content-Type: text/html; charset=utf-8
Transfer-Encoding: chunked
Connection: keep-alive
Cache-Control: no-cache, no-store, max-age=0, must-revalidate
Pragma: no-cache
Expires: Fri, 01 Jan 1990 00:00:00 GMT
X-Frame-Options: sameorigin
X-Robots-Tag: none
Location: https://n149.meraki.com/api/v0/organizations
X-UA-Compatible: IE=Edge,chrome=1
X-Request-Id: 87654dbd16ae23fbc7e3282a439b211c
X-Runtime: 0.320067
Strict-Transport-Security: max-age=15552000; includeSubDomains
```

&nbsp;

You can see in Example 8-1 that the response code for the request is 302.  This indicates a redirect to the URL value in the Location header.  Redirects like the one in Example 8-1 can occur with any API call within the Dashboard API, including POST, PUT, and DELETE.  For GET calls, the redirect is specified through a 302 status code, and for any non-GET calls, the redirects are specified with 307 or 308 status codes.  When you specify the **-I** option for **curl**, only the headers of the response are displayed to the user.  At this point, you need to run the **curl** command again but this time specify the resource as https://n149.meraki.com/api/v0/organizations, remove the **-I** flag, and add a n Accept header to specify that the response to the call should be in JSON format.  The command should look like this.

&nbsp;

```
curl -X GET \

  --url 'https://n149.meraki.com/api/v0/organizations' \

  -H 'X-Cisco-Meraki-API-Key:
   15da0c6ffff295f16267f88f98694cf29a86ed87'\

  -H 'Accept: application/json'
```

&nbsp;

The response in this case contains the Id of the DevNet Sandbox organization in JSON format:

&nbsp;

```
[  
    {
        "name": "DevNet Sandbox",
        "id": "549236"
    }
]
```

&nbsp;

Now let's loo at how you can obtain the organization ID for the Cisco DevNet Sandbox Meraki account by using Postman.  As mentioned in Chapter 7, Postman is a popular tool used to explore APIs and create custom requests; it has extensive built-in support for different authentication mechanisms, headers, parameters, collections, environments, and so on.  By default Postman has the Automatically Follow Redirects option enabled in Settings, so you do not have to change the https://api.meraki.com/api/v0/organizations resource as it is already done in the background by Postman.  If you disable the Automatically Follow Redirects option in the Postman settings, you should see exactly the same behavior you just saw with **curl**.  Figure 8-1 shows the Postman client interface with all the fields (the method of the call, the resource URL, and the headers) populated so that the Cisco Meraki REST API returns all the organizations to which this account has access.

&nbsp;

**Figure 8-1** *GET Organization REST API Call in Postman*

>  GET with URL of httpsL//api.meraki.com/api/v0/organizations.  Under the Headers tab there is a Key of Accept with a Value of application/json and a Key of X-Cisco-Meraki-API-Key with a value of 15da0c6ffff295f16267f88f98694cf29a86ed87.

&nbsp;

In the body of the response, you see the same JSON-formatted output as before, with the same organization ID for the DevNet Sandbox account.

&nbsp;

Let's explore the Meraki Dashboard API further and obtain the networks associated with the DevNet Sandbox organization.  If you look up the API documentation at https://developer.cisco.com/meraki/api/#/rest/api-endpoints/networks/get-organization-networks, you see that in order to obtain the networks associated with the specific organization, you need to do a GET request to https://api.meraki.com/api/v0/organizations/{organizationID}/networks, where {organizationId} is the ID you obtained previously, in your first interaction with the Dashboard API.  You have also discovered that the base URL for the DevNet Sandbox organization is https://n149.meraki.com/api/v0.  You can modify the API endpoint with this information to use the following **curl** command:

&nbsp;

```
curl -X GET \

    --url 'https://n149.meraki.com/api/v0/organizations/549236/networks' \

    -H 'X-Cisco-Meraki-API-Key: 15da0c6ffff295f16267f88f98694c
    f29a86ed87' \

    -H 'Accept: application/json'
```

&nbsp;

The response from the API should contain a list of all the networks that are part of the DevNet Sandbox organization and should look similar to the output in Example 8-2.

&nbsp;

**Example 8-2** *List of All the NEtworks in a Specific Organization*

```
[
   {
      "timeZone" : "America/Los_Angeles",
      "tags" : " Sandbox ",
      "organizationId" : "549236",
      "name" : "DevNet Always On Read Only",
      "type" : "combined",
      "disableMyMerakiCom" : false,
      "disableRemoteStatusPage" : true,
      "id" : "L_646829496481099586"
   },
   {
      "organizationId" : "549236",
      "tags" : null,
      "timeZone" : "America/Los_Angeles",
      "id" : "N_646829496481152899",
      "disableRemoteStatusPage" : true,
      "name" : "test - mx65",
      "disableMyMerakiCom" : false,
      "type" : "appliance"
   }, ... omitted output
```

&nbsp;

The output in Example 8-2 shows a list of all networks that are part of the DevNet Sandbox organization with an ID of 549236.  For each network, the output contains the same information found in the Meraki dashboard.  You should make a note of the first network ID returned by the API as you will need it in the next step in your exploration of the Meraki Dashboard API.

&nbsp;

Now you can try to get the same information - a list of all the networks that are part of the DevNet Sandbox organization - by using Postman.  As you've seen, Postman by default does the redirection automatically, so you can specify the API endpoint as https://api.meraki.com/api/v0/organizations/549236/networks.  You need to make sure to specify the GET method, the X-Cisco-Meraki-API-Key header for authentication, and the Accept header, in which you specify that you would like the response from the API to be in JSON format.  Figure 8-2 shows the Postman client interface with all the information needed to obtain a list of all the networks that belong to the organization with ID 549236.

&nbsp;

**Figure 802** *GET Networks REST API Call in Postman*

>  GET https://api.meraki.com/app/v0/organizations/549236/networks with the following headers:  
> - Key: Accept - Value: application/json
> - Key X-Cisco-Meraki-API-Key - Value:  15da0c6ffff295f16267f88f98694cf29a86ed87

&nbsp;

The body of the response contains exactly the same information as before: a complete list of all the networks that are part of the DevNet Sandbox organization.

&nbsp;

Next, you can obtain a list of all devices that are part of the network that has the name "DevNet Always On Read Only" and ID L_646829496481099586.  Much as in the previous steps, you start by checking the API documentations to find the API endpoint that will return this data to you.  The API resource that contains the information you are looking for is /networks/{networkId}/devices, as you can see from the API documentation at the following link:  https://developer.cisco.com/meraki/api/#/rest/api-endpoints/devices/get-network-devices.  You add the base URL from the DevNet Sandbox account, https://n149.meraki.com/api/v0, and populate {networkId} with the value you obtained in the previous step.  Combining all this information, the endpoint that will return the information you are seeking is https://n149.meraki.com/api/v0/networks/L_646829496481099586/devices.  The curl command in this case is as follows:

&nbsp;

```
curl -X GET \

  --url 'https://n149.meraki.com/api/v0/networks/L_646829496481099586/
  devices' \

  -H 'X-Cisco-Meraki-API-Key: 15da0c6ffff295f16267f88f98694cf29a86ed87'\

  -H 'Accept: application/json'
```

&nbsp;

And the response from the API should be similar to the one in Example 8-3.

&nbsp;

**Example 8-3** *Lists of All the Devices in a Specific Network*

```
[
   {
      "wan2Ip" : null,
      "networkId" : "L_646829496481099586",
      "lanIp" : "10.10.10.106",
      "serial" : "QYYY-WWWW-ZZZZ",
      "tags" : " recently-added ",
      "lat" : 37.7703718,
      "lng" : -122.3871248,
      "model" : "MX65",
      "mac" : "e0:55:3d:17:d4:23",
      "wan1Ip" : "10.10.10.106",
      "address" : "500 Terry Francois, San Francisco"
   },
   {
      "switchProfileId" : null,
      "address" : "",
      "lng" : -122.098531723022,
      "model" : "MS220-8P",
      "mac" : "88:15:44:df:f3:af",
      "tags" : " recently-added ",
      "serial" : "QAAA-BBBB-CCCC",
      "networkId" : "L_646829496481099586",
      "lanIp" : "192.168.128.2",
      "lat" : 37.4180951010362
   }
]
```

&nbsp;

Notice from the API response that the "DevNet Always On Read Only" network has two devices: an MX65 security application and an eight-port MS-220 switch.  The output also includes geographic coordinates, MAC addresses, serial numbers, tags, model numbers, and other information.  The same information is available in the Meraki GUI dashboard.

&nbsp;

Following the process used so far, you can obtain the same information but this time using Postman.  Since the redirection is automatically done for you, the API endpoint for Postman is https://api.meraki.com/api/v0/networks/L_646829496481099586/devices.  You populate the two headers Accept and X-Cisco-Meraki-API-Key with their respective values, select the GET method, and click the Send button.  If everything went well, the response code should be 200 OK, and the body of the response should contain exactly the same information found using **curl**.

&nbsp;&nbsp;

So far, you have explored the Meraki Dashboard API using **curl** and Postman.  You first obtained the organization ID of the DevNet Sandbox Meraki account and then, based on that ID, you obtained all the networks that are part of the organization and then used one of the network IDs you obtained to find all of the devices that are a part of that specific network.  This is, of course, just a subset of all the capabilities of the Meraki Dashboard API, and we leave it as an exercise for you to explore in more depth all the capabilities and functionalities of the API.

&nbsp;

As a final step in this section, let's take a look at the Meraki Python SDK.  As of this writing, there are two Meraki SDKs for the Dashboard API: one is Python based and the other is Node.js based.  The Meraki Python SDK used in this book is version 1.0.2; it was developed for Python 3 and implements a complete set of classes, methods, and functions to simplify how users interact with the Dashboard API in Python.

&nbsp;

In order to get access to the SDK, you need to install the meraki-sdk module.  As a best practice, always use virtual environments with all Python projects.  Once a virtual environment is activated, you can run **pip install meraki-sdk** to get the latest version of the SDK.  In this section, you follow the same three steps you have followed in other examples in this chapter:  Get the organization ID for the DevNet Sandbox account, get a list of all the networks that are part of this organization, and all the devices associated to the "DevNet Always on Read Only" network.  The Python 3 code to accomplish these three tasks might look as shown in Example 8-4.

You need to import the MerakiSdkClient class from the meraki_sdk module.  You use the MerakiSdkClient class to create an API client by passing the API key as a parameter and creating an instance of this class called MERAKI.

&nbsp;

**Example 8-4** *Python Script That Uses meraki_sdk*

```python
#! /usr/bin/env python
from meraki_sdk.meraki_sdk_client import MerakiSdkClient

#Cisco DevNet Sandbox Meraki API key
X_CISCO_MERAKI_API_KEY = '15da0c6ffff295f16267f88f98694cf29a86ed87'

#Establish a new client connection to the Meraki REST API
MERAKI = MerakiSdkClient(X_CISCO_MERAKI_API_KEY)

#Get a list of all the organizations for the Cisco DevNet account
ORGS = MERAKI.organizations.get_organizations()

for ORG in ORGS:
    print("Org ID: {} and Org Name: {}".format(ORG['id'], ORG['name']))

PARAMS = {}
PARAMS["organization_id"] = "549236"    # Demo Organization "DevNet Sandbox"

#Get a list of all the networks for the Cisco DevNet organization
NETS = MERAKI.networks.get_organization_networks(PARAMS)
for NET in NETS:
    print("Network ID: {0:20s}, Name: {1:45s},Tags: {2<10s}"\
        .format(NET['id'], NET['name'], str(NET['tags'])))

#Get a list of all the devices that are part of the Always On Network
DEVICES = MERAKI.devices.get_network_devices("L_646829496481099586")
for DEVICE in DEVICES: 
    print("Device Model: {0:9s},Serial: {1:14s},MAC: {2:17}, Firmware:3:12s}"\
        .format(DEVICE['model'], DEVICE['serial'], \
            DEVICE['mac'], DEVICE['firmware']))
```

&nbsp;

After you instantiate the MerakiSdkClient class, you get an API client object that provides access to all the methods of the class.  You can find the documentation for the Python SDK at https://developer.cisco/meraki/api/#/python/guides/python-sdk-quick-start.  This documentation covers all the classes and methods, their parameters, and input and output values for the Python SDK implementation.  Unlike with the **curl** and Postman examples earlier in this chapter, you do not need to determine the exact API resource that will return the information you are interested in; however you do need to know how the MerakiSdkiClient API class is organized and what methods are available.  There's a consistent one-to-one mapping between the Dashboard API and the Python SDK, so when you are familiar with one of them, you should find the other one very easy to understand.  There is also no need to pass the API key through the X-Cisco-Meraki-API-Key header.  This is all automatically handled by the SDK as well as all the redirects that had to manually be changed for the **curl** examples.

&nbsp;

Obtaining the organization ID for the DevNet Sandbox account is as easy as invoking the **organizations.get_organizations()** method of the API client class.  The **ORGS** variable in Example 8-4 contains a list of all the organizations that the DevNet Sandbox account is a member of.  Next, you iterate within a **for** loop through all these organizations and display to the console the organization Id and the organization name.

&nbsp;

Next, you create an empty dictionary called **PARAMS** and add to it a key called organization_id with a value of 549236.  Remember that this was the organization ID for the DevNet Sandbox account.  You still use the Meraki API client instance, but in this case, you invoke the **networks.get_organization_networks()** method.  Just as in the case of the REST API calls with **curl** and Postman earlier in this section, where you had to specify the organization Id when building the endpoint to obtain the list of networks, the get_organization_networks() method takes as input the params dictionary, which contains the same organization ID value but in a Python dictionary format.  The **NETS** variable stores the output of the API call.  In another iterative loop, information about each network is displayed to the console.  

&nbsp;

Finally, you get the list of devices that are part of the networks and have the ID L_646829496481099586.  Recall from earlier that this ID is for the "DevNet Always on Read Only" network.  In this case, you use the **devices.get_network_devices()** method of the Meraki API client instance and store the result in the **DEVICES** variable.  You iterate over the **DEVICES** variable and, for each device in the list, extract and print to the console the device model, the serial number, the MAC address, and the firmware version.

&nbsp;

##  Cisco DNA Center

&nbsp;

Cisco Digital NEtwork Architecture (DNA) is an open, extensible, software-driven architecture from Cisco that accelerates and simplifies enterprise network operations.  Behind this new architecture is the concept of intent-based networking, a new era in networking, in which the network becomes an integral and differentiating part of the business.  With Cisco DNA and the products behind it, network administrators define business intents that get mapped into infrastructure configurations by a central SDN controller.  In the future, an intent-based network will dynamically adjust itself based on what it continuously learns from the traffic it transports as well as the business inputs it gets from the administrator.

&nbsp;

Cisco DNA Center is the network management and command center for Cisco DNA.  With Cisco DNA Center, you can provision and configure network devices in minutes, define a consistent policy throughout a network, get live instantaneous statistics, and get granular networkwide views.  Multidomain and multivendor integrations are all built on top of a secure platform.

&nbsp;

>  ***`Key Topic`***

&nbsp;

From a programmability perspective, Cisco DNA Center provides a set of REST APIs and SDKs through the Cisco DNA Center platform that are grouped in the following categories:

-   Intent API
-   Integration API
-   Multivendor SDK
-   Events and notifications

&nbsp;

The Intent API is a northbound REST API that exposes specific capabilities of the Cisco DNA Center platform.  The main purpose of the Intent API is to simplify the process of creating workflows that consolidate multiple network actions into one.  An example is the SSID provisioning API, which is part of the Intent API.  When configuring an SSID on a wireless network, several operations need to be completed, including creating a wireless interface, adding WLAN settings, and adding security settings.  The SSID provisioning API combines all these operations and makes them available with one API call.  This results in a drastic reduction in overall wireless SSID deployment time and also eliminates errors and ensures a consistent configuration policy.  The Intent API provides automation capabilities and simplified workflows for QoS policy configuration, software image management and operating system updates for all devices in the network, overall client health status, and monitoring of application health.  Application developers and automation engineers can take advantage of this single northbound integration layer to develop tools and applications on top of the network.

&nbsp;

One of the main goals of the Cisco DNA Center platform is to simplify and streamline end-to-end processes.  The Integration API was created for exactly this purpose.  Through this API, Cisco DNA Center platform publishes network data, events, and notifications to external systems and at the same time can consume information from these connected systems.  Integrations with IT service management systems like Service Now, BMC Remedy, and other ticketing systems are supported.  Automatic ticket creation and assignment based on network issues that are flagged by Cisco DNA Center are now possible.  Cisco DNA Center can even suggest remediation steps based on the machine learning algorithms that are part of the assurance capabilities.  You can see how a typical support workflow can be improved with Cisco DNA Center platform in the future.  Cisco DNA Center detects a network issue, automatically creates a ticket and assigns it to the right support personnel, along with a possible solution to the issue.  The support team reviews the ticket and the suggested solution and can approve either immediately or during a maintenance window the remediation of the problem that Cisco DNA Center suggested.  IP Address Management (IPAM) integrations are also supported by the Integration API.  It is possible to seamlessly import IP address pools of information from IPAM systems such as Infoblox and BlueCat into Cisco DNA Center.  Synchronization of IP pool/subpool information between Cisco DNA Center and IPAM systems is also supported.  Through the Integration API that Cisco DNA Center provides, developers can integrate with any third-party IPAM solution.

Data as a service (DaaS) APIs that are part of the Integration API allow Cisco DNA Center to publish insights and data to external tools such as Tableau and similar reporting solutions.  IT administrators have the option to build dashboards and extract business-relevant insights.

The Integration API is also used for cross-domain integrations with other cisco products, such as Cisco Meraki, Cisco Stealthwatch, and Cisco ACI.  The idea is to deliver a consistent intent-based infrastructure across the data center, wan, and security solutions.

&nbsp;

Cisco DNA Center allows customers to have their non-Cisco devices managed by DNA Center through a multivendor SDK.  Cisco DNA Center communicates with third-party devices through device packages.  The device packages are developed using the multivendor SDK and implemented southbound interfaces based on CLI, SNMP, or NETCONF.

Cisco DNA Center also provides webhooks for events and notifications that are generated in the network or on the Cisco DNA Center appliance itself.  You have the option of configuring a receiving URL to which the Cisco DNA Center platform can publish events.  Based on these these events, the listening application can take business actions.  For instance, if some of the devices in a network are out of compliance, the events that the platform generates can be interpreted by a custom application, which might trigger a software upgrade action in Cisco DNA Center.  This completes the feedback loop in the sense that a notification generated by Cisco DNA Center is interpreted by a third-party custom application and acted upon by sending either an Intent API or Integration API call back to Cisco DNA Center to either remedy or modify the network, based on the desired business outcome.  This mechanism of publishing events and notifications also saves on processing time and resources; before this capability existed, the custom application had to poll continuously to get the status of an event.  By subscribing through the webhook, polling can now be avoided entirely, and the custom application receives the status of the event right when it gets triggered.

&nbsp;

Next, let's focus on the Cisco DNA Center Platform Intent API.  As of this writing, the Intent API is organized into several distinct categories:

-   **Know Your Network category**:  This category contains API calls pertaining to sites, networks, devices, and clients:
    -   With the Site Hierarchy Intent API, you can get information about, create, update, and delete sites as well as assign devices to a specific site.  (Sites within Cisco DNA Center are logical groupings of network devices based on geographic location or site.)
    -   The Network Heath Intent API retrieves data regarding network devices, their health, and how they are connected.
    -   The Network Device Detail Intent API retrieves detailed information about devices.  Different parameters can be passed to limit the scope of the information returned by the API, such as timestamp, MAC address, and UUID.  Besides all the detailed information you can retrieve for all the devices in the network, you can also add, delete, update, or sync specified devices.  
    -   The Client Health Intent API returns overall client health information for both wired and wireless clients.
    -   The Client Detail Intent API returns detailed information about a single client.
-   **Site Management category**:  This category helps provision enterprise networks with zero-touch deployments and manage the activation and distribution of software images in the network:
    -   The Site Profile Intent API gives you the option to provision NFV and ENCS devices as well as retrieve the status of the provisioning activities.
    -   The Software Image Management (SWIM) API enables you to completely manage the lifecycle of software images running within a network in an automated fashion.  With this API, you can retrieve information about available software images, import images into Cisco DNA Center, distribute images to devices, and activate software images that have been deployed to devices.
    -   The Plug and Play (PnP) API enables you to manage all PnP-related workflows.  With this API, you can create, update, and delete PnP workflows and PnP server profiles, claim and unclaim devices, add and remote virtual accounts, and retrieve information about all PnP-related tasks.
-   **Connectivity category**:  This category contains APIs that provide mechanisms to configure and manage both non-fabric wireless and Cisco SDA wired fabric devices.  For fabric devices, you can add and remove border devices to the fabric and get details about their status.  For non-fabric wireless devices, you can create, update, and delete wireless SSIDs, profiles, and provisioning activities.
-   **Operational Tools category**:  This category includes APIs for the most commonly used tools in the Cisco DNA Center toolbelt:
    -   The Command Runner API enables the retrieval of all valid keywords that Command Runner accepts and allows you to run read-only commands on devices to get their real-time configuration.
    -   The Network Discovery API provides access to the discovery functionalities of Cisco DNA Center.  You can use this API to create, update, delete, and manage network discoveries and the credentials needed for them.  You can also retrieve network discoveries, network devices that were discovered as part of a specific network discovery task, and credentials associated with these discoveries.
    -   The Temple Programmer API can be used to manage configuration templates.  You can create , view, edit, delete, version, add commands, check contents for errors, deploy, and check the status of template deployments.
    -   The Path Trace API provides access to the Path Trace application in Cisco DNA Center.  Path Trace can be used to troubleshoot and trace application paths throughout the network and provide statistics at each hop.  The API gives you access to initiating,retrieving, and deleting path traces.
    -   The File API enables you to retrieve files such as digital certificates, maps, and SWIM files fromm Cisco DNA Center.
    -   The Task API provides information about the network action that are being run asynchronously.  Each of the se background actions can take from seconds to minutes to complete, and each has a task associated with it.  You can query the Task API about the completion status of these tasks, get the task tree, retrieve tasks by their IDs, and so on.
    -   The Tag API gives you the option of creating, updating, and deleting tags as well as assigning tags to specific devices.  Tags are very useful in Cisco DNA Center; they are used extensively to group devices by different criteria.  You can then apply policies and provision and filter these groups of devices.

&nbsp;

The Cisco DNA Center platform APIs are rate limited to five API requests per minute.

&nbsp;

So in this section, we've covered all the APIs and the multivendor SDK offered by Cisco DNA Center.  Next, we will start exploring the Intent API, using Cisco DNA Center version 1.3 for the rest of the chapter.  As API resources and endpoints exposed by the Cisco DNA Center platform might change in future versions of the software, it is always best to start exploring the API documentation for any Cisco product at https://developer.cisco.com/docs/dna-center/api/1-3-0-x/.

&nbsp;

In Cisco DNA Center version 1.3, the REST API is not enabled by default.  Therefore, you need to log in to DNA Center with a super-admin role account, navigate to Platform > MAnagement > Bundles, and enable the DNA Center REST API bundle.  The status of the bundle should be active.

&nbsp;

For this section, you can use the always-on DevNet Sandbox for Cisco DNA Center at https://sandboxdnac2.cisco.com.  The username for this sandbox is **devnetuser**, and the password is **Cisco123!**.  You need to get authorized to the API and get the token that you will use for all subsequent API calls.  The Cisco DNA Center platform API authorization is based on basic auth.  Basic auth, as you learned in Chapter 7, is an authorization type that requires a username and password to access an API endpoint.  In the case of Cisco DNA Center, the username and password mentioned previously are base-64 encoded and then transmitted to the API service in the Authorization header.  There are many online services that can do both encoding and decoding of base-64 data for you, or as a fun challenge you can look up how to do it manually.  The username **devnetuser** and the password **Cisco123!** become **ZGV2- bmV0dXNlcjpDaXNjbzEyMyE=** when they are base-64 encoded.  The only missing component is the resource that you need to send the authorization request to.  You verify the documentation and see that the authorization resource is /system/api/v1/auth/token and requires the API call to be POST.  With this information, you can build the authorization, you can build the authorization API endpoint, which becomes http://sandboxdnac2.cisco.com/system/api/v1/auth/token.

&nbsp;

Next, you will use **curl**, a command-line tool that is useful in testing REST APIs and web services.  Armed with the authorization API endpoint, the Authorization header containing the base-64-encoded username and password, and the fact that hte API call needs to be a POST call, you can now craft the authorization request in **curl**.  The authorization API call with **curl** should look as follows:

&nbsp;

```
curl -X POST \
    https://sandboxdnac2.cisco.com/dna/system/api/v1/auth/token \
    -H 'Authorization: Basic ZGV2- bmV0dXNlcjpDaXNjbzEyMyE=
```

&nbsp;

The result should be JSON formatted with the key Token and a value containing the actual authorization token.  It should look similar to th following:

&nbsp;

```
{"Token":"eyJ0eXAiOiJKV1QiLCJhbGciOiJIUzI1NiJ9.eyJzdWIiOiI1Y2U3M-
TJiMDhlZTY2MjAyZmEyZWI4ZjgiLCJhdXRoU291cmNlIjoiaW50ZXJuYWwiL-
CJ0ZW5hbnROYW1lIjoiVE5UMCIsInJvbGVzIjpbIjViNmNmZGZmNDMwOTkwM-
DA4OWYwZmYzNyJdLCJ0ZW5hbnRJZCI6IjViNmNmZGZjNDMwOTkwMDA4OWYwZ-
mYzMCIsImV4cCI6MTU2NjU0Mzk3OCwidXNlcm5hbWUiOiJkZXZuZXR1c2VyIn0.
Qv6vU6d1tqFGx9GETj6SlDa8Ts6uJNk9624onLSNSnU"}
```

&nbsp;

Next, you can obtain an authorization token by using Postman.  Make sure you select POST as the verb for the authorization API call and the endpoint https://sandboxdnac2.cisco.com/dna/system/api/v1/auth/token.  This is a POST call because you are creating new data in the system - in this case, a new authorization token.  Under the Authorization tab, select Basic Auth as the type of authorization, and in the Username and Password fields, make sure you have the correct credentials (devnetuser and Cisco123!).  Since you have selected basic auth as the authorization type, Postman does the base-64 encoding for you automatically.  All you need to do is click Send, and the  authorization API call is sent to the specified URL.  If the call is successfully completed, the status code should be 200 OK, and the body of the response should be JSON-formatted token key and the corresponding value.

&nbsp;

The body of the response for the Postman request should look as follows:

&nbsp;

```json
{

    "Token":

"eyJ0eXAiOiJKV1QiLCJhbGciOiJIUzI1NiJ9.eyJzdWIiOiI1Y2U3MTJiMDhlZ-
TY2MjAyZmEyZWI4ZjgiLCJhdXRoU291cmNlIjoiaW50ZXJuYWwiLCJ0ZW5hbnROY-
W1lIjoiVE5UMCIsInJvbGVzIjpbIjViNmNmZGZmNDMwOTkwMDA4OWYwZmYzNyJdL-
CJ0ZW5hbnRJZCI6IjViNmNmZGZjNDMwOTkwMDA4OWYwZmYzMCIsImV4cCI6MTU2N-
jU5NzE4OCwidXNlcm5hbWUiOiJkZXZuZXR1c2VyIn0.ubXSmZYrI-yoCWmzCSY486y-
HWhwdTlnrrWqYip5lv6Y"

}
```

&nbsp;

As with the earlier **curl** example, this token will be used in all subsequent API calls and performed in the rest of this chapter.  The token will be passed in the API calls through a header that is called **X-Auth-Token**.

&nbsp;

Let's now get a list of all the network devices that are being managed by the instance of Cisco DNA Center that is running in the always-on DevNet Sandbox you've just authorized with.  If you verify with the Cisco DNA Center API documentation on https://developer.cisco.com/docs/dna-center/api/1-3-0-x/, you can see that the API resource that will return a complete list of all network devices managed by Cisco DNA Center is /dna/intent/api/v1/network-device.

&nbsp;

With all this information in mind, you can craft the **curl** request to obtain a list of all the network devices managed by the Cisco DevNet always-on DNA Center Sandbox.  The complete URL is https://sandboxdnac2.cisco.com/dna/intent/api/v1/network-device.  You need to retrieve the information through the API, so we need to do a GET request; don't forget the X-Auth-Token header containing the authorization token.  The **curl** command should look as follows, and it should contain a valid token:

&nbsp;

```
curl -X GET \

  https://sandboxdnac2.cisco.com/dna/intent/api/v1/network-device \

  -H 'X-Auth-Token: eyJ0eXAiOiJKV1QiLCJhbGciOiJIUzI1NiJ9.
  eyJzdWIiOiI1Y2U3MTJiMDhlZTY2MjAyZmEyZWI4ZjgiLCJhdXRoU291c-
  mNlIjoiaW50ZXJuYWwiLCJ0ZW5hbnROYW1lIjoiVE5UMCIsInJvbGVzIjpbI-
  jViNmNmZGZmNDMwOTkwMDA4OWYwZmYzNyJdLCJ0ZW5hbnRJZCI6IjViNmNmZG-
  ZjNDMwOTkwMDA4OWYwZmYzMCIsImV4cCI6MTU2NjYwODAxMSwidXNlcm5hbWUiOi-
  JkZXZuZXR1c2VyIn0.YXc_2o8FDzSQ1YBhUxUIoxwzYXXWYeNJRkB0oKBlIHI'

```

&nbsp;

The response of this **curl** command should look as shown in Example 8-5.

&nbsp;

**Example 8-5** *List of Network Devices Managed by the Always-On Cisco DNA Center Sandbox Instance*
```
{
   "response" : [
       {
         "type" : "Cisco 3504 Wireless LAN Controller",
         "roleSource" : "AUTO",
         "apManagerInterfaceIp" : "",
         "lastUpdateTime" : 1566603156991,
         "inventoryStatusDetail" : "<status><general code=\"SUCCESS\"/></status>",
         "collectionStatus" : "Managed",
         "serialNumber" : "FCW2218M0B1",
         "location" : null,
         "waasDeviceMode" : null,
         "tunnelUdpPort" : "16666",
         "reachabilityStatus" : "Reachable",
         "lastUpdated" : "2019-08-23 23:32:36",
         "tagCount" : "0",
         "series" : "Cisco 3500 Series Wireless LAN Controller",
         "snmpLocation" : "",
         "upTime" : "158 days, 13:59:36.00",
         "lineCardId" : null,
         "id" : "50c96308-84b5-43dc-ad68-cda146d80290",
         "reachabilityFailureReason" : "",
         "lineCardCount" : null,
         "managementIpAddress" : "10.10.20.51",
         "memorySize" : "3735302144",
         "errorDescription" : null,
         "snmpContact" : "",
         "family" : "Wireless Controller",
         "platformId" : "AIR-CT3504-K9",
         "role" : "ACCESS",
         "softwareVersion" : "8.5.140.0",
         "hostname" : "3504_WLC",
         "collectionInterval" : "Global Default",
         "bootDateTime" : "2019-01-19 02:33:05",
         "instanceTenantId" : "SYS0",
         "macAddress" : "50:61:bf:57:2f:00",
         "errorCode" : null,
         "locationName" : null,
         "softwareType" : "Cisco Controller",
         "associatedWlcIp" : "",
         "instanceUuid" : "50c96308-84b5-43dc-ad68-cda146d80290",
         "interfaceCount" : "8"
      },
      ... omitted output
   ],
   "version" : "1.0"
```

&nbsp;

From this verbose response, you can extract some very important information about the network devices managed by Cisco DNA Center.  The date returned in the response is too verbose to fully include in the previous output, so just a snippet is included for your reference.  As of this writing, in the complete response output, you can see that there are 14 devices in this network.

&nbsp;

-   One AIR-CT3504-K9 wireless LAN controller
-   One WS-C3850-24P-L Catalyst 3850 switch
-   Two C9300-48U Catalyst 9300 switches
-   Ten AIR-AP141N-A-K9 wireless access points

&nbsp;

For each device, you can see extensive information such as the hostname, uptime, serial number, software version, management interface IP address, reachability status, hardware platform, and role in the network.  You can see here the power of the Cisco DNA Center platform APIs.  With one API call, you were able to get a complete status of all devices in the network.  Without a central controller like Cisco DNA Center, it would have taken several hours to connect to each device individually and run a series of commands to obtain the same information that was returned with one API call in less than half a second.  These APIs can save vast amounts of time and bring numerous possibilities in terms of infrastructure automation.  The data returned by the API endpoints can be extremely large, and it might take a long time to process a request and return a complete response.  As mentioned in Chapter 7, pagination is an API feature that allows for passing in parameters to limit the scope of the request.  Depending on the Cisco DNA Center platform API request, different filter criteria can be considered, such ass management IP address, MAC address, and hostname.

&nbsp;

Now you will see how to obtain the same information you just got with **curl** but now using Postman.  the same API endpoint URL is used: https://sandboxdnac3.cisco.com/dna/intent/api/v1/network-device.  In this case, it is a GET request, and the X-Auth-Token header is specified under the Headers tab and populated with a valid token.  If you click Send and there aren't any mistakes with the request, the status code should be 200 OK, and the body of the response should be very similar to that obtained with the **curl** request.

&nbsp;

Now you can try to obtain some data about the clients that are connected to the network managed by Cisco DNA Center.  Much like network devices, network clients have associated health scores, provided through the Assurance feature to get a quick overview of client network health.  This score is based on several factors, including onboarding time, association time, SNR (sign-to-noise ratio), and RSSI (received signal strength indicator) values for wireless clients, authentication time, connectivity and traffic patterns, and number of DNS requests and responses.  In the API documentation, you can see that the resource providing the health status of all clients connected to the network is /dna/intent/api/v1/client-health.  This API call requires a parameter to be specified when performing the call.  This parameter, called timestamp, represents the UNIX epoch time in milliseconds.  UNIX epoch time is a system for describing a point in time since January 1, 1970, not counting leap seconds.  It is extensively used in UNIX and many other operating systems.  The timestamp provides the point in time for which the client health information should be returned in the API response.  For example, if I retrieved the health status of all the clients connected to the network on Thursday, August 22, 2019 8:41:29 PM GMT, the UNIX time, in milliseconds, would be 15665064890000.  Keep in mind that based on teh data retention policy set in Cisco DNA Center, client data might not be available for past distant timeframes. 

&nbsp;

With the information you now have, you can build the API endpoint to process the API call: https://sandboxdnac2.cisco.com/dna/intent/api/v1/client-health?timestamp=15665064890000.  The authorization token also needs to be included in the call as a value in the X-Auth-Token header.  The **curl** command should look as follows:

&nbsp;

```
curl -X GET \

    https://sandboxdnac2.cisco.com/dna/intent/api/v1/client-health?timestamp=1566506489000 \ 

    -H 'X-Auth-Token: eyJ0eXAiOiJKV1QiLCJhbGciOiJIUzI1NiJ9.
    eyJzdWIiOiI1Y2U3MTJiMDhlZTY2MjAyZmEyZWI4ZjgiLCJhdXRoU291c
    mNlIjoiaW50ZXJuYWwiLCJ0ZW5hbnROYW1lIjoiVE5UMCIsInJvbGVzIjpbI
    jViNmNmZGZmNDMwOTkwMDA4OWYwZmYzNyJdLCJ0ZW5hbnRJZCI6IjViNmNmZG-
    ZjNDMwOTkwMDA4OWYwZmYzMCIsImV4cCI6MTU2NjYxODkyOCwidXNlcm5hbWUiO
    iJkZXZuZXR1c2VyIn0.7JNXdgSMi3Bju8v8QU_L5nmBKYOTivinAjP8ALT_opw'
```

&nbsp;

The API should look similar to Example 8-6 (shown later).

&nbsp;

From this response, you can see that there are a total of 82 clients in the network, and the average health score for all of them is 27.  To further investigate why the health scores for some of the clients vary, you cna look into the response to the /dna/intent/api/v1/client-detail call.  This API call takes as input parameters the timestamp and the MAC address of the client, and it returns extensive data about the status and health of that specific client at the specific time.

&nbsp;

Now you can try to perform the same API call but this time with Postman.  The API endpoint stays the same:  https://sandboxdnac2.cisco.com/dna/intent/api/v1/client-health?timestamp=15665064890000.  In this case, you are trying to retrieve information from the API, so it will be a GET call, and the X-Auth-Token header contains a valid token value.  Notice that the Params section of Postman gets automatically populated with a timestamp key, with the value specified in the URL: 15665064890000.  Click Send, and if there aren't any errors with the API call, the body of the response should be very similar to the one obtained previously with **curl**.

&nbsp;

**Example 8-6** *List of Clients and Their Status*
```
{
  "response" : [ {
    "siteId" : "global",
    "scoreDetail" : [ {
      "scoreCategory" : {
        "scoreCategory" : "CLIENT_TYPE",
        "value" : "ALL"
      },
      "scoreValue" : 27,
      "clientCount" : 82,
      "clientUniqueCount" : 82,
      "starttime" : 1566506189000,
      "endtime" : 1566506489000,
      "scoreList" : [ ]
    }, ... output omitted
}
```

&nbsp;

So far in this section, you've explored the Cisco DNA Center platform API and seen how to authorize the API calls and obtain a token, how to get a list of all the devices in the network, and how to get health statistics for the clients in the network using both **curl** and Postman.  Next let's explore the Cisco DNA Center Python SDK.  The SDK has been developed for Python 3 and maps all the Cisco DNA Center APIs into Python classes and methods to make it easier for developers to integrate with and expand the functionality of Cisco DNA Center.  Installing the SDK is as simple as issuing the command **pip install dnacentersdk** from the command prompt.  At the time of this writing, the current Cisco DNA Center SDK version is 1.3.0.  The code in Example 8-7 was developed using this version of the SDK to first authorize the API and then retrieve a list of all the network devices and client health statuses.

&nbsp;

```python
#! /usr/bin/env python
from dnacentersdk import api

# Create a DNACenterAPI connection object;
# it uses DNA Center sandbox URL, username and password
DNAC = api.DNACenterAPI(username="devnetuser",
           password="Cisco123!",
           base_url="https://sandboxdnac2.cisco.com")

# Find all devices
DEVICES = DNAC.devices.get_device_list()

# Print select information about the retrieved devices
print('{0:25s}{1:1}{2:45s}{3:1}{4:15s}'.format("Device Name", "|", \
    "Device Type", "|", "Up Time"))
print('-'*95)
for DEVICE in DEVICES.response:
    print('{0:25s}{1:1}{2:45s}{3:1}{4:15s}'.format(DEVICE.hostname, \
        "|", DEVICE.type, "|", DEVICE.upTime))
print('-'*95)

# Get the health of all clients on Thursday, August 22, 2019 8:41:29 PM GMT
CLIENTS = DNAC.clients.get_overall_client_health(timestamp="1566506489000")

# Print select information about the retrieved client health statistics
print('{0:25s}{1:1}{2:45s}{3:1}{4:15s}'.format("Client Category", "|",\
    "Number of Clients", "|", "Clients Score"))
print('-'*95)
for CLIENT in CLIENTS.response:
    for score in CLIENT.scoreDetail:
        print('{0:25s}{1:1}{2:<45d}{3:1}{4:<15d}'.format(
            score.scoreCategory.value, "|", score.clientCount, "|", \
            score.scoreValue))
print('-'*95)
```

&nbsp;

First, this example imports the **api** class from **dnacentersdk**.  Next, it instantiates the **api** class and creates a connection ot the always-on Cisco DevNet Sandbox DNA Center instance and stores the result of that connection in a variable called ***DNAC***.  If the connection was successfully established, the **DNAC** object has all the API endpoints mapped to the methods that are available for consumption.  DNAC.**devices.get_device_list()** provides a list of all the devices in the network and stores the result in the **DEVICES** dictionary.  The same logic applies to the client health status.  **DNAC.clients.get_overall_client_health(timestamp='1566506489000')** returns a dictionary of health statuses for all the clients at the specific time, which translates to Thursday, August 22, 2019 8:41:20 PM GMT.  When the data is extracted from the API and stored in the variables named **DEVICES** for all the network devices and CLIENTS for all the client health statuses, a rudimentary table is displayed in the console, with select information from both dictionaries.  For the **DEVICES** variable, only the device name, device type, and device uptime are displayed, and for the **CLIENTS** variable, only the client health category, number of clients, and client score for each category as displayed.

&nbsp;

##  Cisco SD-WAN

&nbsp;

Cisco SD-WAN (Software-DEfined Wide Area Network) is a cloud-first architecture for deploying WAN connectivity.  Wide-area networks have been deployed for a long time, and many lessons and best practices have been elarned throughout the years.  Applying all these lessons to software-defined networking (SDN) resulted in the creation of Cisco SD-WAN.  An important feature of SDN is the separation of the control plane from the data plane.

&nbsp;

The control plane includes a set of protocols and features that a network device implements so that it can determine which network path to use to forward data traffic.  Spanning tree protocols and routing protocols such as OSPF (Open Shortest Path First), EIGRP (Enhanced Interior Gateway Routing Protocol), and BGP (Border Gateway Protocol) are some of the protocols that make up the control plane in network devices.  These protocols help build the switching or routing tables in network devices to enable them to determine how to forward network traffic.

&nbsp;

The data plane includes the protocols and features that a network device implements to forward traffic to its destination as quickly as possible.  Cisco Express Forward (CEF) is a proprietary switching mechanism that is part of the data plane.  It was developed specifically to increase the speed with which data traffic is forwarded through network devices.  You can read more about the control and data planes in Chapter 17, "Networking Components."

&nbsp;

Historically, the control plane and data plane were part of the network device architecture, and they worked together to determine the path that the data traffic should take through the network and how to move this traffic as fast as possible from its source to its destination.  As mentioned previously, software-defined networking (SDN) suggests a different approach.

&nbsp;

SDM separates the functionality of the control plane and data plane in different devices, and several benefits result.  First, the cost of the resulting network should be lower as not all network devices have to implement expensive software and hardware features to accommodate both a control plane and data plane.  The expensive intelligence from the control plane is constrained to a few devices that become the brains of the network, and the data plane is built with cheaper devices that implement only fast forwarding.  Second, the convergence of this new network, which is the amount of time it takes for all devices to agree on a consistent view of the network, should be much lower than in the case of the non-SDN architectures of the past.  In networks of similar sizes, the ones built with network devices that implement both the control plane and the data plane in their architecture take much longer to exchange all thet information needed to forward data traffic than do the networks that implement separate control and data plane functionality in their architecture.  Depending on the size of a network, this could mean waiting for thousands of devices to exchange information through their control plane protocols and settle on a certain view of the network or wait for tens of SDN controllers to accomplish the same task; the convergence time improvements are massive.

&nbsp;

Cisco currently has two SD-WAN offerings.  The first one, based on the Viptela acquisition, is called Cisco SD-WAN; the second one, based on the Meraki acquisition is called Meraki SD-WAN.  We already covered Cisco Meraki at the beginning of this chapter; this section covers Cisco SD-WAN based on the Viptela acquisition.

&nbsp;

You've already seen some of the advantages that SDN brings to WAN connectivity.  Based on this new architecture and paradigm, the Cisco SD-WAN offering contains several products that perform different functions:

&nbsp;

>  ***`Key Topic`***

&nbsp;

-	**vManage**:  Cisco vManage is a centralized network management system that provides a GUI and REST API interface to the SD-WAN fabric.  You can easily manage, monitor, and configure all Cisco SD-WAN component through this single pane of glass.
-	**vSmart**:  Cisco vSmart is the brains of the centralized control plane for the overlay SD-WAN network.  It maintains a centralized routing table and centralized routing policy that it propagates to all the network Edge devices through permanent DTLS tunnels.
-	**vBond**:  Cisco vBond is the orchestrator of the fabric.  It authenticates the vSmart controllers and the vEdge devices and coordinates connectivity between them.  The vBond orchestrator is the only component in the SD-WAN fabric that needs public IP reachability to ensure that all devices can connect to it.
-	**vEdge**:  Cisco vEdge routers, as the name implies, are Edge devices that are located at the perimeter of the fabric, such as in remote offices, data center, branches, and campuses.  They represent the data plane and bring the whole fabric together and route traffic to and from their site across the overlay network.

&nbsp;

All the components of the Cisco SD-WAN fabric run as virtual appliances, and the vEdges are also available as hardware routers.

&nbsp;

Separating the WAN fabric this way makes it more scalable, faster to converge, and cheaper to deploy and maintain.  On top of a transport-independent underlay that supports all types of WAN circuits (MPLS, DSL, broadband, 4G, and so on), an overlay network is being built that runs OMP (Overlay Management Protocol).  Much like BGP, OMP propagates throughout the network all the routing information needed for all the components of the fabric to be able to forward data according to the routing policies configured in vManage.

&nbsp;

Cisco vManage provides a REST API that exposes the functionality of the Cisco SD-WAN software and hardware features.  The API resources that are available through the REST interface are grouped in the following collections:

-	**Administration**:  For management of users, groups, and local vManage instance
-	**Certificate Management**:  For management of SSL certificates and security keys
-	**Configuration**:  For creation of feature and device configuration templates and creation and configuration of vManage cluster
-	**Device Inventory**:  For collecting device inventory information including system status
-	**Monitoring**:  For getting access to status, statistics, and related operational information about all the devices in the network every 10 minutes from all devices
-	**Real-Time Monitoring**:  For gathering real-time monitoring statistics and traffic information approximately once per second
-	**Troubleshooting Tools**:  For API calls used in troubleshooting, such as to determine the effects of applying a traffic policy, updating software, or retrieving software version information

&nbsp;

Cisco vManage exposes a self-documenting web interface for the REST API, based on the OpenAPI specification.  This web interface is enabled by default and can be access https://vManage_IP_or_hostname:port/apidocs.  vManage_IP_or_hostname is the IP address or hostname of the Cisco vManage sever, and the port is 8443 by default.  The rest of this chapter uses the always-on Cisco DevNet SD-WAN Sandbox, available at https://sandboxsdwan.cisco.com.  The username for this vManage server is devnetuser, and the password is Cisco123!.  At this writing, this sandbox is running Cisco SD-WAN version 18.3 for all components of the fabric.  Because this sandbox will be updated in time, or you might be using a different version, you should check https://developer.cisco.com for the latest information on all Cisco REST APIs documentation and changes.

&nbsp;

The web interface displays a list of all the REST API resources available, the methods associated with each one of them, and the model schema of the responses.  The option of trying out each API call and exploring the returned data is also available.

&nbsp;

Let's explore the Cisco vManage REST API next.  The API documentation can be found at https://sdwan-docs.cisco.com/Product_Documentation/Command_Reference/Command_Reference/vManage_REST_APIs. At this link, you can find all the information needed on how to interact with the REST API, all the resources available, and extensive explanations.

&nbsp;

You need to establish a connection to the Cisco vManage instance.  The initial connection is established through an authorization request to https://sandboxsdwan.cisco.com:8443/j_security_check.  The information sent over this POST call is URL form encoded and contains the username and password mentioned previously.  The **curl** request for this authorization request should look as follows:

&nbsp;

```
curl -c - -X POST -k \
  https://sandboxsdwan.cisco.com:8443/j_security_check \
  -H 'Content-Type: application/x-www-form-urlencoded' \
  -d 'j_username=devnetuser&j_password=Cisco123!'
```

&nbsp;

The **-c -** option passed to the **curl** request specifies that the returned authorization cookie should be printed to the console.  The **-k** option bypasses SSL certificate verification as the certificate for this sandbox is self-signed.  The output of the command should look as follows:

&nbsp;

```
# Netscape HTTP Cookie File

# https://curl.haxx.se/docs/http-cookies.html

# This file was generated by libcurl! Edit at your own risk.

#HttpOnly_sandboxsdwan.cisco.com.  FALSE  /  TRUE  0   JSESSIONID.
v9QcTVL_ZBdIQZRsI2V95vBi7Bz47IMxRY3XAYA6.4854266f-a8ad-4068-9651-
d4e834384f51
```

&nbsp;

The long string after JESSIONID is the value of the authorization cookie that will be needed in all subsequent API calls.

&nbsp;

The same API call can be made in Postman.  The status code of the response should be 200 OK, the body should be empty, and the JSESSIONID cookie should be stored under the Cookies tab.  The advantage with Postman is that it automatically saves the JSESSIONID cookie and reuses it in all API calls that follow this initial authorization request.  With **curl**, in contrast, you have to pass in the cookie value manually.  To see an example, you can try to get a list of all the devices that are part of this Cisco SD-WAN fabric.  According to the documentation, the resource that will return this information is /dataservice/device.  It will have to be a GET call, and the JSESSIONID cookie needs to be passed as a header in the request.  The **curl** command to get a list of all the devices in the fabric should look as follows:

&nbsp;

```
curl -X GET -k \

  https://sandboxsdwan.cisco.com:8443/dataservice/device \  

  -H 'Cookie: JSESSIONID=v9QcTVL_ZBdIQZRsI2V95vBi7Bz47IMxRY3XAYA6.4
  854266f-a8ad-4068-9651-d4e834384f51'
```

&nbsp;

The response from the always-on Cisco DevNet vManage server should look similar to the one in Example 8-8

&nbsp;

**Example 8-8** *List of Devices That Are Part of the Cisco SD-WAN Fabric*

```
{
   ... omitted output
 
   "data" : [
      {
         "state" : "green",
         "local-system-ip" : "4.4.4.90",
         "status" : "normal",
         "latitude" : "37.666684",
         "version" : "18.3.1.1",
         "model_sku" : "None",
         "connectedVManages" : [
            "\"4.4.4.90\""
         ],
         "statusOrder" : 4,
         "uuid" : "4854266f-a8ad-4068-9651-d4e834384f51",
         "deviceId" : "4.4.4.90",
         "reachability" : "reachable",
         "device-groups" : [
            "\"No groups\""
         ],
         "total_cpu_count" : "2",
         "certificate-validity" : "Valid",
         "board-serial" : "01",
         "platform" : "x86_64",
         "device-os" : "next",
         "timezone" : "UTC",
         "uptime-date" : 1567111260000,
         "host-name" : "vmanage",
         "device-type" : "vmanage",
         "personality" : "vmanage",
         "domain-id" : "0",
         "isDeviceGeoData" : false,
         "lastupdated" : 1567470387553,
         "site-id" : "100",
         "controlConnections" : "5",
         "device-model" : "vmanage",
         "system-ip" : "4.4.4.90",
         "validity" : "valid",
         "system-ip" : "4.4.4.90",
         "state_description" : "All daemons up",
         "max-controllers" : "0",
         "layoutLevel" : 1,
         "longitude" : "-122.777023"
      },
      ... omitted output
   ]
}
```

&nbsp;

The output of this GET API call is too verbose to be fully displayed.  We encourage you to explore this API call and observe the full response on your own computer.

&nbsp;

The body of the response is in JSON format and contains information about all the devices in the SD-WAN fabric.  As of this writing, this specific fabric contains the following:

- One Cisco vManage server
- One Cisco vSmart server
- One Cisco vBond server
- Four Cisco vEdge routers

&nbsp;

For each device, the response includes status, geographic coordinates, role, device ID, uptime, site ID, SSL certificate status, and more.  You can build the same request in Postman and send it to vManage.  The body of the response is very similar to the one received from the **curl** command.

&nbsp;

While exploring the Cisco SD-WAN REST API, let's get a list of all the device templates that are configured on the Cisco DevNet vManage server.  According to the API documentation, the resource that will return this information is /dataservice/template/.  You pass in the JSESSIONID value in the cookie header and build the following **curl** command:

&nbsp;

```
curl -X GET -k \

   https://sandboxsdwan.cisco.com:8443/dataservice/template/device  \  

   -H 'Cookie: JSESSIONID=v9QcTVL_ZBdIQZRsI2V95vBi7Bz47IMxRY3XAYA6.48
   54266f-a8ad-4068-9651-d4e834384f51'
```

&nbsp;

The response from the vManage server at https://sandboxsdwan.cisco.com should look as shown in Example 8-9

&nbsp;

**Example 8-9** *List of Device Configuration Templates*

```
{
   "data" : [
      {
         "templateDescription" : "VEDGE BASIC TEMPLATE01",
         "lastUpdatedOn" : 1538865915509,
         "templateAttached" : 15,
         "deviceType" : "vedge-cloud",
         "templateId" : "72babaf2-68b6-4176-92d5-fa8de58e19d8",
         "configType" : "template",
         "devicesAttached" : 0,
         "factoryDefault" : false,
         "templateName" : "VEDGE_BASIC_TEMPLATE",
         "lastUpdatedBy" : "admin"
      }
   ],
... output omitted
}
```


&nbsp;

The response contains details about the only device template available on this vManage server.  The template is called VEDGE_BASIC_TEMPLATE, it is of type vedge-cloud (which means it can be applied to vEdge devices), and it currently has no devices attached to it.  

&nbsp;

The same information is returned by vManage when using Postman to get the list of all device templates.  As before, the JSESSIONID cookie is already included with Postman and does not need to be specified again.

&nbsp;

Next, let's use Python to build a script that will go through the same steps:  Log in to vManage, get a list of all the devices in the SD-WAN fabric, and get a list of all device templates available.  No SDK will be used in this case; this will help you see the difference between this code and the Python code you used earlier in this chapter.  Since no SDK will be used, all the API resources, payloads, and handling of data will have to be managed individually.

&nbsp;

The Python **requests** library will be used extensively in this sample code.  You should be familiar with this library from Chapter 7.  Example 8-10 shows a possible version of the Python 3 script that accomplishes these tasks.  The script was developed using Python 3.7.4 and version 2.22.0 of the requests library.  The **json** library that comes with Python 3.7.4 was also used to deserialize and load the data returned from the REST API into a Python object; in this case, that object is a list.  In this code, first the **import** keyword makes the two libraries **requests** and **json** available for use within the script.  Since the connection in the script is made to an instance of vManage that is in a sandbox environment and that uses a self-signed SSL certificate, the third and fourth lines of the script disable the warning messages that are generated from the **requests** library when connecting to REST API endpoints that are secured with self-signed SSL certificates.  Next, the script specifies the vManage hostname and the username and password for this instance; this example uses the same vManage server used earlier in this chapter.  The code then specifies the base URL for the vManage REST API endpoint: https://sandboxsdwan.cisco.com:8443.  the code shows the authentication resource (j_security_check) and the login credentials, and then the login URL is built as a combination of the base URL and the authentication API resource.  In the next line, a new **request** session instance is created and stored in the SESS variable.

&nbsp;

**Example 8-10** *Python Script Showcasing How to Interact with the Cisco SD-WAN REST API*

```python
#! /usr/bin/env python
import json
import requests
from requests.packages.urllib3.exceptions import InsecureRequestWarning
requests.packages.urllib3.disable_warnings(InsecureRequestWarning)

# Specify Cisco vManage IP, username and password
VMANAGE_IP = 'sandboxsdwan.cisco.com'
USERNAME = 'devnetuser'
PASSWORD = 'Cisco123!'

BASE_URL_STR = 'https://{}:8443/'.format(VMANAGE_IP)

# Login API resource and login credentials
LOGIN_ACTION = 'j_security_check'
LOGIN_DATA = {'j_username' : USERNAME, 'j_password' : PASSWORD}
# URL for posting login data
LOGIN_URL = BASE_URL_STR + LOGIN_ACTION

# Establish a new session and connect to Cisco vManage
SESS = requests.session()
LOGIN_RESPONSE = SESS.post(url=LOGIN_URL, data=LOGIN_DATA, verify=False)

# Get list of devices that are part of the fabric and display them
DEVICE_RESOURCE = 'dataservice/device'
# URL for device API resource
DEVICE_URL = BASE_URL_STR + DEVICE_RESOURCE

DEVICE_RESPONSE = SESS.get(DEVICE_URL, verify=False)
DEVICE_ITEMS = json.loads(DEVICE_RESPONSE.content)['data']

print('{0:20s}{1:1}{2:12s}{3:1}{4:36s}{5:1}{6:16s}{7:1}{8:7s}'\
    .format("Host-Name", "|", "Device Model", "|", "Device ID", \
        "|", "System IP", "|", "Site ID"))
print('-'*105)

for ITEM in DEVICE_ITEMS:
    print('{0:20s}{1:1}{2:12s}{3:1}{4:36s}{5:1}{6:16s}{7:1}{8:7s}'\
        .format(ITEM['host-name'], "|", ITEM['device-model'], "|", \
             ITEM['uuid'], "|", ITEM['system-ip'], "|", ITEM['site-id']))
print('-'*105)
# Get list of device templates and display them
TEMPLATE_RESOURCE = 'dataservice/template/device'
# URL for device template API resource
TEMPLATE_URL = BASE_URL_STR + TEMPLATE_RESOURCE

TEMPLATE_RESPONSE = SESS.get(TEMPLATE_URL, verify=False)
TEMPLATE_ITEMS = json.loads(TEMPLATE_RESPONSE.content)['data']

print('{0:20s}{1:1}{2:12s}{3:1}{4:36s}{5:1}{6:16s}{7:1}{8:7s}'\
    .format("Template Name", "|", "Device Model", "|", "Template ID", \
        "|", "Attached devices", "|", "Template Version"))
print('-'*105)

for ITEM in TEMPLATE_ITEMS:
    print('{0:20s}{1:1}{2:12s}{3:1}{4:36s}{5:1}{6:<16d}{7:1}{8:<7d}'\
        .format(ITEM['templateName'], "|", ITEM['deviceType'], "|", \
            ITEM['templateId'], "|"" ITEM['devicesAttached'], "|", \
                ITEM['templateAttached']))
 print('-'*105)
```

&nbsp;

Using this new session, a POST request is sent to the login URL, containing the username and password as payload and disabling the SSL certificate authenticity verification by specifying verify=False.  At this point, a session is established to the DevNet Sandbox vManage instance.  This session can be used to interact wit the vManage REST API by getting, creating, and modifying and deleting data.

&nbsp;

The code specifies the APi resource that iwll return a list of all the devices in the SD-WAN fabric: dataservice/device.  The complete URL to retrieve the devices in teh fabric is built on the next line by combining the base URL with the new resource.  The DEVICE_URL variable will look like https://sandboxsdwan.cisco.com:8443/dataservice/device.  Next, the same session that was established earlier is used to perform a GET request to the device_url resource.  The result of this request is stored in the variable aptly named **DEVICE_RESPONSE**, which contains the same JSON-formatted data that was obtained in the previously **curl** and Postman request, with extensive information about all the devices that are part of the SD-WAN fabric.  From that JSON data, only the list of devices that are values of the **data** key are extracted and stored in the **DEVICE_ITEMS** variable.

&nbsp;

Next, the header of a rudimentary table is created.  This header contains the fields Host-Name, Device Model, Device ID, System IP, and Site ID.  From the extensive list of information contained in the **DEVICE_ITEM** variable, only these five fields will be extracted and displayed to the console for each device in the fabric.  The code next prints a series of delimiting dashes to the console to increase the readability of the rudimentary table.  The next line of code has a **for** loop that is used to iterate over each element of the**DEVIEC_ITEMS** list and extract the hostname, device model, device ID, system IP address, and site ID for each device in the fabric and then display that information to the code.  The code then prints a series of dashes for readability purposes.  Next, the same logic is applied to GET data from the API but this time about all the device templates that are configured on this instance of vManage.  The URL is built by concatenating the base URL with the device template resources, dataservice/template/device.  The same session is reused once more to obtain the data from the REST API.  In the case of the device templates, only the template name, the type of device the template is intended for, the template ID, the number of attached devices to each template, and the template version are extracted and displayed to the console.

&nbsp;

If you run this script in Python 3.7.4 virtual environment with the **requests** library version 2.22.0 installed, you get output similar to that shown in Figure 8-15.