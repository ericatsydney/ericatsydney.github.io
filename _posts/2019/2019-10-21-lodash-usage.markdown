---
layout: post
title:  "Lodash Usage"
date:   2019-10-21 14:10:00 +1000
categories: Geek
---

Lodash is very useful to control and manipulate the data structure, no mater it's an array or object or string, lodash is your good friend.

Here are some use case I encounter in the real world project. Put them here for future reference:

Case 1: get all the key of true value
=======================================
{% highlight js%}
  let types = {'house': true, 'apartment': false, 'townhouse': true};
  let keys = _.keys(_.pickBy(types)); // return ['house', 'townhouse']
{% endhighlight %}
