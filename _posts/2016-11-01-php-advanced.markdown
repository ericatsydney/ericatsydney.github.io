---
layout: post
title:  "php advanced"
date:   2016-11-01 7:40:52 +1000
categories: Geek
---

Callable function as variable
==========================
{% highlight php%}
  // Execute the screen specific preprocess function.
  $preprocess_func = 'sample_module_preprocess_screen__' . $screen;
  if (is_callable($preprocess_func)) {
    $preprocess_func($variables);
  }
{% endhighlight %}

Magic Variables
===============
These are the magic variables I used a lot in php coding.

|Name	| Description |
|----------|:-------------|
|\_\_LINE\_\_|	Good for debugging with var_dump().|
|\_\_FILE\_\_|	The full path and filename.|
|\_\_DIR\_\_|	The directory of the file.|
|\_\_FUNCTION\_\_|	The function name.|


Closures
=======
Closures is the anonymous function in PHP. We can use it in the callback.

{% highlight php%}
$greetings = array_map(function($name) {
  return 'Hello ' . $name;
}, ['John', 'Eric', 'Josh']);

print_r($greetings);
{% endhighlight %}

