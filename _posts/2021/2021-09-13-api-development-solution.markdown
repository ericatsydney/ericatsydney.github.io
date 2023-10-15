---
layout: post
title:  "API Development"
date:   2021-09-13 21:32:00 +1000
categories: Geek
---

If we want to build a web application, we can use `spring-boot-starter-web` as the dependency.

It will include all the necessary libs for us, for example by default it will use the Jackson to marshall and unmarshall the request and response.

Labs [Test setup unmarshall/marshall message]

DTO: use one object (DTO) to aggregate the data that would have been transferred by multiple calls, by doing this just one call can get the result we want.

ModelMapper can help to convert between the entiy and DTO.  