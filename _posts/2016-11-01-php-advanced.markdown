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

Magic Variable
===============
|Name	| Description |
|----------|:-------------:|
|__LINE__|	Good for debugging with var_dump().|
|__FILE__|	The full path and filename of the file with symlinks resolved. If used inside an include, the name of the included file is returned.|
|__DIR__|	The directory of the file. If used inside an include, the directory of the included file is returned. This is equivalent to dirname(__FILE__). This directory name does not have a trailing slash unless it is the root directory.|
|__FUNCTION__|	The function name.|
