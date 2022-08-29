#  Application Programming Interfaces (APIs)

##  "Do I Know This Already?" Quiz

&nbsp;

-   Which of the following is a sample use case of a southbound API?
    -   Pushing network configuration changes down to devices
    -   Increasing security
    -   Streaming telemetry
    -   Sending information to the cloud

&nbsp;

-   What are some benefits of using asynchronous APIs?  (Choose two.)
    -   Not having to wait on a response to process data
    -   Reduce processing time
    -   Increased processing time
    -   Data function reuse

&nbsp;

-   What are the HTTP functions used for API communication?  (Choose three.)
    -   GET
    -   SOURCE
    -   PURGE
    -   PATCH
    -   PUT

&nbsp;

-   True or false:  RESTful API authentication can use API keys or custom tokens.
    -   True
    -   False

&nbsp;

-   What dose SOAP stand for?
    -   Software Operations and Procedures
    -   Software Operations Authentication Protocol
    -   Simple Object Access Protocol
    -   Simple Operations Automation Platform
    -   Support Object Abstract Protocol

&nbsp;

-   What are the main components of SOAP messages?  (Choose all that apply.)
    -   Envelope
    -   Header
    -   Destination
    -   Body
    -   Fault
    -   Authentication
    -   Source

&nbsp;

-   Remote-procedure calls (RPCs) behave similarly to which of the following?
    -   Synchronous API
    -   Asynchronous API

&nbsp;

## Application Programming Interfaces (APIs)

&nbsp;

For communicating with and configuring networks, software developers commonly use application programming interfaces (APIs).  APIs are mechanisms used to communicate with applications and other software.  They are also used to communicate with various components of a network through software.  A developer can use APIs to configure or monitor specific components of a network.  Although there are multiple different types of APIs, this chapter focuses on two of the most common APIs: northbound and southbound APIs.  The following sections explain the differences between these two APIs types through the lens of network automation.

&nbsp;

> ***Personal Notes**:  Essentially, **Applications** is at the top, **Controller** is in the middle, and **Data Plane** is at the bottom.  The **Northbound API** connects the **Applications** and **Controller**, and the **Southbound API** connects the **Controller** with the **Data Plane**.*

&nbsp;

###  **Northbound APIs**

&nbsp;

Northbound APIs are often used for communication from a network controller to its management software.  For example, Cisco DNA Center has a software graphical user interface (GUI) that is used to manage its own network controller.  Typically, when a network operator logs into a controller to manage the network, the information that is passed to the management software leverages a northbound REST-based API.  Best practices suggest that the traffic should be encrypted using TLS between the software and the controller.  Most types of APIs have the ability to use encryption to secure the data in flight.

&nbsp;

> **Note**:  RESTful APIs are covered in an upcoming section of this chapter and in depth in Chapter 7, "RESTful API Requests and Responses."

&nbsp;

###  **Southbound APIs**

&nbsp;

If a network operator makes a change to a switch's configuration in the management software of the controller, those changes will then be pushed down to the individual devices using a southbound API.  These devices can be routers, switch, or even wireless access points.  APIs interact with the components of a network through the use of a programming interface.  Southbound APIs can modify more than just the data plane on a device.

&nbsp;

> ***Key Topic***

&nbsp;

### Synchronous Versus Asynchronous APIs**

&nbsp;

APIs can handle transactions either in a synchronous manner or an asynchronous manner.  A **synchronous API** causes an application to wait for a response from the API in order to continue processing data or function normally.  This can lead to interruptions in application processing or delay in response or failed responses could cause the application to hang or stop performing the way it was intended to work.  This might occur, for example, if an application relies on some piece of information to be retrieved from another API before it can continue functioning.  For example, uploading videos to YouTube was originally a synchronous use case.  While the videos were uploading, users couldn't use the rest of the GUI or change the names of the videos or make other changes.  Users had to wait until the process completed prior to doing any other work within the YouTube application.

&nbsp;

>  ***Personal Note**:  The client makes an API call.  It sends the request to the server which is waiting for a request.  The server receives the request and begins to execute procedure.  It then sends the response to the client which is waiting for a reply, and the client then resumes execution while the server waits for the next request.*

&nbsp;

**Asynchronous APIs** do exactly the opposite of synchronous APIs in that they do not wait until a response is received prior to continuing to function and process other aspects of data.  Asynchronous APIs provide a callback function so that the API response can be sent back at another time, without the application having to wait for the entire transaction to complete.  As an example of an asynchronous API, today you can upload a video to YouTube, and while it's uploading, users can change the title, add hashtags, and even retrieve the URL to which the video will be posted once it is finished being uploaded.

