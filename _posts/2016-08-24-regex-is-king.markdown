---
layout: post
title:  "Regex is the King"
date:   2016-08-24 7:05:52 +1000
categories: Geek
---

Regex is so powerful to search any pattern you want, and it can used in almost every language.

However, considering the performance, try to use the simple replace / search if not necessary. 

e.g. in php, we will use `str_replace` to replace the simple string rather than using `preg_replace`.

In the folliwng snippet, we can see most of regex syntax is quite consistent across different languages. Only the delimiter is not the same.

Use in Shell
============
{% highlight shell%}
# \ back slash is the escape character.
# () parentheses is the sub expression
# [] square bracket match any character inside
# ^ caret inside square bracket mean except, but outside mean begin with 
ag '\$conf\[(.+)\]' ./**/*.php
{% endhighlight %}

Use in JS
=========
In JS, we can use regex with forward slash as the literal notation.

{% highlight js%}
pattern = \(.*)Key Word(.*)\;
{% endhighlight %}
 
Use in PHP
==========
{% highlight php%}
// / forward slash is the delimiter here.
// \ back slash is the escape character
pattern = '/(\s*)Key Word(.*)/'
{% endhighlight %}

