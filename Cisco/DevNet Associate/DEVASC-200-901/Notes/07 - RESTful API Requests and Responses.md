#  RESTful API Requests and Responses

&nbsp;

##  "Do I Know This Already?" Quiz

&nbsp;

-   In HTTP, in order to make a successful GET request to the server, the client needs to include at least which of the following?  (Choose two.)
    -   URL
    -   Method
    -   Headers
    -   Body

&nbsp;

-   Which of the following is not an HTTP method?
    -   GET
    -   HEAD
    -   TRIGGER
    -   PATCH

&nbsp;

-   Webhooks are like which of the following?  (Choose two.)
    -   Remote procedure calls
    -   Callback functions
    -   State-altering functions
    -   Event-triggered notifications

&nbsp;

-   Which response code indicates that a resource has moved?
    -   201
    -   301
    -   401
    -   501

&nbsp;

-   Which of the following model the interactions between various objects in a single use case?
    -   REST APIs
    -   Sequence diagrams
    -   Excel sheets
    -   Venn diagrams

&nbsp;

-   Which REST API architectural constraint allows you to download code and execute it?
    -   Client/server
    -   Stateless
    -   Code on demand
    -   Layered systems

&nbsp;

-   Rate limiting is an essential REST API design method for developers.  Rate-limiting techniques are used to ______.
    -   increase security
    -   have business impact
    -   enhance efficiency end to end
    -   do all the above

&nbsp;

-   To add HTTP headers to a Python request, you can simply pass them in as which of the following?
    -   list
    -   dict
    -   tuple
    -   set

&nbsp;

##  RESTful API Fundamentals

&nbsp;

*An **application programming interface** (API) is a set of functions and procedures intended to be used as an interface for software components to communicate with each other.*  An API may be for a web app, an operating system, a database system, computer hardware, or any software library.  A common example of an API is the Google Maps API, which lets you interface with Google Maps so that you can display maps in your application, query locations, and so on.  Figure 7-1 shows a simple way to visualize an API.

&nbsp;

**Figure 7-1** *APIs are a contract between two communicating applications.*

> ***Personal Notes**:  App1 sends a REQUEST of "Get Me Some Information, Please." to App2.  App2 sends a RESPONSE of "Here's the information."*

&nbsp;

The follow sections look at the different API types.

&nbsp;

### **API Types**

&nbsp;

APIs can be broadly classified into three categories, based on the type of work that each one provides:

&nbsp;

-   **Service API**:  In a service API, an application can call on another application to solve a particular problem (see Figure 7-2).  Usually these systems can exist independently.  For example, in a payment system, an application cal call the API to accept payments via credit cards.  As another example, with a user-management system, an application can call an API to validate and authenticate users.

&nbsp;

**Figure 7-2** *Service API Providing a Complete Service to the Calling Application*

> ***Personal Note**:  App1 sends a REQUEST "Solve or Execute This Task for Me".  Service sends a RESPONSE back saying "Done!  Here's the Info About the Task"*
> - Payment Systems
> - User Management
> - Social Media Handler*

&nbsp;

-   **Information API**:  An information API allows one application to ask another application for information.  *Information* in this context can refer to data gathered over time, telemetry data, or a list of devices that are currently connected.  Figure 7-3 provides a visual representation of an information API.

&nbsp;

Figure 7-3 *Information API Providing Information or Analysis of Data That Has Been Collected*

>  ***Personal Note**:  App1 sends a REQUEST of "Get Me the Current Information" to the Information Store.  Information Store sends a RESPONSE of "Done!  Here's the Info You Asked For".*
> - Analytics
> - Device List
> - Time Series Data

&nbsp;

-   Hardware API:  Application developers use hardware APIs to gain access to the features of hardware devices.  Usually these APIs encompass some kind of hardware or sensors, and an application can call this kind of API to get the GPS location or real-time sensor data such as temperature or humidity.  Figure 7-4 provides a visual representation of what a hardware API does.

&nbsp;

Figure 7-4 Hardware API Providing Access to Hardware in Order to Get or Set Data

>  ***Personal Note**:  App1 sends REQUEST of "Get Me the Current Location of the Vehicle" to Hardware.  Hardware sends RESPONSE of 40.689263   -74.044505.*
> - Sensor Data
> - Real-Time Hardware Status
> - Device Management

&nbsp;

### **API Access Types**

&nbsp;

There are typically three ways APIs can be accessed:

-   Private:  A private API is for internal use only.  This access type gives a company the most control over its API.
-   Partner:  A partner API is shared with specific business partners.  This can provide additional revenue streams without compromising security.
-   Public:  A public API is available to everyone.  This allows third parties to develop applications that interact with an API and can be a source for innovation.

&nbsp;

Regardless of how they are accessed, APIs are designed to interact through a network.  Because the most widely used communications network is the Internet, most APIs are designed based on web standards.  Not all remote APIs are web APIs, but it's fair to assume that web APIs are remote.

&nbsp;

Thanks to the ubiquity of HTTP on the web, most developers have adopted it as the protocol underlying their APIs.  The greatest benefit of using HTTP is that it reduces the learning curve for developers, which encourages use of an API.  HTTP has several features that are useful in building a good API, which will be apparent as we start exploring the basics in the next section.

&nbsp;

### **HTTP Basics**

&nbsp;

A web browser is a classic example of an HTTP client.  Communication in HTTP centers around a concept called the request/response cycle, in which the client sends the server a request to do something.  The server, in turn, sends the client a response saying whether or not the server can do what the client asked.  Figure 7-5 provides a very simple illustration of how a client requests data from a server and how the server responds to the client.

&nbsp;

**Figure 7-5** *Simple HTTP Request/Response Cycle*

