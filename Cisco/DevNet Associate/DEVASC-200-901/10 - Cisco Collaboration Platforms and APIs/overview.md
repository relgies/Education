#   Introduction to Cisco Collaboration Platform Portfolio

&nbsp;

Cisco's collaboration portfolio can be broken down into essentially four high-level components:

-   **Unified Communications Manager**:  This product unifies voice, video, data, and mobile apps.
-   **Unified Contact Center**:  This product provides customers with personalized omnichannel experiences.
-   **Cisco Webex**:  This conferencing solution enables teamwork with intuitive solutions that bring people together.
-   **Cisco collaboration endpoints**:  These devices provide better-than-being-there experiences via new devices.

&nbsp;

**Figure 10-1** *Rich Collaboration Portfolio*

![Figure 10-1 Rich Collaboration Portfolio](assets/images/Figure%2010-1%20Rich%20Collaboration%20Portfolio.jpeg)

&nbsp;

##  **Unified Communications**

&nbsp;

Cisco Unified communications solutions deliver seamless user experiences that help people work together more effectively - anywhere and on any device.  They bring real-time communication from your phone system and conferencing solutions together with messaging and chat and integrate with everyday business applications using APIs.

Unified Communications solutions are available as on-premises software, as partner-hosted solutions, and as a service (UCaaS) from cloud providers.

&nbsp;

##  **Cisco Webex Teams**

&nbsp;

Both Webex and Webex Meetings have a Join button you can click to easily join a meeting.  This helps ensure that meetings start on time and it streamlines the process of joining a meeting.  Cisco Webex Teams also has features that will help you make decisions on which meetings to prioritize and when to join them:

-   **Seeing invitee status/participants**:  Every invitee can see who has accepted/declined the meeting and who's in the meeting live before even joining.  There is no need to switch back and fourth between your calendar and the meeting application.
-   **Instantly switching between meetings**:  If you need to move from one meeting to another, simply leave the meeting with one click and join the other one with another click.
-   **Easily informing attendees when you are running late**:  In Webex Teams, you can message people in the meeting to keep them posted on your status.

&nbsp;

##  **Cisco Webex Calling**

&nbsp;

Webex Calling is a cloud-based phone system that is optimized for midsize businesses.  

Webex Calling seamlessly integrates with Webex Teams and Webex Meetings.  You can also add Cisco Webex Board, Room, or Desk Device to get the most out of Webex Teams and Meetings.

&nbsp;

##  **Cisco Unified Communications Manager (Unified CM)**

&nbsp;

***Cisco Unified Communications Manager (CM)***, often informally referred to as ***Call Manager***, is the core of Cisco's collaboration portfolio.  It often delivers people-centric user and administrative experiences and supports a full range of collaboration services, including videos, voice, instant messages and presence, massaging, and mobility on Cisco as well as third-party devices.

&nbsp;

##  **Unified Contact Center**

&nbsp;

The ***Cisco Unified Contact Center (Unified CC)***, also called ***Finesse***, is a next-generation desktop that is designed to provide the optimal user experience for agents.  It is 100% browser based, so agent client machines do not need any Unified CC-specific applications.  Cisco Finesse is a next-generation agent and supervisor desktop designed to provide a collaborative experience for the various communities that interact with a customer service organization.  It also helps to improve the customer experience and offers a user-centric design to enhance customer care representative satisfaction.

Cisco Finesse provides the following:

-   An agent and supervisor desktop that integrates traditional contact center functions into a thin-client desktop.
-   A 100% browser-based desktop implemented through a Web 2.0 interface; no client-side installations are required.
-   A single customizable interface that gives customer care provides quick and easy access to multiple assets and information sources.
-   Open Web 2.0 APIs that simplify the development and integration of value-added applications and minimize the need for detailed desktop development expertise.

&nbsp;

##  **Cisco Webex**

&nbsp;

Cisco Webex is a conferencing solution that allows people to collaborate more effectively with each other anytime, anywhere, and from any device.  Webex makes online meetings easy and productive with features such as document, application, and desktop sharing; integrated audio/video; active speaker detection; recording; and machine learning features.

&nbsp;

##  **Cisco Collaboration Endpoints**

&nbsp;

The Cisco collaboration endpoint portfolio includes the following devices:

-   **Room-based devices**:  These include video system or codec in the Cisco TelePresence MX Series, SX, and DX Series.
-   **Cisco Webex Board**:  Cisco Webex Board allows you to wirelessly present whiteboarding and video or audio conference for team collaboration.
-   **Webex Share**:  The new Webex Share device allows easy, one-clicking wireless screen sharing from the Webex Teams software client to any external display with an HDMI port.
-   **Collaboration desktop video devices**:  A range of options are available, from entry-level HD video up to the lifelike DX video collaboration devices.
-   **IP Phone portfolio**:  Cisco IP Phone devices deliver superior voice communications, with select endpoints supporting HD video and a range of options that offer choices for businesses of various sizes and with unique needs and budgets.  The complete portfolio also supports specialty use cases, such as in-campus wireless with WLAN handsets and an audio-conferencing endpoint for small to large conference rooms.  The goal of the IP Phone portfolio is to deliver the highest-quality audio communications with affordable, scalable options for desktop video that are easy to use and administer so you can collaborate effectively and achieve your desired business results.
-   **Cisco Headset 500 Series**:  These headsets deliver surprisingly vibrant sound for open workspaces.  Now users can stay focused in noisy environments with rich sound, exceptional comfort, and proven reliability.  The headsets offer a lightweight form factor designed for workers who spend a lot of time collaborating in contact centers and open workspaces.  With the USB headset adapter, the 500 Series delivers an enhanced experience, including automatic software upgrades, in-call presence indicator, and audio customizations that allow you to adjust how you hear the far end and how they hear you.

&nbsp;

##  **API Options in the Cisco Collaboration Portfolio**

&nbsp;

APIs are used to integrate and scale these products in building various applications.  The following sections cover four categories of collaboration APIs:

-   Webex Meetings API
-   Webex Teams
-   Contact Center (Finesse)
-   Endpoints

&nbsp;

#   Webex Teams API

&nbsp;

Conversations in Webex Teams take place in virtual meeting rooms called ***spaces***.  Some spaces live for a few hours while others become permanent.

