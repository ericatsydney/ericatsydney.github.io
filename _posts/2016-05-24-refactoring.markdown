---
layout: post
title:  "重构"
date:   2016-05-24 7:05:52 +1000
categories: Programming
---

JS:

- Change file name to use this pattern: [module].[some]-[function].js

- Change variable name to camel case.

- Split files according to different purpose: main logic, default setting, implementation, utility, event sequence

- Use object literal to setup variable, so we could use jQuery `extend` function to override the configuration in the future.
{% highlight js %}
defaultSetting = {
  variable1: value1,
  variable2: value2,
  // More variables .....
}

$.extend(defaultSetting, overrideSetting)
{% endhighlight %}

- DRY: use object notation, callback function name, jQuery `each` function to simplify logic and decouple module
{% highlight js %}
eventHandlers = {
  event1: callBack1,
  event2: callBack2,
}

$.each(eventHandlers, function(eventName, callback) {
  janrain.events[eventName].addHandler(callback);
});
{% endhighlight %}

PHP based on Drupal:

- setup variable, and admin form

- template file: use framework class, with BEM syntax

- use `include` to import separate file

- use array to organize the relations (implode, array_map)

- use block to put multiple template together

SASS:

- setup sass, rb file


Devops, Data Structure, Style Practise, React, Restful API, CSS box model in-depth
