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

In the `on` function, we could use object to define multiple events.
{% highlight js%}
  $(document).on({
  'event1': functionReference2,
  'event2': functionReference2,
  'event3': functionReference3
  })
{% endhighlight %}


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
- `once()` is a plugin of jQuery:
{% highlight javascript%}
// The following will change the color of each paragraph to red, just once
// for the "changecolor" key.
$('p').once('changecolor').css('color', 'red');
{% endhighlight %}

- while `one()` is a jQuery function, it attach a handler to an event for the elements, and the handler will be executed once per element per event type.
{% highlight javascript%}
// .one(events, handler)
$( "#foo" ).one( "click", function() {
  alert( "This will be displayed only once." );
});
{% endhighlight %}

bind vs proxy
=============

js handler pass the data
========================

ready vs attach
===============

event vs callback function
==========================

type casting
============
{% highlight js%}
(string) variable1
{% endhighlight %}

