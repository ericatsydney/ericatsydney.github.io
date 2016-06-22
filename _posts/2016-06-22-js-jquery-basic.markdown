---
layout: post
title:  "Javascript and jQuery"
date:   2016-06-22 22:30:52 +1000
categories: Programming
---

this is mystry
==============

`this` is the value of the object that invoke the function where `this` is used. 

- `this` refers to the global object in the following cases:

  - in the outermost context, outside of any function block

  - in functions that are not methods of objects

  - in functions that are not object constructors

- When a function is called as a property on a parent object, this refers to the parent object.

- When a function is called using call() or apply(), or bind(), this refers to the first argument passed to these methods. If the first argument is null or not an object, this refers to the global object.

event
=====

Use `trigger` and `on` to throw and catch the event.


unbind
======

unbind's drawback

Solution is chain `once` and `on` to attach function only once.
{% highlight javascript%}
  $selector.once().on('eventName', function() {
    //callback function.
  });
{% endhighlight %}

