---
layout: post
title:  "Redux Insight"
date:   2019-05-03 14:10:00 +1000
categories: Geek
---

Core Concepts
==============

*Actions*
Actions are used to tell Redux that something in an application has changed, or that the user has interacted with the application in some way. Actions in Redux are plain objects with a `type` property.

*Reducers*
In Redux, reducers are used to facilitate state transformations based on actions. It use current state and action object to compute a new state.

{% highlight shell%}
# compress text, html, javascript, css, xml:
AddOutputFilterByType DEFLATE text/plain
AddOutputFilterByType DEFLATE text/html
AddOutputFilterByType DEFLATE text/xml
AddOutputFilterByType DEFLATE text/css
AddOutputFilterByType DEFLATE application/xml
AddOutputFilterByType DEFLATE application/xhtml+xml
AddOutputFilterByType DEFLATE application/rss+xml
AddOutputFilterByType DEFLATE application/javascript
AddOutputFilterByType DEFLATE application/x-javascript

# Or, compress certain file types by extension:
<files *.html>
SetOutputFilter DEFLATE
</files>
{% endhighlight %}
