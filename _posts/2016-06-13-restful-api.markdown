---
layout: post
title:  "Restful API - OAuth"
date:   2016-06-13 21:30:52 +1000
categories: Geek
---
When I study Restful API, I found [Linked Restful API](https://developer.linkedin.com/docs/rest-api) documentation is very easy to understand.

Authentication
================

When we use API to work, the authentication is the first or the most important thing we need to finish. OAuth2.0 is the industry standard and quite easy to implement.

- Step 1: Resource owner raise a authentication request to client, then client will redirect resource owner to authentication server(not show in this chart). 

- Step 2: After resource owner grant authority(need to fill in credential), owner will be redirected back to the client with `authorization code`.

- Step 3,4: Then client server will talk to service API directly. Client use `authorization code`, `client ID` to get `access token`.

- Step 5,6: Communicate with the resource server on behalf of user, making authenticated request with `access token` in the header.

![flow chart](/assets/slack_oauth_flow_diagram@2x.png)

Reference:

- [Slack Authentication](https://api.slack.com/docs/oauth)

- [Linkedin Authentication](https://developer.linkedin.com/docs/oauth2) 

- Here's an article about [OAuth2.0](http://www.ruanyifeng.com/blog/2014/05/oauth_2_0.html) in chinese.

Restful API
===========

After athentication, we could start using the API to control the resource.

- [Twitter API](https://dev.twitter.com/rest/reference/get/direct_messages) 

- [Linkedin API](https://developer.linkedin.com/docs/rest-api) 

- url stand for the resources

- client to server

- use post/get/delete/put to change the presentation layter

Janrain study
=============

session = access token

responsive type = token and code

P.S. Wechat scan QR code to login on desktop:

1. Visit desktop website, unique ID is generated as QR code.

2. Open Wechat on mobile, scan QR code.

3. Authenticate login on mobile, Wechat App send Wechat ID and unique ID to server.

4. Sever grant authority on desktop.