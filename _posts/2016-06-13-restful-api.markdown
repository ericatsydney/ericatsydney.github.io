---
layout: post
title:  "Janrain API study"
date:   2016-06-03 21:30:52 +1000
categories: Programming
---
When we use API to work, the authentication is the first / most important thing.
As the API need authorization, OAuth2.0 is involved.
[OAuth2.0 Chinese reference](http://www.ruanyifeng.com/blog/2014/05/oauth_2_0.html)

[Linked Restful API](https://developer.linkedin.com/docs/rest-api)

Janrain
session = access token

responsive type = token and code


url stand for the resources
client to server
use post/get/delete/put to change the presentation layter




Wechat scan QR code to login on desktop:
1. Visit desktop website, unique ID is generated as QR code.
2. Open Wechat on mobile, scan QR code.
3. Authenticate login on mobile, Wechat App send Wechat ID and unique ID to server.
4. Sever grant authority on desktop.