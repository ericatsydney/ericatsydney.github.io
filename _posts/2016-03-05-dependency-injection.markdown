---
layout: post
title:  "Denpendency Injection"
date:   2016-03-05 22:00:52 +1000
categories: Promgramming
---

Inspired by <a href='http://www.sitepoint.com/dependency-injection-laravels-ioc/'>this blog</a>

当看Laravel文档时，一定会看到service provider和service container.

开始对这两个概念很模糊，但看到sitepoint上这篇博客之后就茅塞顿开。

service provider是提供全局服务的类，service container是一个提供使用service provider的等级系统。

Dependency Injection用参数形式来解释了应用类与服务类之间的关系， 当服务类是一个接口时，Laravel就用service container（IOC）来进一步地解释/搭建他们的关系。

 请看下面的例子：

{% highlight php %}
App:bind( 'SessionStorage', 'MysqlSessionStorage' );
{% endhighlight %}
