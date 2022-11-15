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