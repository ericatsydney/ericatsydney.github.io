---
layout: post
title:  "API Best Practices"
date:   2020-03-03 09:55:00 +1000
categories: Geek
---

Define the url as resource using pluralized nouns but not verb, use sub resource for relations.

Use the correct http method for CRUD, e.g. don't use get method to update. 

But because of the `get` method's limitation, there are some violations:

- When try to retrieve resource using complex data structure, we will use `post` and put the data in body.

- When try to retrieve batch resources, we can use something like this `students?ids=12345, 81999, 1222`

URL pattern should be consistent across the different environments.

Use the correct response code, e.g. don't use 200 to return any error response.










