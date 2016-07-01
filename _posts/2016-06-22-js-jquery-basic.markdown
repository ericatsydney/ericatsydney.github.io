---
layout: post
title:  "Javascript and jQuery"
date:   2016-06-22 22:30:52 +1000
categories: Programming
---

`this` is a mystry
==================

`this` is the value of the object that invoke the function where `this` is used. It could be

- global object `window`.

- the DOM element bound to call back function.
  
- the name space (parent object) define function reference.

When a prototype function is called using `call()` or `apply()`, or `bind()`, this refers to the first argument passed to these methods. 

Use event to decouple
=====================

Use `trigger` and `on` to throw and catch the event, rather than call function in different file directly. 
 
The jQuery `on` function is not compatible against version under 1.7.

unbind
======
unbind's drawback ??????

Solution is chain `once` and `on` to attach function only once.
{% highlight javascript%}
  $selector.once().on('eventName', function() {
    //callback function.
  });
{% endhighlight %}

once vs one
===========

bind vs proxy
=============

js handler pass the data
========================

ready vs attach
===============


event vs callback function
==========================