>  ***Personal Note**:  The Client block has a Request and a Response block above and below it respectively.  The top Client Request block sends a REQUEST of "Send Me the Home Page for the Site" to the Web Server.  The Web Server receives the Request and Responds with Information.  The Web Server sends "Here's the \<HTML> Page You Request" in the RESPONSE".*

&nbsp;

Now let's look at a request from the HTTP point of view, where the client (web browser) makes a request (GET /index.html) to the server (developer.cisco.com).  The server eventually responds to the client with the actual HTML page, which then gets rendered by the browser.  Figure 7-6 provides a very simple representation of how a client sends a GET request requesting the page from the server and how the server responds with the HTML page to the client.

&nbsp;

Figure 7-6 Simple HTTP GET Request with 200 OK Response

>  ***Personal Note**:  Client sends a **REQUEST GET /index.html HTTP 1.1** to the Web Server.  The Web Server receives the request and responds with information.  The Web Server sends a **RESPONSE 200 OK** to the Client.*

&nbsp;

In HTTP, in order to make a successful request to the server, the client needs to include four items:

-   URL (uniform resource locator)
-   Method
-   List of headers
-   Body

The following sections looks at each of these items in detail.

&nbsp;

### **Uniform Resource Locator (URL)**

&nbsp;

A URL is similar to a house address in that it defines the location where a service resides on the internet.  A URL typically has four components, as shown in Figure 7-7.

&nbsp;

>  ***Key Topic***

&nbsp;

-   Protocol
-   Server/host address
-   Resource
-   Parameters

&nbsp;

**Figure 7-7** *Anatomy of an HTTP URL*

>  ***Personal Note**:  http://myhouse.cisco.com/api/room/livingroom/lights?state=ON*
> - **Protocol**:  http (Not Secure) or https (Secure)
> - **Server**:  IP Address or Hostname to Connect to (myhouse.cisco.com)
> - **Resource**:  Location of the Data or Object on the Server (api/room/livingroom/)
> - **Parameters**:  Details to Scope, Filter, or Clarify the Request (lights?state=ON)

&nbsp;

These four components are shown in Figure 7-7.  

As you can see, the server or host address is the unique server name, api/rooms/livingroom defines a resource to access, and lights?state=ON is the parameter to send in order to take some action.

&nbsp;

###  **Method**

&nbsp;

HTTP defines a set of request methods, outlined in Table 7-2.  A client can use one of these request methods to send a request message to an HTTP server.

&nbsp;

>  ***Key Topic***

&nbsp;

**Table 7-2** Request Methods

&nbsp;

| Method | Explanation |
| -- | -- |
| GET | A client can use a GET request to get a web resource from the server. |
| HEAD | A client can use a HEAD request to get the header that a GET request would have obtained.  Because the header contains the last-modified date of the data, it can be used to check against the local cache copy. |
| POST | A client can use a POST request to post data or add new data to the server. |
| PUT | A client can use a PUT request to ask a server to store or update data. |
| PATCH | A client can use a PATCH request to ask a server to partially store or update data. |
| DELETE | A client can use a DELETE request to ask a server to delete data. |
| TRACE | A client can use a TRACE request to ask a server to return a diagnostic trace of the actions it takes. |
| OPTIONS | A client can use an OPTIONS request to ask a server to return a list of the request methods it supports. |
| CONNECT | A client cna use a CONNECT request to tell a proxy to make a connection to another host and simply reply with the content, without attempting to parse or cache it.  This request is often used to make SSL connection through the proxy. |

&nbsp;

###  **REST Methods and CRUD**

&nbsp;

As you have seen, REST is an architectural paradigm that allows developers to build RESTful services.  These RESTful applications make use of HTTP requests for handling all four CRUD operations:  CREATE, READ, UPDATE, and DELETE.  These four operations are the operations most commonly used in manipulating data.  The HTTP methods map in a one-to-one way to the CRUD operations, as show in Table 7-3.

&nbsp;

**Table 7-3** Mapping HTTP Methods to CRUD Operations

| HTTP Method | Operation | Explanation |
| -- | -- | -- |
| POST | CREATE | Used to create a new object or resource.  <br/>  Example:  Add new room to a house. |
| GET | READ | Used to retrieve resource details from the system.  <br/>  Example:  Get a list of all the rooms or all the details of one room. |
| PUT | UPDATE | Typically used to replace or update a resource.  Can be used to modify or create a resource.  <br/>  Example:  Update details of a room. |
| PATCH | UPDATE | Used to modify some details about a resource.  <br/>  Example:  Change the dimensions of a room. |
| DELETE | DELETE | Used to remove a resource from the system.  <br/>  Example:  Delete a room from a house. |

&nbsp;

###  **Deep Dive into GET and POST**

&nbsp;

GET is the most common HTTP request method.  A client can use the GET request method to request (or "get") a resource from an HTTP server.  GET requests, which have special qualities, fetch information, and that's it; they have no side effects, make no modifications ot the system, create nothing, and destroy nothing.  GET requests should, in other words, be safe and idempotent.  (Idempotent means that no matter how many times you perform an action, the state of the system you're dealing with remains the same.)

&nbsp;

A GET request message has the following components, as shown in Figure 7-8.

&nbsp;

**Figure 7-8** *Syntax of a GET Request*

> GET &nbsp;&nbsp;&nbsp; | &nbsp;&nbsp;&nbsp; Request URI &nbsp;&nbsp;&nbsp; | &nbsp;&nbsp;&nbsp; HTTP Version
> <br/>
> __
> <br/>
> Request Header (Optional)
> <br/>
> __
> <br/>
> Request Body (Optional)

&nbsp;