Webex Teams allows conversations between messages, video calls, and real-time whiteboarding sessions.

Webex APIs allow developers to build integrations and bots for Webex Teams.  APIs also allow administrator to perform administrative tasks.

Webex APIs provide applications with direct access to the Cisco Webex platform, giving you the ability to do the following:

-   Administer the Webex Teams platform for an organization, add user accounts, and so on
-   Create a Webex teams team, space, and memberships
-   Search for people in the company
-   Post messages in a Webex teams space
-   Get Webex Teams space history or be notified in real time when new messages are posted by others

&nbsp;

Only an admin has the ability to add a new organization or a new user account for the organization.  An organization is made up of teams, and a team can have one or more rooms.  A person is an end user who can be added to a room.  

**Figure 10-2** *Webex Teams Building Blocks:  Organizations, Teams, Rooms, People, and Messages*

![Figure 10-2 Webex Teams Building Blocks:  Organizations, Teams, Rooms, People, and Messages](assets/images/Figure%2010-2%20Webex%20Teams%20Building%20Blocks%20Organizations,%20Teams,%20Rooms,%20People,%20and%20Messages.jpeg)

&nbsp;

##  **API Authentication**

&nbsp;

There are four ways to access the Webex teams APIs:

-   ***Personal access tokens***
-   ***Integrations***
-   ***Bots***
-   ***Guest issuers***

&nbsp;

The Webex Representation State Transfer (REST) API uses the Cisco Webex ***Common Identity (CI)*** account.  Once you create an account to join Webex Teams, you have access to the Common Identity account, which allows you to use the APIs and SDKs.

&nbsp;

##  **Personal Access Tokens**

&nbsp;

