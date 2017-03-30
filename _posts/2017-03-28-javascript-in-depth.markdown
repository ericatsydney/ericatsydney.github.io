---
layout: post
title:  "Javascript in depth"
date:   2017-03-28 21:00:00 +1000
categories: Geek
---

Prototype
=========
Most of the Javascript code are objects, but interestingly Javascript do not have class concept. Instead it will use `prototype`. 

When we define a constructor function below like that, an `object prototype` is created. Anything defined in `prototype` can be accessed by all the instances.

{% highlight javascript%}
var Object = function(a, b) {
  this.attributeA = a;
  this.attributeB = b;
}
{% endhighlight %}

When we define a method within `prototype`, it can be access by all the instances (they are objects as well, so confusing). And it's static as well.
{% highlight javascript%}
Object.prototype.methodA = function() {
  // Logic goes here.
}
{% endhighlight %}

More details please check this [Codepend](https://codepen.io/eric_tan/pen/OpBqJp).

Callback function
=================



Hosting
=======

Mis-understanding `hosting` will cause some error difficult to detect.

And I think this concept is quite unique/ odd behaviours exist in Javascript ONLY.

This is a [stackoverflow link](http://stackoverflow.com/questions/7609276/javascript-function-order-why-does-it-matter)  have sample and detail explanation about `hosting`. 