-   **GET**:  The keyword GET must be all uppercase.
-   **Request URI**:  Specifies the path of the resource requested, which must begin from the root / of the document base directory.
-   **HTTP version**:  Either HTTP/1.0 or HTTP/1.1.  This client negotiates the protocol to be used for the current session.  For example, the client may request to use HTTP/1.1.  If the server does not support HTTP/1.1, it may inform the client in the response to use HTTP/1.0.
-   **Request headers (optional)**:  The client can use optional request headers (such as accept and accept language) to negotiate with the server and ask the server to deliver the preferred contents (such as in the language the client prefers).
-   **Request body (optional)**:  A GET request message has an optional request body, which containers the query string (explained later in this chapter).

&nbsp;

The POST request method is used to post additional data to the server (for example, submitting HTML form data or uploading a file).  Issuing an HTTP URL from the browser always triggers a GET request.  To trigger a POST request, you can use an HTML form with attribute method="post" or write your own code.  For submitting HTML form data, the POSt request is the same as the GET request except that the URL-encoded query string is sent in the request body rather than appended behind the URI.

&nbsp;

The POST request has the following components, as shown in Figure 7-9:

**Figure 7-9** *Syntax of a POST Request*

> POST &nbsp;&nbsp;&nbsp; | &nbsp;&nbsp;&nbsp; Request URI &nbsp;&nbsp;&nbsp; | &nbsp;&nbsp;&nbsp; HTTP Version
> <br/>
> __
> <br/>
> Content Type
> <br/>
> __
> <br/>
> Content Length
> <br/>
> __
> <br/>
> Request Header (Optional)
> <br/>
> __
> <br/>
> Request Body (Optional)

&nbsp;

-   POST:  The keyword POST must be in all uppercase.
-   Request URI:  Specifies the path of the resource requested, which must begin from the root / of the document base directory.
-   HTTP version:  Either HTTP/1.0 or HTTP/1.1.  This client negotiates the protocol to be used for the current session.  For example, the client may request to use HTTP/1.1.  If the server does not support HTTP/1.1, it may inform the client in the response to use HTTP/1.0.
-   Request headers (optional):  The client can use optional request headers, such as content type and content length to inform the server of the media type and the length of the request body, respectively.
-   Request body (optional):  A POST request message has an optional request body, which contains the query string (explained later in this chapter).

&nbsp;

###  **HTTP Headers**

&nbsp;

The HTTP headers and parameters provide a lot of information that can help you trace issues when you encounter them.  HTTP headers are an essential part of an API request and response as they represent the metadata associated with the API request and response.  Headers carry information for the following:

-   Request and response body
-   Request authorization
-   Response caching
-   Response cookies

In addition, HTTP headers have information about HTTP connection types, proxies, and so on.  Most of these headers are for managing connections between a client, a server, and proxies.

&nbsp;

Headers are classified as request headers and response headers.  You have to set the request headers when sending a request API and have to set the assertion against the response headers to ensure that the correct headers are returned.

&nbsp;

###  **Request Headers**

&nbsp;

The request headers appear as name:value pairs.  Multiple values separated by commas, can be specified as follows:

&nbsp;

```
request-header-name: request-header-value1, request-header-value2, ...
```

&nbsp;

The following are some examples of request headers:

&nbsp;

```
Host:  myhouse.cisco.com
Connection:  Keep-Alive
Accept: image/gif, image/jpeg, */*
Accept-language: us-en, fr, cn
```

&nbsp;

###  **Response Headers**

&nbsp;

The response headers also appear as name:value pairs.  as with request headers, multiple values can be specified as follows:

&nbsp;

```
response-header-name: response-header-value1, response-header-value2,
```

&nbsp;

The following are some examples of response headers:

&nbsp;

```
Content-Type: text/html
Content-Length: 35
Connection: Keep-Alive
Keep-Alive: timeout=15, max=100
The response message body contains the resource data requested.
```

&nbsp;

The following are some examples of request and response headers:

-   **Authorization**:  Carries credentials containing the authentication information of the client for the resource being requested.
-   **WWW-Authenticate**:  This is sent by the server if it needs a form of authentication before it can respond with the actual resource being requested.  It is often sent along with response code 401, which means "unauthorized."
-   **Accept-Charset**:  This request header tells the server which character sets are acceptable by the client.
-   **Content-Type**:  This header indicates the media type (text/HTML or application/JSON) of the client request sent to the server by the client, which help process the request body correctly.
-   **Cache-Control**:  This header is the cache policy defined by the server.  For this response, a cached response can be stored by the client and reused until the time defined in the Cache-Control header.

&nbsp;

### **Response Codes**

&nbsp;

The first line of a response message (that is, the status line) contains the response status code, which the server generates to indicate the outcome of the request.  Each status code is a three-digit number:

-   1xx (informational):  The request was successfully received; the server is continuing the process.
-   2xx (success):  The request was successfully received, understood, accepted, and serviced.
-   3xx (redirection):  Further action must be taken to complete the request.
-   4xx (client error):  The request cannot be understood or is unauthorized or the requested source could not be found.
-   5xx (server error):  The server failed to fulfill a request.

&nbsp;

Table 7-4 describes some commonly encountered status codes.

&nbsp;

>  ***Key Topic***

&nbsp;

Table 7-4 HTTP Status Codes

