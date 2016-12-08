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
|----------|:-------------:|
|\__LINE\__|	Good for debugging with var_dump().|
|\__FILE\__|	The full path and filename of the file with symlinks resolved. If used inside an include, the name of the included file is returned.|
|\__DIR\__|	The directory of the file. If used inside an include, the directory of the included file is returned. This is equivalent to dirname(\__FILE\__). This directory name does not have a trailing slash unless it is the root directory.|
|\__FUNCTION\__|	The function name.|
