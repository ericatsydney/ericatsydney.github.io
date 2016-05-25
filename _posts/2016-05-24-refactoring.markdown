---
layout: post
title:  "重构"
date:   2016-05-24 7:05:52 +1000
categories: Programming
---

PHP based on Drupal:
- setup variable, and admin form
- template file: use framework class, with BEM syntax
- use `include` to import separate file
- use array to organize the relations (implode, array_map)
- use block to put multiple template together

SASS:
setup sass, rb file


JS:
- once vs one
- change file name, use this pattern: [module].[function].js
- separate file according to the function, e.g. setting, eventHandler, utility, main

{% highlight js %}
defaultSetting = {
  variable1: value1,
  variable2: value2,
  // More variables .....
}
{% endhighlight %}

- short hand name, object notation, foreach to simplify logic
{% highlight js %}
defaultSetting = {
  variable1: value1,
  variable2: value2,
}
{% endhighlight %}



Devops, Data Structure, Style Practise, React, Restful API, CSS box model in-depth

Again, syntax basic array, object