| Status Code | Meaning | Explanation |
| -- | -- | -- |
| 100 | Continue | The server received the request and is in the process of giving the response. |
| 200 | Okay | The request is fulfilled. |
| 301 | Move permanently | The resource requested has been permanently moved to a new location.  The URL of the new location is given in the Location response header.  The client should issue a new request to the new location, and the application should update all references to this new location. |
| 302 | Found and redirected (or move temporarily) | This is the same as code 301, but the new location is temporary in mature.  The client should issue a new request, but applications need not update the references. | 
| 304 | Not modified | In response to the if-modified-since conditional GET request, the server notifies that the resource requested has not been modified. |
| 400 | Bad request | The server could not interpret or understand the request; there is probably a syntax error in the request message. |
| 401 | Authentication required | The requested resource is protected and requires the client's credentials (username and password).  The client should resubmit the request with the appropriate credentials (username and password). |
| 403 | Forbidden | The server refuses to supply the resource, regardless of the identity of the client. |
| 404 | Not found | The requested resource cannot be found on the server. |
| 405 | Method not allowed | THe requested method used (for example, POST, PUT, DELETE) is a valid method.  However the server does not allow that method for the resource requested. |
| 408 | Request timeout | THe request sent to the server took longer than the website's server was prepared to wait. |
| 414 | Request URI too large | The URI requested by the client is longer than the server is willing to interpret. |
| 500 | Internal server error | The server is confused;  this may be caused by an error in the server-side program responding to the request. |
| 501 | Method not implemented | The request method used is invalid; this could be caused by a typing error, such as Get in place of GET. |
| 502 | Bad gateway | The proxy or gateway indicates that it received a bad response from the upstream server. |
| 503 | Service unavailable | The server cannot respond due to overloading or maintenance.  The client can try again later. |
| 504 | Gateway timeout | The proxy or gateway indicates that it received a timeout from an upstream server. |

&nbsp;

>  ***Key Topic***

&nbsp;

Now that we have looked at HTTP methods and return codes, let's look at the data that is sent or received during a GET or POST.  Let's look at an example and see how the same information is represented in the various data types.  For this example, refer to Figure 7-7.  In this example, you are making a GET request to the server at myhouse.com to change the state of the lights in the living room to ON.

The data sent and received in a RESTful connection requires structured data formatting.  For the house example, you now see a response from the server that includes information about the house.  Standard data formats include XML, JSON, and YAML, which are described in the following sections.

&nbsp;

###  **XML**

&nbsp;

Extensible Markup Language (XML) is a markup language that encodes information between descriptive tags.  XML is a superset of Hypertext Markup Language (HTML), which was originally designed to describe the formatting of web pages served by servers through HTTP.  The encoded information is defined within user-defined schemas that tenable any data to transmitted between systems.  An entire XML document is stored as text, and it is both machine readable and human readable.

Example 7-1 shows a sample XML response document.  As you can see, with XML, you can assign some meaning to the tags in the document.  You can extract the various attributes from the response by simply locating the content surround by <study_room> and </study_room>; this content is technically known as the <study_room> *element*.

&nbsp;

**Example 7-1** *XML Data Format*

```
<?xml version="1.0" encoding="UTF-8" ?>
<root>
    <home>this is my house</home>
    <home>located in San Jose, CA</home>
    <rooms>
        <living_room>true</living_room>
        <kitchen>false</kitchen>
        <study_room>
            <size>20x30</size>
        </study_room>
        <study_room>
            <desk>true</desk>
        </study_room>
        <study_room>
            <lights>On</lights>
        </study_room>
    </rooms>
</root>
```

&nbsp;

###  **JSON**

&nbsp;

JSON, short for **JavaScript Object Notation**, is pronounced like the name "Jason.".  The JSON format is derived from JavaScript object syntax, but it is entirely text based.  It is a key:value data format that is typically rendered in curly braces {} and square brackets [].  JSON is readable and lightweight, and it is easy for humans to understand.

&nbsp;

A key/value pair has a colon (:) that separates the key from the value, and each such pair is separated by a comma in the document or the response.

JSON **keys** are valid strings.  The value of a key is one of the following data types:

-   String
-   Number
-   Object
-   Array
-   Boolean(true or false)
-   Null

&nbsp;

Example 7-2 shows a sample JSON response document, and you can see the full response.  If you are interested in seeing the status of the lights in the study_room, then you look at the values that are present and follow the various key/value pairs (such as "lights":"On") and extract the various values from the response by locating the correct keys and corresponding values.

&nbsp;

**Example 7-2** *JSON Data Format*

```
{
    "home": [
        "this is my house",
        "located in San Jose, CA"
    ],
    "rooms": {
        "living_room": "true",
        "kitchen": "false",
        "study_room": [
            {
                "size": "20x30"
            },
            {
                "desk": true
            },
            {
                "lights": "On"
            }
        ]
    }
}
```

&nbsp;

###  **YAML**

&nbsp;