When making requests to the Webex REST API, an authentication HTTP header is used to identify the requesting user.  This header must include an ***access token***, which may be a ***personal access token*** from the developer site (https://developer.webex.com), a ***bot token***, or an ***OAuth token*** from the ***integration*** or a ***guest issuer application***.

The API reference uses your personal access token, which you can use to interact with the Webex API as yourself.  This token has a short lifetime - it lasts only 12 hours after logging in to the site - so it shouldn't be used outside of app development.

**Figure 10-3** *Webex Teams:  Getting a Personal Access Token*

![Figure 10-3 Webex teams:  Getting a Personal Access Token](assets/images/Figure%2010-3%20Webex%20Teams%20Getting%20a%20Personal%20Access%20Token.jpeg)

&nbsp;

##  **Integrations**

&nbsp;

To perform actions on behalf of someone else, you need a separate access token that you obtained through an ***OAuth*** authorization grant flow.  OAuth is supported directly into the platform.

**Figure 10-4** *Webex Teams:  Third Party Integrations*

![Figure 10-4 Webex Teams:  Third Party Integrations](assets/images/Figure%2010-4%20Webex%20Teams%20%20Third%20Party%20Integrations.jpeg)

You can use an integration to request permission to invoke the Webex REST API on behalf of another Webex Teams users.  To provide security, the API supports the OAuth 2 standard, which allows a third-party integration to get a temporary access token for authentication API calls instead of asking users for their password.

Here are a few easy steps to get started using an integration:

-   **Step 1**.  Registeran integration with Webex Teams at https://developer.webex.com/my-apps/new.
-   **Step 2**.  Request permissiong by using an OAuth grant flow by invoking the flow via https://webexapis.com/v1/authorize and providing a redirect URL to come back to.
-   **Step 3**.  Click Accept to obtain the authorization code for an access token.

The redirect URL contains a code parameter in the query string like so:

`https://0.0.0.0:8080/?code=NzAwMGUyZDUtYjcxMS00YWM4LTg3ZDYtNzdhMDhhNWRjZGY5NGFmMjA3ZjEtYzRk_PF84_1eb65fdf-9643-417f-9974-ad72cae0e10f&state=set_state_here`

&nbsp;

##  **Access Scopes**

&nbsp;

***Scopes*** define the level of access that an integration requires.  Each integration alerts the end user with the scope of the integration.  Scopes determine what resources the Access Token has access to.  Table 10-2 lists and describes the scopes.

**Table 10-2** Webex Teams and Scopes API Definitions

| Scope | Description |
| -- | -- |
| permission dialog.spark:all | Full access to your Webex Teams account |
| spark:people_read | Read your company directory |
| spark:rooms_read | List the title of rooms that you're in |
| spark:rooms_write | Manage rooms on your behalf |
| spark:memberships_read | List the people in rooms that you're in |
| spark:memberships_write | Invite people to rooms on your behalf |
| spark:messages_read | Read the content of rooms that you're in |
| spark:messages_write | Post and delete messages on your behalf |
| spark:teams_read | List the teams you are a member of |
| spark:teams_write | Manage teams on your behalf |
| spark:team_memberships_read | List the people in the teams that you are in |
| spark:team_memberships_write | Add people to teams on your behalf |
| spark:webhooks_read | See all webhooks created on your behalf |
| spark:webhooks_write | Modify or delete webhooks created on your behalf |

&nbsp;

*The following sections examine some of the APIs you can use to create rooms, add people, and send messages in a room.*

&nbsp;

##  **Organizations API**

&nbsp;

*An organization is a set of people in Webex Teams.*  Organizations may manage other organizations or may be managed themselves.  The organizations API can be accessed only by an administrator.  Table 10-3 shows the methods used with Organizations API to get details about organizations.

**Table 10-3** *Webex Teams:  Organization API*

| Method | API | Description |
| -- | -- | -- |
| GET | `http://webexapis.com/v1/organizations` | List all the organizations |
| GET | `https://webexapis.com/v1/organizations{orgId}` | Get details about an organization |

> Note
> <br>
> The hostname https://api.ciscospark.com has now been changed to https://webexapis.com.  The old https://api.ciscospark.com will continue to work.

&nbsp;

## **Teams API**

&nbsp;

*A team is a group of people with a set of rooms that is visible to all members of that team.*

The TEAM API is used to manage teams - to create, delete, and rename teams.  Table 10-4 lists the various operations that can be performed on the Teams API.

**Table 10-4** Webex Teams:  Teams API

| Method | API | Description |
| -- | -- | -- |
| GET | `https://webexapis.com/v1/teams` | List all teams |
| POST | `https://webexapis.com/v1/teams` | Create a new team |
| GET | `https://webexapis.com/v1/teams/{teamId}` | Get details about a particular team |
| PUT | `https://webexapis.com/v1/teams/{teamId}` | Update details about a team |
| DELETE | `https://webexapis.com/v1/teams/{teamId}` | Delete a team |

You can use a Python request to make the REST call.  Example 10-1 shows a Python script that sends a POSt request to create a new team.  It initializes variables such as the base URL, the payload, and the headers and it calls the request.

**Example 10-1** *Python code to Create a New Team*

```python
""" Create Webex Team """

import json
import requests

URL = "https://webexapis.com/v1/teams"
PAYLOAD = {
    "name": "DevNet Associate Certification Team"
}
HEADERS = {
    "Authorization": "Bearer MDA0Y2VlMzktNDc2Ni00NzI5LWFiNmYtZmNmYzM3OTkyNjMxNmI0ND-VmNDktNGE1_PF84_consumer",
    "Content-Type": "application/json"
}
RESPONSE = requests.request("POST", URL, data=json.dumps(PAYLOAD), headers=HEADERS)
print(RESPONSE.text)
```

&nbsp;

##  **Rooms API**

&nbsp;

*Rooms are virtual meeting places where people post messages and collaborate to get work done.*

The Rooms API is used to mange rooms - to create, delete, and rename them.  Table 10-5 lists the operations that can be performed with the Room API.

**Table 10-5** Webex Teams:  Rooms API

| Method | API | Description |
| -- | -- | -- |
| GET | `https://webexapis.com/v1/rooms` | List of all the rooms |
| POST | `https://webexapis.com/v1/rooms` | Create a new room |
| GET | `https://webexapis.com/v1/rooms/{roomId}` |Get room details |
| GET | `https://webexapis.com/v1/rooms/{roomId}/meetingInfo` | Get room meeting details |
| PUT | `https://webexapis.com/v1/rooms/{roomId}` | Update room details |
| DELETE | `https://webexapis.com/v1/rooms/{roomId}` | Delete a room |

You can use the Rooms API to create a room.  When you do, an authenticated user is automatically added as a member of the room.  

To create a room, you can use the POST method and the API `https://webexapis.com/v1/rooms`.

Example 10-2 shows Python request code that create a room with the name "DevAsc Team Room".  It initializes variables such as the base URL, the payload, and the headers, and it calls the request.  The header consists of the bearer token of the authenticated user or the integration along with the other parameters.

**Example 10-2** *Python Request to Create a New Room*

```python
import json
import requests
import pprint

URL = "https://webexapis.com/v1/rooms"
PAYLOAD = {
    "title": "DevAsc Team Room"
}
HEADERS = {
    "Authorization": "Bearer MDA0Y2VlMzktNDc2Ni00NzI5LWFiNmYtZmNmYzM3OTkyNjMxNmI0ND-VmNDktNGE1_PF84_consumer",
    "Content-Type": "application/json"
}
RESPONSE = requests.request("POST", URL, data=json.dumps(PAYLOAD), headers=HEADERS)
pprint.pprint(json.loads(RESPONSE.text))
```

Example 10-3 shows the response to create a room.  The response includes the creation time and owner, along with the ID, which can be used in subsequent calls.

**Example 10-3** *Response to the Successful Creation of a Room*

```bash
$ python3 CreateRoom.py
{'created': '2020-02-15T23:13:35.578Z',
 'creatorId': 'Y2lzY29zcGFyazovL3VzL1BFT1BMRS8wYWZmMmFhNC1mN2IyLTQ3MWU-
 tYTIzMi0xOTEyNDgwYmDEADB',
 'id': 'Y2lzY29zcGFyazovL3VzL1JPT00vY2FhMzJiYTAtNTA0OC0xMWVhLWJiZWItYmY1MWQyNGRm
 MTU0',
 'isLocked': False,
 'lastActivity': '2020-02-15T23:13:35.578Z',
 'ownerId': 'consumer',
 'title': 'DevAsc Team Room',
 'type': 'group'}
$
```

You can use the Rooms API to get a list of all the rooms that have been created.  To do so, you use the GET method and the API `https://webexapis.com/v1/rooms`.

Example 10-4 shows how to use the curl command to make the REST call.  This scripts sends a GET request to list all rooms that a particular user belongs to.

**Example 10-4** ***curl** Script for Getting a List of All Rooms*

```curl
$ curl -X GET \
    https://webexapis.com/v1/rooms \
    -H 'Authorization: Bearer DeadBeefMTAtN2UzZi00YjRiLWIzMGEtMThjMzliNWQwZGEyZTljN-
  WQxZTktNTRl_PF84_1eb65fdf-9643-417f-9974-ad72cae0e10f'
```

&nbsp;

##  **Memberships API**

&nbsp;

*A membership represents a person's relationship to a room.*  

You can use the Memberships API to list members of any room that you're in or create memberships to invite someone to a room.  Memberships can also be updated to make someone a moderator or delete to remove someone from the room.

Table 10-6 lists the operations that can be performed with respect to the Memberships API, such as listing memberships and adding a new member.

**Table 10-6** Webex teams:  Memberships API

| Method | API | Description |
| -- | -- | -- |
| GET | `https://webexapis.com/v1/memberships` | List memberships |
| POST | `https://webexapis.com/v1/memberships` | Add a new member |
| GET | `https://webexapis.com/v1/memberships/{membershipId}` | Get details about a member |
| PUT | `https://webexapis.com/v1/memberships/{membershipId}` | Update details about a member |
| DELETE | `https://webexapis.com/v1/memberships/{membershipId}` | Delete a member |

You can use the Membership API to add a new member to a given room (that is, create a new membership) by using the POST method and the API `https://webexapis.com/v1/memberships`

You can use Python to make a REST call.  Example 10-4 shows a **curl** script that sends a POSt request to add a new member with email-id `newUser@devasc.com` to the room.

**Example 10-5** *Python Script to Add a New Member to a Room*

```python
""" Add new Member to a Webex Room """

import json
import requests
import pprint

URL = "https://webexapis.com/v1/memberships"
PAYLOAD = {
    "roomId": "Y2lzY29zcGFyazovL3VzL1JPT00vY2FhMzJiYTAtNTA0OC0xMWVhLWJiZ-WItYmY1MWQyNGRDEADB",
    "personEmail": "newUser@devasc.com",
    "personDisplayName": "Cisco DevNet",
    "isModerator": "false"
}
HEADERS = {
    "Authorization": "Bearer MDA0Y2VlMzktNDc2Ni00NzI5LWFiNmYtZmNmYzM3OTkyNjMxNmI0NDVmNDktNGE1_PF84_consumer",
    "Content-Type": "application/json"
}
RESPONSE = requests.request("POST", URL, data=json.dumps(PAYLOAD), headers=HEADERS)
print(RESPONSE.text)
```

&nbsp;

##  **Messages API**

&nbsp;

*Messages are communications that occur in a room.*

In Webex teams, each message is displayed on its own line, along with a timestamp and sender information.  You can use the Messages API to list, create, and delete messages.


Messages can contain plaintext, rich text, and a file attachment.  Table 10-7 shows the API for sending messages to Webex Teams.

**Table 10-8** Webex Teams:  Message API

| Method | API | Description |
| -- | -- | -- |
| GET | `https://webexapis.com/v1/messages` | List messages |
| GET | `https://webexapis.com/v1/messages/direct` | List one-to-one messages |
| POST | `https://webexapis.com/v1/messages` | Post a new message |
| GET | `https://webexapis.com/v1/messages/{messageId}` | Get details about a message |
| DELETE | `https://webexapis.com/v1/messages/{messageId}` | Delete a message |

You can use the Messages API to add a new message to a given room (that is, create a new message).  To do so, you use the POST method and the API `https://webexapis.com/v1/messages`.

You can use a Python request to make a REST call.  Example 10-6 shows a Python script that sends a POST message to add a new message to a particular room.

**Example 10-6** *Python Script to Add a New Message to a Room*

```python
""" Send Webex Message """

import json
import requests
import pprint

URL = "https://webexapis.com/v1/messages"
PAYLOAD = {
    "roomId" : "Y2lzY29zcGFyazovL3VzL1JPT00vY2FhMzJiYTAtNTA0OC0xMWVhLWJiZ-WItYmY1MWQyNGRmMTU0",
    "text": "This is a test message"
}
HEADERS = {
    "Authorization": "Bearer  NDkzODZkZDUtZDExNC00ODM5LTk0YmYtZmY4NDI0ZTE5ZDA1MGI-5YTY3OWUtZGYy_PF84_consumer",
    "Content-Type": "application/json",
}
RESPONSE = requests.request("POST" URL, data=json.dumps(PAYLOAD), headers=HEADERS)
pprint.pprint(json.loads(RESPONSE.text))
```

&nbsp;

##  **Bots**

&nbsp;

*A bot (short for chatbot) is a piece of code or an application that simulates a human conversations.*

Users communicate with a bot via the chat interface or by voice, just as they would talk to a real person.  Bots help users automate tasks, bring external content into the discussion, and gain efficiencies.  Webex Teams has a set of APIs which makes it easy to add a bot to any Teams room.  

In Webex, bots are similar to regular Webex Teams users.  They can participate in one-to-one and group spaces, and users can message them directly or add them to a group space.  A special badge is added to a bot's avatar in the Webex Teams client so users know they're interacting with a bot instead of a human.

A bot can only access messages sent to it directly.  In group spaces, bots must be @mentioned to access a message.  In one-to-one spaces, a bot has access to all messages from the user.  Bots are typically of the three types describes in Table 10-8.

**Table 10-8** Bot Types

| Type | Description |
| -- | -- |
| **Notification bot** | Events from external services are brought in and posted in Webex Teams.  Examples of events include build complete, retails, inventory, status, and temperature today. |
| **Controller bot** | External systems that have APIs allow third-party apps to be integrated to control them.  For example, you could control turning lights on or off by invoking a lights bot. |
| **Assistance bot** | Virtual assistants usually understand natural language, so a user can ask questions of bots as they would ask humans (for example, "@Merakibit, how many wifi devices are currently on floor 2?") |

&nbsp;

##  **Bot Frameworks Tools**

&nbsp;

These are two popular bot frameworks:

-   Flint:  Flint is an open-source bot framework with support for regex pattern matching for messages and more.
-   Botkit:  Botkit is a popular open-source bot framework with advanced conversational support as well as integrations with a comprehensive array of natural language processing and storage providers.

&nbsp;

##  **Guest Issuer**

&nbsp;

***Guest issuer** applications give guest users temporary access to users within the organization.*

Guest issuers can be created at https://developer.webex.com/my-apps/new/guest-issuer.  To create a new guest issuer, the only thing that is required is the name.  A new guest issuer ID and shared secret will be generated and can be used subsequently.

The main reason to use a guest issuer is to interact with users who do not have a Webex Teams account.  These guest users can interact with a regular Webex Teams users via **tokens** generated by a **guest issuer application**.

Guest users of Webex Teams authenticate by using ***guest tokens***.  Guest tokens use the ***JSON Web Token (JWT)*** standard to create and share authentication credentials between SDKs and widgets and the Webex REST API.  These tokens are exchanged for an access authentication token that can be used for a limited time and limited purpose to interact with regular Webex Teams users.

Each  guest token should be associated with an individual user of an application.

Example 10-7 shows a Python code snippet that creates a JWT token from the guest issuer ID and secret and passes it in the authentication headers.  It is then possible to use any of the APIs to interact with other users in the system.

Exmaple 10-7 Python Code to Generate a JWT Token for a Guest Issuer

```python
""" Generate JWT """

import base64
import time
import math
import jwt

EXPIRATION = match.floor(time.time()) + 3600 # 1 hour from now

PAYLOAD = {
    "sub": "devASC",
    "name": "devASC-guest",
    "iss": "GUEST_ISSUER_ID",
    "exp": EXPIRATION
}

SECRET = base64.b64decode('GUEST_ISSUE_SECRET')

TOKEN = jwt.encode(PAYLOAD, SECRET)

print(TOKEN.decode('utf-8'))

HEADERS = {
    'Authorization': 'Bearer ' + TOKEN.decode('utf-8')
}
```

&nbsp;

Webex Teams SDKs

&nbsp;

There are variety of SDKs available; some of them official Webex teams SDKs, and others are from the community.

The following is a selection of Webex teams SDKs that are available:

-   **Go (go-cisco-Webex-teams)**:  A god client library (by jbogarin)
-   **Java (spark-java-sdk)**:  A Java library for consuming the RESTful APIs (by Cisco Webex)
-   *Node.js (ciscospark)*:  A collection of Node.js modules targeting the REST API (by Cisco Webex)
-   **PHP (SparkBundle)**:  A Symfony bundle (by CiscoVE)
-   **Python (Webexteamssdk)**:  An SDK that works with the REST APIs in native Python (by cmlccie)

The following are some advanced APIs:

-   **SDK for Android**:  Integrates messaging and calling into Android apps (by Cisco Webex)
-   **SDK for Browsers**:  Integrates calling into client-side JavaScript applications (by Cisco Webex)
-   **SDK for iOS**:  Integrates messaging and calling into iOS apps (By Cisco Webex)
-   **SDK for Windows**:  Integrates messaging and calling into Windows apps (by Cisco Webex)
-   **Widgets**:  Provides components that mimic the web user experience (by Cisco Webex)

&nbsp;

#   Cisco Finesse

&nbsp;

*The Cisco Finesse desktop is a call agent and supervisor desktop solution.*

The Cisco Finesse desktop runs in a browser, which means you install Cisco Unified Contact Center Express (Unified CCX), and agents start by simply typing in the URL for the Unified CCX server.

**Figure 10-9** *Finesse High-Level Flow*

![Figure 10-9 Finesse High-Level Flow](assets/images/Figure%2010-9%20Finesse%20High-Level%20Flow.jpeg)

**Table 10-9** User States in Finesse

| State | Description |
| -- | -- |
| LOGIN | The agent is signing in to the system.  This is an intermediate state. |
| LOGOUT | The agent is signed off the system. |
| READY | The agent is ready to take calls. |
| NOT_READY | The agent is signed in but not ready to take calls.  It could be on a break, or the shift might be over, or the agent might be in between calls. |
| RESERVED | This is a transient state, as the agent gets chosen but has not answered the call. |

&nbsp;

##  **Cisco Finesse API**

&nbsp;

*The Cisco Finesse API is an open-standards-based web API exposed via REST.*

Agents and supervisors use the Cisco Finesse desktop APIs to communicate between the Finesse desktop and Finesse server, and they use ***Unified Contact Center Enterprise (Unified CCE) or Unified Contact Center Express (Unified CCX)*** to send and receive information.

The Finesse APIs can be broadly classified into the following categories:

-   User
-   Dialog
-   Queue
-   Team
-   ClientLog
-   Task Routing APIs
-   Single Sign-On
-   TeamMessage

Cisco Finesse supports both HTTP and HTTP Secure (HTTPS) requests from clients.  Cisco Finesse desktop operations can be performed using one of the available REST-like HTTP/HTTPS requests.  Operations on specific objects are performed using the Id of the object in the REST URL.  For example, the URL to view a single object (HTTP) would be as follows:

`https://<FQDN>:<port>/finesse/api/<object>/<objectID>`

The FQDN is the full qualified domain name of the Finesse server.

&nbsp;

Finesse APIs use the following HTTP methods to make requests:

-   **GET**:  Retrieves a single value in an object (for example, a single user or list of users).
-   **PUT**:  Replaces a value in an object (for example, to change the state of a user from NOT_READY to READ).
-   **POST**:  Creates a new entry in a collection (for example, to make a new reason code or wrap-up reason).
-   **DELETE**:  Removes an entry form a collection (for example, to delete a reason code or wrap-up reason).

Finesse uses the standard HTTP status code (for example, 200, 400, and 500) in the response to indicate the overall success or failure of a request.

&nbsp;

##  **API Request**

&nbsp;

***All Finesse APIs use HTTP BASIC authentication, which requires the credentials to be sent in the authorization header.***  The credentials contain the username and password, separated by a single colon (:), within a Base64-encoded string.

For example, the authorization header would contain the following string `"Basic ZGV2YXNjOnN0cm9uZ3Bhc3N3b3Jk"` where ZGV2YXNjOnN0cm9uZ3Bhc3N3b3Jk is the Base64-encoded string *devasc:strongpassword* (*devasc* is the username and *strongpassword* is the password).

Example 10-8 shows three lines of code that do Base64 encoding in order to plug the value in the authorization headers.

**Example 10-8** *Python Code to Generate Base64 Encoding*

```python
""" Generate Base64 Encoding """

import base64
ENCODED = base64.b64encoded('devasc:strongpassword'.encode('UTF-8'))
print(ENCODED.decode('utf-8'))
```

With Single Sign-On mode, the authorization header would contain the following string: `"Bearer <authtoken>"`

&nbsp;

##  **Finesse User APIs**

&nbsp;

Table 10-10 lists the various methods and User APIs to perform operations with the user, such as listing, logging in, and changing properties.

**Table 10-10** Finesse User APIs

| Method | API | Description |
| -- | -- | -- |
| GET | <pre>http://\<FQDN>/finesse/api/User/\<id></pre> | Get a copy of the user object |
| GET | <pre>http://\<FQDN>/finesse/api/User</pre> | Get a list of all users |
| PUT | <pre>http://\<FQDN>/finesse/api/User/\<id><br>with XML body:<br>\<User><br>    \<state>LOGIN\</state><br>\<extension>5250001\</extension><br>\</User></pre> | Sign in to the CTI server |
| PUT | <pre>http://\<FQDN>/finesse/api/User/\<id><br>with XML body:<br>\<User><br>    \<state>READY</state><br>\</User></pre> | Set the user's state:<br><li>READY<li>NOT_READY<li>LOGOUT |
| GET | <pre>http://\<FQDN>/finesse/api/Users/\<id>/PhoneBooks | Get a list of phone books and the first 1500 associated contacts for that user |

&nbsp;

> ***Personal Note***
> <br>
> Several Python examples skipped.

&nbsp;

##  Finesse Team API

&nbsp;

*The team object represents a team and contains the **URI**, the **team name**, and the **users** associated with the team.*  


**Table 10-11** Finesse Team APIs

| Method | API | Description |
| -- | -- | -- |
| GET | <pre>http://\<FQDN>/finesse/api/Team/\<id>?includeLoggedOutAgents=true</pre> | Allow a user to get a copy of the Team object |
| GET | <pre>http://\<FQDN>/finesse/api/Team/\<teamid>/TeamMessages</pre> | Get a list of all active team messages for a particular team |

> ***Personal Note***
> <br>
> Several Python examples skipped.

&nbsp;

##  **Dialog APIs**

&nbsp;

*The Dialog object represents a dialog (voice or non-voice) between two or more users.*

**Table 10-12** Sample of Finesse Dialog APIs

| Method | API | Description |
| -- | -- | -- |
| POST | <pre>http://\<FQDN>/finesse/api/User/\<id>/Diaglogs<br>with XML Body:<br>\<Dialog><br>  \<requestedAction>MAKE_CALL\</requestedAction><br>  \<fromAddress>6001\</fromAddress><br>  \<toAddress>6002\</toAddress><br>\</Dialog></pre> | Allow a user to make a call |
| PUT | <pre>http://\<FQDN>/finesse/api/Dialog\<diaglogId><br>with XML body:<br>\<Dialog><br>  \<requestedAction>START_RECORDING\</requestedAction><br>  \<targetMediaAddress>6001\</targetMediaAddress><br>\</Dialog></pre> | Allow a user to start recording an active call |

&nbsp;

> ***Personal Note***
> <br>
> Several Python examples skipped.

&nbsp;

##  **Finesse Gadgets**

As indicated earlier, the Finesse desktop application is an OpenSocial gadget container.  This means that an agent or anyone else can customize what is on the desktop.  Gadget are built using HTML, CSS, and JAvaScript. 

A gadget is defined using declarative XML syntax that is processed by a gadget server so that it can be embedded into the following contexts:

-   Standalone web pages
-   Web applications
-   Other gadgets

The Finesse JavaScript library can be found on a Finesse server at `http(s)://<FQDN>:<port>/desktop/assets/js/doc/index.html`.

&nbsp;

#   Webex Meetings APIs

&nbsp;

The Webex Meetings APIs let users incorporate Cisco Webex meetings into their own applications:

-   **URL API**:  The URL API is a convenient lightweight, HTTP/HTTPS-based mechanism that provides browser-based external hooks into Webex Meetings services.  The URL API is typically used in enterprise portal integrations to support basic interactions such as ***single sign-on (SSO)***, scheduling meetings, starting and joining simple meetings, and inviting attendees and presenters.
-   **XML API**:  If more advanced integration is needed than is possible with URL API, Cisco strongly recommends using the Webex Meetings XML.  The XML API is a comprehensive set of service that supports most aspects of Webex Meetings services, including detailed user management, comprehensive scheduling features, and attendee management and reporting.  The Webex XML API uses a ***service-oriented architecture (SOA)*** to provide comprehensive services to extend applications wishing to interact with one or more Webex services.
-   **Teleconference Service Provider (TSP) API**:  The TSP API provides full-featured XML-based integrations with audio conferencing networks.  The integration architecture supports redundancy, failover, and load balancing, and it provides robust features that tightly integrate audio conferencing capabilities with telephony management and provisioning in the Webex environment.

**Table 10-13** Webex Meetings Services Supported via APIs

| Service Name | Integration Usage |
| -- | -- |
| Managing User Accounts | <li>Creating a new user account<li>Editing an existing user account<li>Activating and deactivating user accounts |
| Webex-hosted website login/logout | Using an authenticated server-to-server connection for logging in to and out of a Webex Meetings - hosted website |
| Using and Managing Meetings | <li>Scheduling a meeting<li>Editing a meeting<li>Starting or deleting a host's scheduled meeting<li>Listing all scheduled meetings<li>Listing all open meetings<li>Joining an open meeting |
| Modifying My Webex Meetings page | <li>Modifying user information on My Webex Meetings Page<li>Managing a user's My Contacts list |
| Modifying My Webex Meetings page | <li>Modifying user information on the My Webex Meetings Page<li>Managing a user's My Contacts list |
| Using Attendee Registration forums | <li>Creating a registration form<li>Determining the current required, optional, or do-not-display settings for a registration page<li>Adding check boxes, buttons, and drop-down lists to a registration form |
| Managing Attendee Lists | <li>Adding attendees to a list of invited users<li>Removing attendees from a list of invited users |
| Playing back a recorded event | Allowing an attendee to get a list of recorded events for playback |
| Querying for Questions and Answers | <li>Viewing a list of custom questions created by the host<li>Viewing attendees' answers to custom questions<li>Viewing a list of standard questions created by the host<li>Viewing attendees' answers to standard questions |
| Making Recording Training Sessions available for viewing | Making all aspects of a previously recorded Training Center sessions available for later playback |

&nbsp;

##  **Authentication**

&nbsp;

There are three methods by which a user can interact with the Webex Meetings via APIs:

-   **Webex Meetings Integration**:  An application can authenticate XML API requests using OAuth 2.0 access tokens.  This authentication method does require end-user authorization and authentication and is best used when performing API functions on behalf of the active user.
-   **Administrative account**:  A system account can perform administrative functions on behalf of host users.  This method requires the username and password to be passed via XML.
-   **User accounts**:  A system account can perform functions only for its own account.  This method requires the username and password to be passed via XML.

&nbsp;

##  **Integration API Keys**

&nbsp;

In order to use the Webex Meetings APIs, you need to preregister an API key and then use the HM256 algorithm to generate a JWT token to access a Webex anonymous API (e.g., GetSessionInfoAgg, GetAllSitesByEmailAgg).

To apply for an API key, visit https://api.webex.com/gapi/registerapikey.

&nbsp;

##  **Webex XML APIs**

&nbsp;

The Webex XML model utilizes the exchange of well-formed XML documents to deploy messages.  Each of these relates to a specific Webex operation.  An XML request document specifies the desired action of the particular service's elements.  The XML response document returned by the Webex XML server describes the revised state of that service, as determined by the Webex XML Server.

The Webex XML server can baccessed at https://api.webex.com/WBXService/XMLService.

&nbsp;

##  **Creating a New Meeting**

&nbsp;

The CreateMeeting API enables users to schedule a meeting.  This API returns a unique meeting key for the session.

**Table 10-14** Creating or Scheduling a Webex Meeting

| Method | API | Description |
| -- | -- | -- |
| POST | <pre>https://api.Webex.com/WBXService/XMLService<br>with XML body:<br>\<body><br>  \<bodyContent xsi:type="java:com.Webex.service.binding.meeting.CreateMeeting"><br>    \<metaData><br>      \<confName>Branding Meeting\</confName><br>    \<metaData><br>    \<schedule><br>      \<startDate/><br>    \</schedule><br>  \</bodyContent><br>\</body> | Create a new meeting with various attributes such as name, start time, password, and attendees. |

**Example 10-14** *Creating a New Meeting Using the CreateMeeting API*

```
curl -X POST \
  https://api.Webex.com/WBXService/XMLService \
  -H 'cache-control: no-cache' \
  -H 'content-type: application/xml' \
  -d '<?xml version="1.0" encoding="UTF-8"?>
<serv:message xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance">
    <header>
        <securityContext>
            <WebexID>devasc</WebexID>
            <password>Kc5Ac4Ml</password>
            <siteName>apidemoeu</siteName>
        </securityContext>
    </header>
    <body>
        <bodyContent xsi:type="java:com.Webex.service.binding.meeting.
        CreateMeeting">
            <metaData>
                <confName>Branding Meeting</confName>
            </metaData>
            <schedule>
                <startDate/>
            </schedule>
        </bodyContent>
    </body>
</serv:message>'
```

&nbsp;

##  **Listing All My Meetings Meeting**

&nbsp;

*The **LstsummaryMeeting** API lists summary information for scheduled meetings.*  This API returns a unique meeting key for a session.

**Table 10-15** Listing All Webex Meetings That Match Certain Criteria

| Method | API | Description |
| -- | -- | -- |
| POST | <pre>https://api.Webex.com/WBXService/XMLService<br>with XML body:<br>\<body><br>  \<bodyContent xsi:type="java:com.Webex.service.binding.meeting.LstsummaryMeeting"><br>    \<order><br>      \<orderBy>STARTTIME\</orderBy><br>    \</order><br>  \</bodyContent><br>\</body></pre> | List all meetings that meet certain criteria |

**Example 10-15** *Listing All Meetings for a User by Using the LstsummaryMeeting API*

```
curl -X POST \
  https://api.Webex.com/WBXService/XMLService \
  -H 'cache-control: no-cache' \
  -H 'content-type: application/xml' \
  -d '<?xml version="1.0" encoding="UTF-8"?>
<serv:message xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance">
    <header>
        <securityContext>
            <WebexID>devasc</WebexID>
            <password>Kc5Ac4Ml</password>
            <siteName>apidemoeu</siteName>
        </securityContext>
    </header>
    <body>
        <bodyContent xsi:type="java:com.Webex.service.binding.meeting.
        CreateMeeting">
            <metaData>
                <confName>Branding Meeting</confName>
            </metaData>
            <schedule>
                <startDate/>
            </schedule>
        </bodyContent>
    </body>
</serv:message>'
```

&nbsp;

##  **Setting or Modifying Meeting Attributes**

&nbsp;

*The **SetMeeting** API enables host/users to update the information for a scheduled meeting that they are able to edit.*

**Table 10-16** Modify Meeting Attributes

| Method | API | Description |
| -- | -- | -- |
| POST | <pre>https://api.Webex.com/WBXService/XMLService<br>with XML body:<br>\<bodyContent xsi:type="java.com.Webex.service.binding.meeting.SetMeeting"><br>  \<meetingkey>625579604\</meetingkey><br>  \<participants><br>    \<attendees><br>      \<attendee><br>        \<person><br>          \<email>student@devasc.com\</email><br>        \</person><br>      \</attendee><br>    \</attendees><br>  \</participants><br>\</bodyContent></pre> | Update meeting attributes such as attendees, record meeting, schedules, and media support |

**Example 10-16** *Adding a New User to a Meeting by Using the SetMeeting API*

```
curl -X POST \
    https://api.Webex.com/WBXService/XMLService \
    -H 'cache-control: no-cache' \
    -H 'content-type: application/xml' \
    -d '<serv:message xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance">
    <header>
        <securityContext>
            <WebexID>devasc</WebexID>
                <password>Kc5Ac4M1</password>
                <siteName>apidemoeu</siteName>
            </securityContext>
        </header>
    <body>
        <bodyContent
            xsi:type="java:com.Webex.service.binding.meeting.SetMeeting">
            <meetingkey>625579604</meetingkey>
            <participants>
                <attendees>
                    <attendee>
                        <person>
                            <email>student@devasc.com</email>
                        </person>
                    </attendee>
                </attendees>
            </participants>
            <attendeeOptions>
                <emailInvitations>true</emailInvitations>
            </attendeeOptions>
            <schedule>
                <openTime>300</openTime>
            </schedule>
        </bodyContent>
    </body>
</serv:message>'
```

&nbsp;

##  **Deleting a Meeting**

&nbsp;

*The **DelMeeting** API allows hosts to delete a meeting that is not currently in progress.*

The API continues to use the POST method, but the XML data contains the operation of deleting the meeting.

**Table 10-17** Deleting a Webex Meeting Using the Meeting Key

| Method | API | Description |
| -- | -- | -- |
| POST | <pre>https://api.Webex.com/WBXService/XMLService<br>with XML body:<br>\<body><br>  \<bodyContent xsi:type="java:com.Webex.servvice.binding.meeting.DelMeeting"><br>    \<meetingKey>625579604\</meetingKey><br>  \</bodyContent><br>\</body> | Delete or cancel a meeting, given the meeting ID |

**Example 10-17** *Deleting a Meeting Using the DelMeeting API*

```
curl -X POST \
    -H 'cache-control: no cache' \
    -H 'content-type: application/xml' \
    -d '<serv:message xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance">
    <header>
        <securityContext>
            <WebexID>devasc</WebexID>
            <password>Kc5Ac4M1</password>
            <siteName>apidemoeu</siteName>
        </securityContext>
    </header>
    <body>
        <bodyContent
            xsi:type="java:com.Webex.service.binding.meeting.DelMeeting">
            <meetingKey>625579604></meetingKey>
        </bodyContent>
    </body>
</serv:message>'
```

&nbsp;

#   Webex Devices

&nbsp;

Webex Devices enables users to communicate and work with each other in real time.

These devices are fully programmable, and through embedded APIs (often referenced as ***xAPI***), you can extender and leverage Webex Room and Desk device capabilities in a number of ways:

-   Create user interface components to customize the meeting experience and control IoT devices such as lights, curtains, and projectors from the device controls interface
-   Configure devices that scale via automation scripts
-   Initiate or respond to calls automatically
-   Deploy code onto the devices without needing to deploy external control systems.

Webex Devices include the following devices:

-   ***Webex Board***
-   ***Room Devices***
-   ***Webex Desk Device***

&nbsp;

##  **xAPI**

&nbsp;

***xAPI*** is the API for collaboration endpoint software (***Cisco CE*** and ***RoomOS***) for both on-premises registered video conferencing devices (Unified CM and VCS) and devices registered to Cisco's cloud service (Cisco Webex Devices).

xAPI consists of four major groups:

-   Commands
-   Configurations
-   Status
-   Events

Table 10-18 shows the high-level API categories that xAPI supports.

**Table 10-18** xAPI Categories

| Method | API | Description |
| -- | -- | -- |
| GET | http://\<ip-address>/status.xml | Get the complete status of the device |
| GET | http://\<ip-address>/configurations.xml | Get the complete configuration of the device |
| GET | http://\<ip-address>/command.xml | Get the complete command set supported by the device |
| GET | http://\<ip-address>/valuespace.xml | Get an overview of all the value spaces used in the system settings, status information, and commands |
| POST | http://\<ip-address>/putxml | Configure any settings on the device |

&nbsp;

##  **xAPI**

&nbsp;

Access to xAPI requires the user to authenticate using ***HTTP basic access authentication*** as a user with the ***ADMIN*** role.  Unauthenticated requests prompt a 401 HTTP response containing a basic access authentication challenge.

If an application will be issuing multiple commands through xAPI, it is recommended that you use ***session authentication*** because the standard basic authentication does a full re-authentication per request, which may affect the performance of your application.

&nbsp;

##  **xAPI Session Authenticaiton**

To open a session, issue a ***POST*** to **`http://<ip-address>/xmlapi/session/begin`** with ***basic access authentication***.  The response sets a **SessionId-cookie** that can be used with subsequent requests.

Note it is important to explicitly close the session when using the API session authentication.

&nbsp;

##  **Creating a Session**

You can create a session by sending an xAPI session request to the endpoint. 

Example 10-18 shows a simple Python POST request, to which the server response with the session cookie.

**Example 10-18** *Python Script to Get a Session Cookie*

```python
""" Webex Device - Endpoint Status """

import requests

URL = "http://10.10.20.159/status.xml"
HEADERS = {
    'Cookie': "Session=c6ca2fc23d3f211e0517d4c603fbe4205c77d13dd6913c7bc12eef4085b7637b"
}

RESPONSE = requests.request("GET", URL, headers=HEADERS)
print(RESPONSE.text)
```

&nbsp;

##  **Registering an Event Notification Webhook**

&nbsp;

You can get a device or an endpoint to post HTTP event notifications (via webhooks) on changes to the API state.

These events are sent to the specified server URL and you can choose between event being posted in XML or JSON format.

You can subscribe to changes on multiple parts of the API by registering up to 15 different feedback expressions. 

The command for registering is **xCommand HttpFeedback**.

The HttpFeedback Register syntax is as follows:

```
FeedbackSlot: <1..4> ServerUrl(r): <S: 1, 2048> Format: <XML/JSON>
Expression: <S: 1, 255> Expression: <S: 1, 255> Expression: <S: 1, 255>
Expression: <S: 1, 255> Expression: <S: 1, 255> Expression: <S: 1, 255>
Expression: <S: 1, 255> Expression: <S: 1, 255> Expression: <S: 1, 255>
Expression: <S: 1, 255> Expression: <S: 1, 255> Expression: <S: 1, 255>
Expression: <S: 1, 255> Expression: <S: 1, 255> Expression: <S: 1, 255>
```

&nbsp;

##  **Room Analytics People Presence Detector**

&nbsp;

***People Presence*** shows day-to-day conference room usage analytics and helps you find available meeting rooms based on facial recognition and ultrasonic technology.  

xAPI allows you to turn on/off the detector via an API.

&nbsp;

#   Cisco Unified Communications Manager

&nbsp;

*Cisco **Unified Communications Manager Unified (Unified CM)** is the powerful call-processing component of the Cisco Unified Communications solution.  *

Unified CM supports the follow interface types:

-   Provisioning interfaces
-   Device monitoring and call control interfaces
-   Serviceability interfaces
-   Routing rules interfaces

&nbsp;

##  **Administrative XML**

&nbsp;

The ***Administrative XML (AXL)*** API provides a mechanism for inserting, retrieving, updating, and removing data from the Unified CM configuration database using an Extensible Markup Language (XML) Simple Object Access Protocol (SOAP) interface.

The AXL methods, referred to as ***requests***, are performed using a combination of HTTP and SOAP.

*SOAP is an XML **remote procedure call protocol (RPC)**.*

&nbsp;

##  **Cisco AXL Toolkit**

&nbsp;

When you download the AXL Toolkit and unzip the file, the schema folder contains AXL API schema files for supported AXL versions:

-   **AXLAPI.wsdl**:  WSDL file
-   **AXLEnums.xsd**:  Enum type definitions
-   **AXLSoap.xsd**:  Type definitions

One advantage of .xsd schema files is that they can be used to automatically/programmatically validate a particular XML document against the schema to ensure that it is well formatted and valid according to the schema specs.

Many XML editing applications and programmatic tools and components that use .xsd schema files to validate XML documents and details about how to do so may vary.  The main necessary detail, however, is to define the **xsi:schemaLocation** attribute with a URI pointing to the **axlsoap.xsd** schema file.

&nbsp;

##  **Accessing the AXL SOAP API**

&nbsp;

### ***Using the Zeep Client Library***

&nbsp;

### ***Using the CiscoAXL SDK***

The Python SDK is called CiscoAXL.

CiscoAXL is installed using the command: `pip install ciscoaxl` or `pip3 install ciscoaxl`