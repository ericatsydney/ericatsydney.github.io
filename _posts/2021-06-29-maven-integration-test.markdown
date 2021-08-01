---
layout: post
title:  "Maven integration test"
date:   2021-06-29 19:45:00 +1000
categories: Geek
---

Nowadays unit test usually is the Must-Have for most of the development, it helps to make sure the new feature will not break the existing logic.

Integration test is another layer checking to make sure the feature is working from user point of view. It fail any defected changes and give us a chance to fix before deployment.

So the sequence of the maven stage will be:

- clean
- validate
- compile
- `test`
- package
- `verify`
- install
- site
- deploy

For testing, we usually use Junit as the framework, which can help us write test (with annotation), run test and format the test results.

When we run unit test, we use surefire plugin, while we use `failsave` plugin for the integration test.

In order to run unit test and integration in different stages, we can use the naming convention to indicate the 2 use case.

In failsafe configuration, we can use

{% highlight java%}

<includes>
   <include> **/*IT.java</include>
</includes>

{% endhighlight %}

{% highlight java%}

In surefire we use the opposite config
<excludes>
   <exclude> **/*IT.java</exclude>
</excludes>

{% endhighlight %}