&nbsp;

In summary, the main difference between synchronous and asynchronous APIs is that a synchronous API waits for other aspects of the code to complete prior to moving on and processing additional code.  An asynchronous API, on the other hand, provides the ability to continue processing code and provides a callback so that an application doesn't have to wait for the API call to complete before it can continue processing other API calls.  An asynchronous API provides a better user experience as the users do not have to wait on certain aspects of information to be received prior to being able to use the application for other things.

&nbsp;

> ***Personal Note**:  Client uses an API call to send a request to the server.  The server receives the request and begin to execute procedure.  During this time the client is continuing to function.  The server sends the response.  The client receives the response via callback and continues execution.

&nbsp;

###  **Representational State Transfer (REST) APIs**

&nbsp;

An API that uses REST is often referred to as a RESTful API.  RESTful APIs use HTTP methods to gather and manipulate data.  Because there is a defined structure for how HTTP works, HTTP offers a consistent way to interact with APIs from multiple vendors.  REST uses different HTTP functions to interact with data.  The table below (Table 6-2 HTTP Functions and Sample Use Cases) will list some of the most common HTTP functions and their associated use cases.

&nbsp;

HTTP functions are very similar to the functions that most applications and databases use to store or alter data, whether it is stored in a database or within an application.  These functions are called CRUD functions; CRUD is an acronym that stands for CREATE, READ, UPDATE, and DELETE.  For example, in an SQL database, the CRUD functions are used to interact with or manipulate the data stored in teh database.  Table 6-3 lists the CRUD functions and their associated actions and use cases.

&nbsp;

>  ***Key Topic***

&nbsp;

**Table 6-2** HTTP Functions and Sample Use Cases

| HTTP Function | Action | Use Case |
| -- | -- | -- |
| GET | Request data from a destination | Viewing a website |
| POST | Submits data to a specific destination | Submitting login credentials |
| PUT | Replaces data at a specific destination | Updating an NTP server |
| PATCH | Appends data to a specific destination | Adding an NTP server |
| DELETE | Removes data from a specific destination | Removing an NTP server |

&nbsp;

> ***Key Topic***

&nbsp;

**Table 6-3** CRUD Functions and Sample Use Cases

| CRUD Function | Action | Use Cases |
| -- | -- | -- |
| CREATE | Inserts data inside a database or an application | Creating a customer's home address in a database | 
| READ | Retrieves data from a database or an application | Pulling up a customer's home address from a database | 
| UPDATE | Modifies or replaces data in a database or an application | Changing a street address stored in a database |
| DELETE | Removes data from a database or an application | Removing a customer from a database |

&nbsp;

Whether you are trying to learn how APIs interact with applications or controllers, test code and outcomes, or become a full-time developer, one of the most important pieces of interacting with any software via APIs is testing.  Testing code helps ensure that developers are accomplishing the desired outcome.  This chapter covers some tools and resources that make it possible to practice using APIs and REST functions and hone your development skills in order to become a more efficient network engineer with coding skills.

&nbsp;

> **Note**:  Chapter 7 provides more detail on HTTP and CRUD functions as well as response codes.

&nbsp;

> ***Key Topic***

&nbsp;

### **RESTful API Authentication**

&nbsp;

As mentioned earlier in this chapter, it is important to be able to interact with a software controller using RESTful APIs and to be able to test code to see if the desired outcomes are accomplished when executing the code.  Keep in mind that APIs are software interfaces into an application or a controller.  Many APIs require authentication; such APIs are just like devices in that the user needs to authenticate to gain access to utilize the APIs.  Once a user has authenticated, any changes that a developer has access to make via the API are then able to impact the application.  This means if a RESTful API call is used to delete data, that data will be removed from the application or controller just as if a user were logged into the device via the CLI and deleted it.  It is best practice to use a test lab or a Cisco DevNet sandbox while learning or practicing API concepts to prevent accidental impacts in a production or lab environment.

&nbsp;

>  **Note**:  Cisco DevNet is covered in Chapter 1, "Introduction to Cisco DevNet Associate Certification."

&nbsp;

### **Basic Authentication**

