---
layout: post
title:  "Restful API"
date:   2016-06-13 21:30:52 +1000
categories: Programming
---
When I study Restful API, I found [Linked Restful API](https://developer.linkedin.com/docs/rest-api) documentation is very easy to understand.

Authentication
================

When we use API to work, the authentication is the first or the most important thing we need to finish. OAuth2.0 is the industry standard and quite easy to implement.

Here's an article about [OAuth2.0](http://www.ruanyifeng.com/blog/2014/05/oauth_2_0.html) in chinese.
 
- Preparation: Create `client ID` and `client secret`.

- Step 1,2: Use `client ID` and `CSRF secret` to get `authorization code`. (from Resource Owner to App Server, user need to fill in their credential)

- Step 3,4: Use `authorization code`, `client ID` and `client secret` to get `access token` (from App Server to Service API).

- Step 5,6: Start making authenticated request including `access token` in the header, communicating with Linkedin server on behalf of user (from client to Linkedin).

![flow chart](/assets/slack_oauth_flow_diagram@2x.png)


Restful API

- url stand for the resources

- client to server

- use post/get/delete/put to change the presentation layter

Janrain

session = access token

responsive type = token and code

P.S. Wechat scan QR code to login on desktop:

1. Visit desktop website, unique ID is generated as QR code.

2. Open Wechat on mobile, scan QR code.

3. Authenticate login on mobile, Wechat App send Wechat ID and unique ID to server.

4. Sever grant authority on desktop.