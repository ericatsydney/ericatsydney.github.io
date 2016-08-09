---
layout: post
title:  "Javascript and jQuery"
date:   2016-06-22 22:30:52 +1000
categories: Programming
---
Does order matter in JS?
===========

Put it on top, as the mis-understanding `hosting` will cause some error how to detect.

When I read the book "xxxx", I thought it's useless feature. But in the daily programming, I found it's so important.

Yes, I agree with it's quite unique/ odd behaviours exist in Javascript ONLY.

This is a [stackoverflow link](http://stackoverflow.com/questions/7609276/javascript-function-order-why-does-it-matter)  have sample and detail explanation about `hosting`. 

Regex in JS
===========
Use the literal notation to create regex `\^Begin\` rather than the `new RegExp()`.

This is the some useful sample.

{% highlight js%}
var startPattern = \^Begin\?
    endPattern = \^Begin\,
    .....
{% endhighlight %}

Ternary statement
=================
Only use for a very simple / short logic.
{% highlight js%}
var a;
a = (b > c) ? b : c;
{% endhighlight %}

Namespace
=========
Use object literal to create the namespace
{% highlight js%}
var name.space = {
  setting1: value1,
  setting2: value2,
  fooMethod: function() {
  },
  barMethod: function() {
  }
}
console.log(name.sapce.fooMethod());
{% endhighlight %}

this is a mystry
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
  bindEvent: function() {
    $(document).on({
      'event1': eventHandler1,
      'event2': eventHandler2,
      'event3': eventHandler3
    });
  },
  eventHandler1: function() {
  },
  eventHandler2: function() {
  },
  eventHandler3: function() {
  },
{% endhighlight %}

Type Conversion
===============
{% highlight js%}
// Convert the object name to string, so that we could reuse that in bracket notation.
$.each(nameSpace.events, function(event) {
  if (typeof nameSpace.events[String(event)].functionName === 'function') {
    nameSpace.events[String(event)].functionName();
  }
}
{% endhighlight %}

Avoid to use unbind
===================
The drawback of `unbind` is ??????.

And the solution is chain `once` and `on` to attach function only once.
{% highlight javascript%}
  $selector.once().on('eventName', function() {
    //callback function.
  });
{% endhighlight %}

Function once vs one
====================
- `once()` is a plugin of jQuery:
{% highlight javascript%}
// The following will change the color of each paragraph to red, just once
// for the "changecolor" key.
$('p').once('changecolor', function() {
  this.css('color', 'red');
}
{% endhighlight %}

- while `one()` is a jQuery function, it attach a handler to an event for the elements, and the handler will be executed once per element per event type.
{% highlight javascript%}
// .one(events, handler)
$( "#foo" ).one( "click", function() {
  alert( "This will be displayed only once." );
});
{% endhighlight %}

Event ready vs attach
=====================
The `ready` event is fired when the full DOM has been loaded. This event is only fired once per page.

The `attach` event on the other hand is fired by **Drupal** whenever the DOM changes in response to an AJAX callback or similar event.

Event handler vs Callback function
==================================
When we use '$.on()' function, we could use either event handler or callback function. And we can pass the arguments to the call back function.

{% highlight js%}
$(document).on('event1', function() {
  // logic goes here.
});

// When use event handler, remember to drop the parentheses.
$(document).on('event2'', eventHandler2);

eventHandler2 = function(event, arg) {
  // logic goes here.
};
$('#id').trigger('event2', arg);
{% endhighlight %}

Function bind vs proxy
======================
Here the `prototype.bind` function is not the same as `$().bind` function, it will pass the object to the function's `this` variable. It is the similar as `$().proxy`.
{% highlight js%}
  var $container = $(this.productContainer);
  // pass the `this` to bindEvents, so in the bindEvents function
  // it will get the nameSpace scope but not the $container. 
  $container.once('shortlist_page', this.bindEvents.bind(this));
{% endhighlight %}

Reserved keyword arguments
==========================
`arguments` is a reserved keyword for a object given to every function scope.

False value in JS
=================
- Objects evaluate to true

- Undefined evaluates to false

- Null evaluates to false

- Booleans evaluate to the value of the boolean

- Numbers evaluate to false if +0, -0, or NaN, otherwise true

- Strings evaluate to false if an empty string '', otherwise true

{% highlight js%}
if ([0]) {
  // true
  // An array is an object, objects evaluate to true
}
{% endhighlight %}


