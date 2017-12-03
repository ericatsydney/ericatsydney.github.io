---
layout: post
title:  "Website Performance Optimization"
date:   2017-12-03 21:10:00 +1000
categories: Geek
---

Tools
==============
Google: page speed

Webpagetest

Speedcurve

Chrome 
 - Performance: can check the perfomrance summary as pie chart, time line, call tree. 
 - Network: can check the number of requests, status, file size(total), loading time by file type.

Concepts
==============
First Byte Time - This metrics mean the time when browser receive fist bit of the server response. Usually refer as the `backend time` i.e. the time server spent to build the page for user.

Keep Alive Enable - reuse the existing connection, config on server.

Start Render - User can see something like background color or any other indicator.

Document Complete - This metrics mean the main page is loaded, i.e. after all the image loaded but not include the javascript execution.

Fully Loaded - This metrics means after 2 sec if no more activity after main page is loaded.

Compress(text) Enable - server configuration, as the (css, js) text resource are downloaded in the begining of the page, so make this kind of data smaller have bigger impact than image.

Compress Image - make sure the image quality not too high, jpg could be compressed a lot without losing visual quality.

How to enable file compression 
=========
Basically, it's a web server configuration. Different type of webserver has different setting.

Like Apache, we can do it like this
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