Basic authentication, explained below (Figure 6-4), is one of the simplest and most common authentication methods used in APIs.  The downfall of basic authentication is that the credentials are passed unencrypted.  This means that if the transport is simple HTTP, it is possible to sniff the traffic and capture the username and password with little to no effort.  The lack of encryption means that the credentials are in simple plaintext base 64 encoding in the HTTP header.  However, basic authentication is more commonly used with SSL or TLS to prevent such attacks.

&nbsp;

**Figure 6-4** Basic Authentication Example

> ***Personal Note***:  Client sends GET /home to web service (server).  Server responds with 401 Unauthorized WWW-AuthenticatE: Basic Realm="localhost".  Client replies with GET /home Authorization:  Basic WYpxUY26bPEcs1dQef=.  The server then sends a 200 ok.

&nbsp;

Another big issue with basic authentication is that the password is sent back and forth with each request, which increases the opportunity for an attacker to capture the traffic containing the password.  This is yet another reason to use encryption on this type of transaction.

&nbsp;

###  **API Keys**

&nbsp;

Some APIs use API keys for authentication.  An **API key** is a predetermined string that is passed from the client to the server.  It is intended to be a pre-shared secret and should not be well known or easy to guess because it functions just like a password.  Anyone with this key can access the API in question and can potentially cause a major outage and gain access to critical or sensitive data.  An API key can be passed to the server in three different ways:

-   String
-   Request header
-   Cookie

&nbsp;

Example 6-1 provides an example of a string based API key.  this type of API key is sent with  every APi call and is often used as a one-off method of authentication.  When you're looking to do multiple API calls, it isn't convenient to manually enter the API key string every time.  This is where the request header or cookie options come into play.

&nbsp;

**Example 6-1** *String Based API Key Example*

```
GET /something?api_key=abcdef12345
```

&nbsp;

Request headers are frequently used when a user is making multiple API calls and doesn't want to keep having to put the API key into each API individually.  This approach is typically seen in Postman and Python scripts.  The header must include the string or token in the header of each API call.  Example 6-2 shows the request header option for API key authentication

&nbsp;

**Example 6-2** *Request Header API Key Example*
```
GET /something HTTP/1.1
X-API-Key: abcdef12345
```

&nbsp;

Finally, one of the most common methods for recurring API calls is to use cookies.  A cookie stores the API key string and can be reused and stored over and over.  This is synonymous with a header.  Example 6-3 shows an API key cookie that uses the same key as the previous example.

&nbsp;

Example 6-3 Cookie API Key Example
```
GET /something HTTP/1.1
Cookie: X-API-KEY=abcdef12345
```

&nbsp;

>  **Note**:  Later chapters provide detailed examples of the authentication methods introduced in this chapter.

&nbsp;

### **Custom Tokens**

&nbsp;

A custom **token** allows a user to enter his or her username and password once and then receive a unique auto-generated and encrypted token.  The user can then use this token to access protected pages or resources instead of having to continuously enter the login credentials.  Tokens can be time bound and set to expire after a specific amount of time has passed, thus forcing users to reauthenticate by reentering their credentials.  A token is designed to show proof that a user has previously authenticated.  It simplifies the login process and reduces the number of times a user has to provide login credentials.  A token is stored in the user's browser and gets checked each time the user tries to access information requiring authentication.  Once the user logs out of the web browser or website, the token is destroyed so it cannot be compromised.  Figure 6-6 provides an overview of token based authentication between a client and a server.

&nbsp;

**Figure 6-5** *Token-Based Authentication Example*

