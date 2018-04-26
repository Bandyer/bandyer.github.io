---
# Page settings
layout: default
keywords:
comments: false

# Hero section
title: Bandyer basic concepts
description: Learn the basics of what Bandyer Integration is and how it works.

# Micro navigation
micro_nav: true

---

### The platform <a name="platform"></a>

The Bandyer platform makes it easy to embed real-time, high-quality interactive video, messaging, screen-sharing, 
and more into web and mobile apps. The platform includes client libraries for web, iOS, Android, 
as well as REST API. Bandyer uses WebRTC for audio-video communications.

**All applications built with the Bandyer platform require two primary components:**

- **The Client** — client-side code that runs in a browser or mobile app, set up by the developer 
using the Bandyer client-side libraries, which are available for Web, iOS, and Android. 
The client-side handles the majority of Bandyer functionality.
- **The Server** — server-side code executed on a web server set up by the developer using the Bandyer REST API.

### Calls <a name="calls"></a>

Every Bandyer video chat occurs within a call. You can think of a call as a “room” where clients can interact 
with one another in real-time. Call are hosted on the Bandyer cloud and manage user connections,
audio-video streams, and user events (such as a new user joining). Each call is associated with a unique call ID.
<!-- To allow multiple clients to chat with one another, you would simply have them connect to the same call 
(using the same call ID). -->

The client is responsabile for creating new calls from his client SDKs.
Clients connected to a call can publish streams and subscribe to other clients’ streams. 
For more info on how clients connect to a call, see the next section.


### Publishing and subscribing <a name="pubsub"></a>

<!-- qui dovrei spiegare anche il dialing -->
This section provides the steps required for two clients to initiate a video chat call.

**Step 1: Client authentication**

The client connects to Bandyer Server and send his credential (appId and userAlias). After that, he's ready to create a 
call.

**Step 2: The call is created by the client**

Your client (Client 1), using Bandyer SDKs, creates a call with one or more users and receives the callID and the credentials needed to join the call.
At this point, the client is occupied.

**Step 3: The call is received by the others users**

The users within the created call (*Step 2*) receives the event of *Incoming Dial*. The client uses that info to perform
the answer or decline actions. If the client answers, he will receive the info needed to establish a connection to the 
specified call.

![bandyer_sdk_dial_flow](https://s3-eu-west-1.amazonaws.com/static.bandyer.com/corporate/images/docs/bandyer_sdk_dial_flow.png)


**Step 4: The clients subscribe to each other’s streams**

Now that it’s connected to the call, Client 2 can subscribe to Client 1’s stream. 
Client 2 then publishes its own video stream to the call, and Client 1 subscribes to it. 
Both clients are now subscribed to each other's stream in a one-to-one video chat,
and both are “listening” for new events (such as a new user connecting the call).

![bandyer_sdk_pubsub](https://s3-eu-west-1.amazonaws.com/static.bandyer.com/corporate/images/docs/bandyer_sdk_pubsub.png)

Bandyer supports one-to-one communication and conference call. 
Multiple clients can connect to a call and each connected clients can subscribe to each stream in the call. 
In addition to the basic functionality above, the Bandyer platform provides a variety of additional features such as 
screen-sharing, text chat, collaborative space, and more. 
<!-- To see the complete set of features offered,see the developer guides. -->

<!-- IMMAGINI DEL PUBLISH SUBSCRIBE -->
<!-- DIRE CHE NEL WEB E' AUTOMATICO -->

### Vocabolary

**Call**

You can think of a call as a "room" where clients can interact with one another in real-time. Clients can 
publish streams and subscribe to streams in the call, as well as listen for events dispatched by the call 
(such as a new user connecting).

---

**Dial**

The dial concept is the signaling process fired after a call request. When the client creates a call between another clients 
(for example Client 2), every client receive a *Incoming Dial* event. After that, the clients can choose to answer 
(they will obtain the credential to access the call) or decline the call.

---

**Answer**

The answer concept is the *action of answering* a *Incoming Dial* received. The clients who receives the *Incoming Dial*
event can answer the call received.

---

**Decline**

The decline concept is the *action of declining* a *Incoming Dial* received. The clients who receives the *Incoming Dial*
event can decline the call received.

---

**Publish**

Once a client is connected to a call, it can publish an audio-video stream to the call using the device’s webcam
and microphone.

---

**Subscribe**

Once a client is connected to a call, it can subscribe to any audio-video streams published by other clients
in the call.

---

**Events**

Once a client establishes a connection to a call, it is able to listen for events dispatched by the call.
Events are dispatched for a variety of reasons, such as a new stream being created or a new client connecting or
disconnecting from the call. If you want a client to react to a certain event, you must set up an event listener.
For information on the various events that can occur during a call and how to handle them,
check out the client SDK reference docs for web (JavaScript), iOS, and Android.

---


**Client SDK**

The client SDKs are a set of code libraries available for web (JavaScript), iOS, Android, used to set up the client. 
The client-side code handles the majority of Bandyer functionality, including publishing and subscribing to streams 
in the call and listening for call events.

---

**Bandyer REST API**

The Bandyer REST API is an HTTP interface with the Bandyer Cloud used to create calls and handle advanced features
such as archiving and broadcast. The Bandyer server SDKs implement many of the methods of the REST API. 
Check out the REST API reference docs to learn the various methods available.