**YAML** is an acronym that stands for "YAML Ain't Markup Language."  According to the official YAML site (https://ymal.org"), "YAML is a human-friendly data serialization standard for all programming languages."

&nbsp;

YAML is a data serialization language designed for human interaction.  It's a strict superset of JSON, another data serialization language.  But because it's a strict superset, it can do everything that JSON cna do and more.  One significant difference is that newlines and indentation mean something in YAML, whereas JSON uses brackets and braces to convey similar ideas.  YAML uses three main data formats:

-   **Scalars**:  The simplest is a *keyvalue* view.
-   **Lists/sequences**:  Data can be ordered by indexes.
-   **Dictionary mappings**:  These are similar to scalars but can contain nested data, including other data types.

&nbsp;

Example 7-3 shows a sample YAML response document.  As you can see, the response is very straightforward and human readable.  If you are interested in seeing the status of the lights in the study_room, you can find the study_room section and then look for the value of lights.

&nbsp;

**Example 7-3** *YAML Data Format*
```
---
home:
- this is my house
- located in San Jose, CA
rooms:
    living_room: 'true'
    kitchen: 'false'
    study_room:
    - size: 20x30
    - desk: true
    - lights: 'On'
```

&nbsp;

###  **Webhooks**

&nbsp;

Webhooks are user-defined HTTP callbacks.  A webhook is triggered by an event, such as pushing code to a repository or typing a keyword in a chat window.  An application implementing webhooks sends a POST message to a URL when a specific event happens.  Webhooks are also referred to as ***reverse APIs***, but perhaps more accurately, a webhook lets you skip the request step in the request/response cycle.  No request is required for a webhook, and a webhook sends data when triggered.

&nbsp;

For security reasons, the REST service may perform some validation to determine whether the receiver is valid.  A simple validation handshake performs validation, but this is just one way of validating.

&nbsp;

The validation token is a unique token specified by the server.  Validation tokens can be generated or revoked on the server side through the configuration UI.  When the server sends data to a webhook URL, it includes a validation token in the request HTTP header.  The webhook URL should consist of the same validation token value in the HTTP response header.  In this way, the server knows that it is sending to a validated endpoint and not a rogue endpoint.

&nbsp;

**Figure 7-10** *Webhook Validation and Event Flow*

>  REST Service sends a GET of /validationkey to Webhook.  Webhook responds with 200 OK {"validation":"33d932-123"} to the REST Service.  The REST Service then sends Event 1, Event 2, Event n.

&nbsp;

### **Tools Used When Developing with Webhooks**

&nbsp;

You will face a particular difficulty when developing an application that consumes webhooks.  When using a public service that provides webhooks, you need a publicly accessible URL to configure the webhook service.  Typically, you develop on localhost, and the rest of the world has no access to your application, so how do you test your webhooks?  ngrok (http://ngrok.com) is a free tool that allows you to tunnel from a public URL to your application running locally.

&nbsp;

###  **Sequence Diagrams**

&nbsp;

Now that you understand the fundamentals of REST API (request, response, and webhooks), authentication, data exchange, and constraints that go with rest APIs, it's time to introduce sequence diagrams.  A sequence diagram models the interactions between various objects in a single use case.  It illustrates how the different parts of a system interact with each other to carry out a function and the order in which the interactions occur when a particular use case is executed.  In simpler terms, a sequence diagram shows how different parts of a system work in a sequence together to get something done.

Figure 7-11 is a sequence diagram for the example we've been looking at, where a user wants to get a list of all rooms in the house.  For this example, assume that there is a web application with a user interface that renders the list of all the rooms and the various attributes of the rooms.

&nbsp;

**Figure 7-11** *Sequence Diagram Showing End-toEnd Flow*

>  Client sends HTTP Request to Web Front End.  Web Front sends GET Request to Back-End API Service.  Back-End API Service sends Response with JSON Data to Web Front End.  Cogs turn and Web Front End returns HTML Rendered UI.

&nbsp;

The sequence of events that occur is as follows:

-   The client browser points to httpL//myhouse.cisco.com/ (the HTTP GET request sent), which is the web application.
-   The server sends out a REST API request to get all the rooms of the back-end service (/API/getallrooms) to get all the details of the house.
-   The back-end API service returns data in JSON format.
-   The web application processes the JSON and renders the data in the user interface.
-   The client sees the data.

&nbsp;

>  ***Key Topic***

&nbsp;

##  REST Constraints

&nbsp;

REST defines six architectural constraints that make any web service a truly RESTful API.  These are constraints also known as Fielding's constraints (see https://www.ics.uci.edu/~fielding/pubs/dissertation/top.html).  They generalize the web's architectural principles and represent them as a framework of constraints or an architectural style.  These are the REST constraints:

-   Client/server
-   Stateless
-   Cache
-   Uniform interface
-   Layered system
-   Code on demand

The following sections discuss these constraints in some detail.

&nbsp;

###  **Client/Server**

&nbsp;

The client and server exist independently.  They must haven o dependency of any sort on each other.  The only information needed is for the client to know the source URIs on teh server.  The interaction between them is only in the form of requests initiated by the client and responses that the server sends to the client in response to the requests.  The client/server constraint encourages separation of concerns between the client and the server and allows them to evolve independently.

&nbsp;

### **Stateless**

&nbsp;

REST services have to be stateless.  each individual request contains all the information the server needs to perform the request and return a response, regardless of other requests made by the same API user.  The server should not need any additional information from previous requests to fulfill the current request.  The URI identifies the resource, and the body contains the state of the resource.  A stateless service is easy to scale horizontally, allowing additional servers to be added or removed as necessary without worry about routing subsequent requests to the same server.  The servers can be further load balanced as necessary.

&nbsp;

###  **Cache**

&nbsp;

With REST services, response data must be implicitly or explicitly labeled as cacheable or non-cacheable.  The service indicates the duration for which the response is valid.  Caching helps improve performance on the client side ans capability on the server side.   If the client has access to a valid cached response for a given request, it avoids repeating the same request.  Instead, it uses its cached copy.  This helps alleviate some of the server's work and thus contributes to scalability and performance.

&nbsp;

>  **Note**
> <br/>
> GET requests should be cacheable by default.  Usually browsers treat all GET requests as cacheable.
> <br/>
> POST requests are not cacheable by default but can be made cacheable by adding either an Expires header or a Cache-Control header to the response.
> <br/>
> PUT nad DELETE are not cacheable at all.

&nbsp;

###  **Uniform Interface**

&nbsp;

The uniform interface is a contract for communication between a client and a server.  It is achieved through four subconstraints:

-   **Identification of resources**:  As we saw earlier in the chapter, resources are uniquely identified by URIs.  THese identifiers are stable and do not change across interactions, even when the resource state changes.
-   **Manipulation of resource through representations**:  A client manipulates resources by sending new representations of the resource to the service.  THe server controls the resource representation and can accept or reject the new resource representation sent by the client.
-   **Self-descriptive messages**:  REST request and response messages contain all information needed for the service and the client to interpret the message and handle it appropriately.  The messages are quite verbose and include the method, the protocol used, and the content type.  This enables each message to be independent.
-   **Hypermedia as the Engine of Application State (HATEOS)**:  Hypermedia connects resources to each other and describes their capabilities in machine-readable ways.  Hypermedia refers to the hyperlinks, or simply links, that the server can include in the response.  Hypermedia is a way for the server to tell a client what HTTP requests the client might want to make in the future.

&nbsp;

###  **Layered System**

&nbsp;

A layered system further builds on the concept of client/server architecture.  A layered system indicates that there can be more components than just the client and the server, and each system can have additional layers in it.  These layers should be easy to add, remove, or change.  Proxies, load balancers, and so on are examples of additional layers.

&nbsp;

###  **Code on Demand**

&nbsp;

Code on demand is an optional constraint that gives the client flexibility by allowing it to download code.  The client can request code from the server, and the response from the server will contain some code, usually in the form of a script, when the response is in HTML format.  The client can then execute that code.

&nbsp;

###  **REST API Versioning**

&nbsp;

Versioning is crucial part of API design.  It gives developers the ability to improve an API without breaking the client's applications when new updates are rolled out.  Four strategies are commonly employed with API versioning:

-   URI path versioning:  In this strategy, the version number of the API is included in the URL path.
-   Query parameter versioning:  In this strategy, the version number is sent as a query parameter in the URL.
-   Custom headers:  REST APIs are versioned by providing custom headers with the version number included as an attribute.  The main difference between this approach and the two previous ones is that it doesn't clutter the URI with versioning information.
-   Content negotiations:  This strategy allows you to version a single resource representation instead of versioning an entire API, which means it gives you more granular control over versioning.  Another advantage of this approach is that it doesn't require you to implement URI routing rules, which are introduced by versioning through the URI path.

&nbsp;

### **Pagination**

&nbsp;

>  ***Key Topic***

&nbsp;

When a request is made to get a list, it is almost never a good idea to return all resources at once.  This is where a pagination mechanism comes into play.  There are two popular approaches to pagination:

-   Offset-based pagination
-   Keyset-based pagination, also known as continuation token or cursor pagination (recommended)

&nbsp;

A really simple approach to offset-based pagination is to use the parameters **offset** and **limit**, which are well known from databases.  

&nbsp;

Example 7-4 shows how query parameters are passed in the URI in order to get data based on offset and to limit the number of results returned.

&nbsp;

**Example 7-4** *Pagination:  Offset and Limit*

```
http://myhouse.cisco.com/api/room/livingroom/devices?offset=100&limit=15 
# returns the devices between 100-115
```

&nbsp;

Usually if the parameters are not specified, the default values are used.  Never return all resources.  One rule of thumb is to model the limit based on the design of your store retrieval performance.

&nbsp;

Example 7-5 shows a URI where no parameters are passed, which results in the default number of results.

&nbsp;

**Example 7-5** *Pagination:  No Parameters Yield the Default*

```
http://myhouse.cisco.com/api/room/livingroom/devices 
# returns the devices 0 to 200
```

&nbsp;

Note that the data returned by the service usually has links to the next and the previous pages, as shown in Example 7-6.

&nbsp;

Example 7-6 Pagination Response Containing Links

```
GET /devices?offset=100&limit=10
{
    "pagination": {
        "offset": 100,
        "limit": 10,
        "total": 220,
    },
    "device": [
        //...
    ],
    "links": {
        "next": "http://myhouse.cisco.com/devices?offset=110&limit=10",
        "prev": "http://myhouse.cisco.com/devices?offset=90&limit=10"
    }
}
```

&nbsp;

### **Rate Limiting and Monetization**

&nbsp;

Rate limiting is an essential REST API design method for developers.  Rate-limiting techniques are used to increase security, business impact, and efficiency across the board or end to end.  Let's look at how rate limiting helps with each of them:

-   **Security**:  Allowing unlimited access to your API is essentially like handing over the master key to a house and all the rooms therein.  While it's great when people want to use your API and find it useful, open access can decrease value and limit business success.  rate limiting is a critical component of an API's scalability.  Processing limits are typically measured in transactions per second (TPS).  If a user sends too many requests, API rate limiting can throttle client connections instead of disconnecting them immediately.  Throttling enables clients to keep using your service while still protecting your API.  Finally, keep in mind that there is always a risk of API requests timing out, and the open connections also increase the risk of DDoS attacks.  (DDos stands for distributed denial of services.  A DDoS attack consists of a website being flooded by requests during a short period of time, with the aim of overwhelming the site and causing it to crash.)
-   **Business impact**:  One approach to API rate limiting is to offer a free tier and a premium tier, with different limits for each tier.  Limits could be in terms of sessions or in terms of numbers of APIs per day or per month.  There are many factors to consider when deciding what to charge for premium API access.  API providers need to consider the following when setting up API rate limits:
    -   Are requests throttled when they exceed the limit?
    -   Do new calls and requests incur additional fees?
    -   Do new calls and requests receive a particular error code and, if so, which one?
-   **Efficiency**:  Unregulated API requests usually and eventually lead to slow page load times for websites.  Not only does this leave customers with an unfavorable opinion but can lower your service rankings.

&nbsp;

### **Rate Limiting on the Client Side**

As discussed in the previous section, various rate-limiting factors can be deployed on the server side.  As a good programming practice, if you are writing client-side code, you should consider the following:

-   Avoid constant polling by using webhooks to trigger updates.
-   Cache your own data when you need to store specialized values or rapidly review very large data sets.
-   Query with special filters to avoid re-polling unmodified data.
-   Download data during off-peak hours.

&nbsp;

>  ***Key Topic***

&nbsp;

## REST Tools

&nbsp;

Understanding and testing REST API architecture when engaging in software development is crucial for any development process.  The following sections explore a few of the most commonly used tools in REST API testing and how to use some of their most important features.  Based on this information, you will get a better idea of how to determine which one suits a particular development process the best.

&nbsp;

### **Postman**

&nbsp;

One of the most intuitive and popular HTTP clients is a tool called Postman (https://www.getpostmancom/downloads/).  It has a very simple user interface and is very easy to use, even if you're just starting out with RESTful APIs.  It can handle the following:

-   Sending simple GETs and POSTs
-   Creating and executing collections (to group together requests and run those requests in a predetermined sequence)
-   Writing tests (scripting requests with the use of dynamic variables, passing data between requests, and so on)
-   Chaining, which allows you to use the output of a response as an input to another request
-   Generating simple code samples in multiple programming languages
-   Importing and executing collections created by the community.


A collection lets you group individual requests together.  You can then organize these requests into folders.  


It is possible to generate code for any REST API call that you try in Postman.  After a GET or POST call is made, you can use the Generate Code option and choose the language you prefer.


Postman also has other helpful features, such as environments.  An environment is a key/value pair.  The key represents the name of the variable, which allows you to customize requests; by using variables, you can easily switch between different setups without changing your requests.


Finally, Postman stores a history of past calls so you can quickly reissue a call.  Postman even includes some nice touches as autocompletion for standard HTTP headers and support for rendering a variety of payloads, including JSON, HTML, and even multipart payloads.

You can find Postman examples at https://learning.postman.com/docs/postman/launching-postman/introduction/.

&nbsp;

### **curl**

&nbsp;

curl is an extensive command-line tool that can be downloaded from https://curl.haxx.se.  curl can be used on just about any platform on any hardware that exists today.  Regardless of what you are running and where, the most basic curl commands just work.

With curl, you commonly use a couple of different command-line options:

-   **-d**:  This option allows you to pass data to the remote server.  You can either embed teh data in the command or pass teh data using a file.
-   **-H**:  This option allows you to add an HTTP header to the request.
-   **-insecure**:  This option tells curl to ignore HTTPS certificate validation.
-   **-c**:  This option stores data received by the server.  You can reuse this data in subsequent commands with the -b option.
-   **-b**:  This option allows you to pass cookie data.
-   **-X**:  This option allows you to specify the HTTP method, which normally defaults to GET.

Now let's take a look at some examples of how to use curl.  Example 7-7 shows how to use curl to call a simple GET request.

&nbsp;

**Example 7-7** *Sample HTTP GET Using curl*

```
$ curl -sD - https://postman-echo.com/get?test=123
HTTP/1.1 200 OK
Content-Type: application/json; charset=utf-8
Date: Tue, 27 Aug 2019 04:59:34 GMT
ETag: W/"ca-42Kz98xXW2nwFREN74xZNS6JeJk"
Server: nginx
set-cookie: sails.sid=s%3AxZUPHE3Ojk1yts3qrUFqTj_MzBQZZR5n.NrjPkNm0WplJ7%2F%2BX9O7VU
TFpKHpJySLzBytRbnlzYCw; Path=/; HttpOnly
Vary: Accept-Encoding
Content-Length: 202
Connection: keep-alive

{"args":{"test":"123"},"headers":{"x-forwarded-proto":"https","host":"postman-
echo.com","accept":"*/*","user-agent":"curl/7.54.0","x-forward-
ed-port":"443"},"url":"https://postman-echo.com/get?test=123"}
```

&nbsp;

Example 7-8 shows how to use curl to call a simple POST request.

&nbsp;

**Example 7-8** *Sample HTTP POST Using curl*

```
$ curl -sD - -X POST   https://postman-echo.com/post   -H 'cache-control: no-cache'
-H 'content-type: text/plain'   -d 'hello DevNet'
HTTP/1.1 200 OK
Content-Type: application/json; charset=utf-8
Date: Tue, 27 Aug 2019 05:16:58 GMT
ETag: W/"13a-0lMLfkxl7vDVWfb06pyVxdZlaug"
Server: nginx
set-cookie: sails.sid=s%3AwiFXmSNJpzY0ONduxUCAE8IodwNg9Z2Y.j%2BJ5%2BOmch8XEq8jO1vzH8
kjNBi8ecJij1rGT8D1nBhE; Path=/; HttpOnly
Vary: Accept-Encoding
Content-Length: 314
Connection: keep-alive

{"args":{},"data":"hello DevNet","files":{},"form":{},"headers":{"x-forwarded-
proto":"https","host":"postman-echo.com","content-length":"12","accept":"*/*","ca
che-control":"no-cache","content-type":"text/plain","user-agent":"curl/7.54.0","x-
forwarded-port":"443"},"json":null,"url":"https://postman-echo.com/post"}
```

&nbsp;

Example 7-9 shows how to use curl to call a simple GET request with Basic Auth sent via the header.

&nbsp;

**Example 7-9** *Basic Auth Using curl*

```
$ curl -sD - -X GET   https://postman-echo.com/basic-auth   -H 'authorization: Basic
cG9zdG1hbjpwYXNzd29yZA=='   -H 'cache-control: no-cache'
HTTP/1.1 200 OK
Content-Type: application/json; charset=utf-8
Date: Tue, 27 Aug 2019 05:21:00 GMT
ETag: W/"16-sJz8uwjdDv0wvm7//BYdNw8vMbU"
Server: nginx
set-cookie: sails.sid=s%3A4i3UW5-DQCMpey8Z1Ayrqq0izt4KZR5-.Bl8QDnt44B690E8J06qyC-
s8oyCLpUfEsFxLEFTSWSC4; Path=/; HttpOnly
Vary: Accept-Encoding
Content-Length: 22
Connection: keep-alive
{"authenticated":true}
```

&nbsp;

### **HTTPie**

&nbsp;

HTTPie is a modern, user-friendly, and cross-platform command-line HTTP client written in Python.  It is designed to make CLI interaction with web services easy and user friendly.  Its simple HTTP commands enable users to send HTTP requests using intuitive syntax.  HTTPie is used primarily for testing, trouble-free debugging, and interacting with HTTP servers, web services, and RESTful APIs.  For further information on HTTPie documentation, downloading, and installation, see https://httpie.org/doc:

-   HTTPie comes with an intuitive UI and supports JSON.
-   It uses expressive and intuitive command syntax.
-   HTTPie allows for syntax highlighting, formatting, and colorized terminal output.
-   HTTPie allows you to use HTTPS, proxies, and authentication.
-   It provides support for forms and file uploads.
-   It provides support for arbitrary request data and headers.
-   It enables Wget-like downloads and extensions.

Now lets take a look at some examples using HTTPie.  Example 7-10 shows how to use HTTPie to call a simple GET request.

&nbsp;

**Example 7-10** *Sample HTTP GET Using HTTPie*

```
$ http https://postman-echo.com/get?test=123
HTTP/1.1 200 OK
Connection: keep-alive
Content-Encoding: gzip
Content-Length: 179
Content-Type: application/json; charset=utf-8
Date: Tue, 27 Aug 2019 05:27:17 GMT
ETag: W/"ed-mB0Pm0M3ExozL3fgwq7UlH9aozQ"
Server: nginx
Vary: Accept-Encoding
set-cookie: sails.sid=s%3AYCeNAWJG7Kap5wvKPg8HYlZI5SHZoqEf.r7Gi96fe5g7%2FSp0jaJk%2Fa
VRpHZp3Oj5tDxiM8TPZ%2Bpc; Path=/; HttpOnly

{
    "args": {
        "test": "123"
    },
    "headers": {
        "accept": "*/*",
        "accept-encoding": "gzip, deflate",
        "host": "postman-echo.com",
        "user-agent": "HTTPie/1.0.2",
        "x-forwarded-port": "443",
        "x-forwarded-proto": "https"
    },
    "url": "https://postman-echo.com/get?test=123"
}
```

&nbsp;

### **Python Requests**

&nbsp;

Requests is a Python module that you can use to send HTTP requests.  It is an easy-to-use library with a lot of possibilities ranging from passing parameters in URLs to sending custom headers and SSL verification.  The Request library is a very handy tool you can use whenever you programmatically start using any APIs.  Here you will see how to use this library to send simple HTTP requests in Python as well as a way to illustrate its easy of use.

You can use Requests with Python version 2.7 and 3.x.  Requests is an external module, so it needs to be installed before you can use it.  Example 7-11 shows the command you use to install the Requests package for Python.

&nbsp;

**Example 7-1** *Installing the Requests Package for Python*

```
$ pip3 install requests
```

&nbsp;

To add HTTP headers to a request, you can simply pass them in a Python dict to the headers parameter.  Similarly, you can send your own cookies to a server by using a dict passed to the cookies parameter.  Example 7-12 shows a simple Python script that uses the Requests library and does a GET request to the Postman Echo server.

&nbsp;

**Example 7-12** *Simple HTTP GET Using Python Requests*

```
import requests

url = https://postman-echo.com/get"

querystring = {"test";"123}

headers = {}

response = requests.request("GET", url, headers=headers, params=querystring)

print(response.text)
```

&nbsp;

Example 7-13 shows a simple Python script that uses the Requests library and does a POST request to the Postman Echo server.  Notice that the headers field is populated with the content type and a new field called payload that sends some random text to the service.  The response to the request is stored in a response object called response.  Everything in the response can be parsed, and further actions can be taken.  This example simply prints the value of a few attributes of the response.  

&nbsp;

**Example 7-13** *Simple HTTP POST Using Python Requests*

```
import requests

url = "https://postman-echo.com/post"

payload = "hello DevNet"

headers = {'content-type': 'text/plain'}

response = requests.request("POST", url, data=payload, headers=headers)

print(response.text)
```

&nbsp;

Example 7-14 shows a simple Python script that uses the Requests library and does a GET request to the Postman Echo server.  One difference you will notice between Example 7-11 and Example 7-14 is related to authentication.  With the Requests library, authentication is usually done by passing the 'authorization' keyword along with the type and key.

&nbsp;

**Example 7-14** *Basic Auth Using Python Requests*

```
import requests

url = "https://postman-echo.com/basic-auth"
headers = {
    'authorization': "Basic cG9zdG1hbjpwYXNzd29yZA=="
}

response = requests.request("GET", url, headers=headers)

print(response.text)
```

&nbsp;

### **REST API Debugging Tools for Developing APIs**

&nbsp;

As you start playing with RESTful APIs, you are bound to encounter errors.  You can use several techniques to determine the nature of a problem.  As you saw in Table 7-3, RESTful APIs use several mechanisms to indicate the results of REST calls and errors that occur during processing.  You can use these methods to start your debugging journey for a RESTful application. Usually the error code returned is the biggest hint you can receive. Once you have this information, you can use tools like Postman and curl to make simple API calls and see the sent and response headers. In addition, other tools that are built in to web browsers can allow you to see traces and do other types of debugging. Most browsers include some type of developer tools, such as Safari’s Web Development Tools, Chrome’s DevTools, and Firefox’s Developer Tools. Such tools are included with browsers by default and enable you to inspect API calls quickly. Finally, if you plan on building your own test environment or sandbox, you might want to use tools like Simple JSON Server (an open-source server that you can clone and run in your environment for playing with and learning about RESTful APIs).