>  ***Personal Note**:  REST Client sends HTTP Request to get access token (username, password).  The REST API Authenticates the user (or sends a HTTP Error Code 401 (Unauthorized User) to generate access and refresh tokens.  The REST API then sends a HTTP 200 OK access and refresh tokens.  The client replies with All HTTP actions with the request for access to the resource (access token).  The REST API will validate the access token and reply with either HTTP Error Code 401 (Unauthorized User) or Appropriate HTTP Response give access to resource.  In case the access token expires:  The client sends a HTTP POST to generate new access token (access and refresh token), the APi then validates the access and refreshes the token. 

&nbsp;

###  **Simple Object Access Protocol** 

&nbsp;

>  ***Key Topic***

&nbsp;

Simple Object Access Protocol (SOAP) is used to access web services.  Although HTTP is the most commonly deployed transports for SOAP, SOAP can use either Simple Mail Transfer Protocol (SMTP), or HTTP.  SOAP is used to exchange data between applications that were built on different programming languages, such as Java,. NET, and PHP.  SOAP greatly simplifies the life of a developer, eliminating the need to know how to develop in each of these specific programming languages.  It makes it possible to exchange data between these applications in a more simplified manner, without requiring a developer to be an expert in all the different languages.  SOAP is based on XML.  Because most programming languages today have libraries for working with XML, SOAP can act as an intermediary specification between the different applications.

&nbsp;

SOAP uses XML to communicate between web services and clients.  Because SOAP is platform and operating system independent, it can work with both Windows and Linux platforms.  SOAP messages, which typically consist of the following four main components, are sent between the web applications and clients (see Figure 6-6):

-   Envelope
-   Header
-   Body
-   Fault (optional)

&nbsp;

**Figure 6-6** *SOAP Message Format*

>  ***Personal Note**:  Soap Envelope has the following blow blocks inside of it:  SOAP Header and SOAP Body.  Inside of the SOAP Header block there are multiple other Header Blocks.  Inside of the SOAP Body, there is a Message block.*

&nbsp;

The SOAP envelope encloses the XML data and identifies it as a SOAP message.  The envelope indicates the beginning and the end of the SOAP message.  The next portion of a SOAP message is the SOAP header, and it can contain multiple header blocks.  Header blocks are targeted to specific SOAP receiver nodes.  If a SOAP message containers a header, it must come before the body element.  The SOAP body contains the actual message that is designated for the SOAP receiver.  Every SOAP envelope must contain at least one body element.  Typically, SOAP messages are automatically generated by the web service when it's called by the client.  Figure 6-7 illustrates the high-level communication that occurs between a client and a server or web service.

&nbsp;

**Figure 6-7** *High-Level SOAP Communication*


>  ***Personal Note**:  Client sends HTTP POST (Request) to Web Service (Server).  The Client also sends the HTTP Body (SOAP Envelope).  The Server then sends back the HTTP Response (Header) and the HTTP Body (SOAP Envelope).

&nbsp;

Another potentially beneficial aspect of SOAP is that because it primarily uses HTTP, it is efficient in passing through firewalls without requiring that any additional ports be allowed or open for the web service traffic to be permitted.  This can save time and reduce some operational overhead.  To reiterate, the benefit of SOAP is it s capability to work between different languages while using a simple common HTTP and XML structure.  Example 6-4 shows a sample SOAP message that is being used to leverage an HTTP GET to retrieve the price for Cisco's stock, using the ticker symbol CSCO.

&nbsp;

**Example 6-4** *Sample SOAP Message*

```
POST /InStock HTTP/1.1
Host:  www.example.com
Content-Type:  application/soap+xml; charset=utf-8
Content-Length:  299
SOAPAction:  "http://www.w3.org/2003/05/soap-envelope"

<?xml version="1.0"?>
<soap:Envelope xmlns:soap="http://www.w3.org/2003/05/soap-envelope" xmlns:m="http://www.example.org">
    <soap:Header>
    </soap:Header>
    <soap:Body>
        <m:GetStockPrice>
            <m:StockName>CSCO</m:StockName>
        </m:GetStockPrice>
    </soap:Body>
</soap:Envelope>
```

&nbsp;

The World Wide Web Consortium (W3C) recommends using the current SOAP specifications, versions 1.2.  The previous version of SOAP is 1.1.  Although it is possible for a SOAP node to support both versions of the protocol, a protocol binding must be used for the version of SOAP that the client intends to use.  

&nbsp;

As mentioned briefly at the beginning of this section, SOAP can include optional fault messages.  Table 6-4 lists the options that are available for the optional fault messages as well as which of them are options.

&nbsp;

**Table 6-4** SOAP Fault Options

| SOAP Fault Code | Description |
| -- | -- |
| VersionMismatch | The faulting node found an invalid element information item instead of the expected envelope element information item.  The namespace, local name, or both did not match the envelope element information item required by this recommendation. |
| MustUnderstand | This is a child element of the SOAP header.  If this attribute is set, any information that was not understood triggers this fault code. |
| DataEncodingUnknown | A SOAP header block or SOAP body child element information item targeted at the faulting SOAP node is scoped. |
| Sender | The message was incorrectly formed or did not contain the information needed to succeed.  For example, the message might have lacked the proper authentication or payment information.  This code generally indicates that the message is not to be resent without change. |
| Receiver | The message could not be processed for reasons attributable to the processing of the message rather than to the contents of the message itself.  For example, processing could include communicating with an upstream SOAP node, which did not respond.  The message could succeed, however, if resent at a later point in time. |

&nbsp;

The fault message shown in Example 6-5 was generated because the Detail value wasn't interpreted correctly due to the type in the XML `<m:MaxTime>P5M</m:MaxTime>`.  The value P5M caused the issue in this case because the code was expecting it to be 5PM.  the XML code and value should be `<m:MaxTime>5PM</m:MaxTime>` in this case.

&nbsp;

**Example 6-5** *Sample SOAP Fault*
```
<env:Envelope xmlns:env="http://www.w3.org/2003.05/soap-envelope"
    xmlns:m="http://www.example.org/timeouts"
    xmlns:xml="http://www.w3.org/XML/1998/namespace">
    <env:Body>
        <env:Fault>
            <env:Code>
                <env:Value>end:Sender</env:value>
                <env:Subcode>
                    <env:Value>m:MessageTimeout</env:Value>
                </env:Subcode>
            </env:Code>
            <env:Reason>
                <env:Text xml:lang="en">Sender Timeout</env:Text>
            </env:Reason>
            <env:Detail>
                <m:MaxTime>P5M</m:MaxTime>
            </env:Detail>
        </env:Fault>
    </env:Body>
</env:Envelope>
```

&nbsp;

>  **Note**:  The examples used in this chapter are all based on SOAP version 1.2.

&nbsp;

### Remote-Procedure Calls (RPCs)

&nbsp;

Remote-procedure calls (RPCs) make it possible to execute code or a program on a remote node in a network.  RPCs behave as if the code were executed locally on the same local node, even though the code is executed on a remote address space, such as another system on the network.  Most remote and local calls are very similar in nature and can be distinguished from one another based on whether they are local or remote.  RPCs are sometimes also known as function or subroutine calls.  Using an RPC is a very common way of executing specific commands, such as executing GET or POST operations to a set API or URL.

&nbsp;

When a client sends a request message, the RPC translates it and then sends it to the server.  A request may be a procedure or a function call destined to a remote server.  When a server receives the request, it sends back a response to the client.  While this communications is happening, the client is blocked, allowing the server time to process the call.  Once the call is processed and a response has been sent back to the client, the communication between the client and server is unblocked so the client can resume executing the procedure call.  This can be considered a security mechanism to prevent the flooding of RPCs to brute-force the server and cause denial-of-service (DoS) attacks or exhaustion fo resources.  Figure 6-8 showcases the high-level RPC communications between a client and a server.

&nbsp;

**Figure 6-9** *High-Level RPC Communications*

> ***Personal Note**:  The client executes a call procedure which then sends a RPC Call (Request) to the Server.  The server which was waiting for a request receives the request and begins to execute the procedure.  The client waits for a reply.  The Server then sends a response which is a RPC Call (Response) - result of procedure execution.  The Client then resumes the execution while the server waits for the next request.

&nbsp;

As mentioned earlier in this section, an RPC call is blocked during the waiting periods.  Once a procedure is executed and the response is sent from the server and received on the client, the execution of the procedure continues.  (This means that RPC calls are typically synchronous.  There are also asynchronous RPC calls, but the focus of this section is on synchronous RPC calls.)

&nbsp;

Now that the high-level communications of RPC have been covered, let's look at an example of an RPC request message.  There are different versions of RPC messages.  However, the most common is XML-RPC; XML-RPC was also the most common version prior to SOAP becoming.  Example 6-6 shows a simple RPC call with XML-RPC that uses a GET to retrieve the name of the 21st sate added to the Untied States.

&nbsp;

**Example 6-6** *Sample XML-RPC Request Message*
```
<?xm version=1.0"?>
<methodCall>
    <methodName>example.getStateName</methodName>
    <params>
        <param>
            <value><i4>21</i4></value>
        </param>
    </params>
</methodCall>
```

&nbsp;

You can see in the Example 6-6 that the format of XML is very similar to that of SOAP, making these messages simples for humans to read and digest and also to build.  Example 6-7 shows an example of an XML-RPC reply or response message, in which the response to the GET message from Example 6-6 is Illinois.

&nbsp;

**Example 6-7** *Sample XML-RPC Reply Message*

```
<?xml version=1.0"?>
<methodResponse>
    <params>
        <param>
            <value><string>Illinois</string></value>
        </param>
    </params>
</methodResponse>