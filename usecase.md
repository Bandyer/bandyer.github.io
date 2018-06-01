---
# Page settings
layout: default
keywords:
comments: false

# Hero section
title: Bandyer use case
description: Learn how to empower your app with voice and video with Bandyer cloud infrastructure and powerful SDKs.

# Micro navigation
micro_nav: true

---

## Bandyer interaction with an CTI and customer care service

Bandyer **Communication Center** dispatches all the events of the user presence to the CTI through Bandyer Web Hooks. The CTI solution will update the presence of the user handling the free agents and forwardin them to the client.

An example of the flow:

![bandyer_sdk_cti_flow](https://s3-eu-west-1.amazonaws.com/static.bandyer.com/corporate/images/docs/Bandyer+sdk+cti+flow.png) 

The CTI system will create the the session and find an available advisor for client. When the two clients are ready to initialize the Bandyer call, the CTI will create
a Bandyer Call using the Bandyer REST API or Bandyer SDK's.

## Bandyer integrations with banks and financial advisor system

In this scenario, we assume that the financial advisor knows his clients. Using the Bandyer SDK's you can connect the two participants (advisor and client) directly in your
website or mobile app. The Bandyer SDK's will send a notification to the company server using the Bandyer WebHooks. Flexible REST API and Web Hooks gives you control over when a Call is created and completed, enabling you to integrate video call creation into your existing business workflows. Webhooks let you easily integrate video to your business workflows.

An example of the flow:

![bandyer_sdk_bank_advisor_flow](https://s3-eu-west-1.amazonaws.com/static.bandyer.com/corporate/images/docs/Bandyer+sdk+bank+advisor.png) 

If you need a record of your call, you can record live audio and video sessions for playback or archiving. Easily convert and compose captured audio and video tracks to the file format and layout of your choice.

