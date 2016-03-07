---
layout: post
title:  "Denpendency Injection"
date:   2016-03-05 22:00:52 +1000
categories: Promgramming
---

不知道service provider和service container，就等于没有很好地理解Laravel.

开始对这两个概念很模糊，但看到sitepoint上这篇<a target="_blank" href='http://www.sitepoint.com/dependency-injection-laravels-ioc/'>博客</a>之后就茅塞顿开。

如果说概念，service provider就是提供全局服务的类，service container是一个service provider的注册系统，用来记录哪些类／接口需要使用了service provider。

Dependency Injection是一种很好的解耦方法，也另单元测试成为可能，她用参数形式来解释了应用与服务之间的关系，Laravel还能方便地使用php的reflection功能，自动实现类的实例化。

 像这个列子：
{% highlight php %}
TBC
{% endhighlight %}

当服务类是一个接口时，Laravel就用service container（IOC／反向控制）来进一步地解释/搭建他们的关系。

 像下面的例子：

{% highlight php %}
App:bind( 'SessionStorage', 'MysqlSessionStorage' );
{% endhighlight %}
