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
Name	Description
__LINE__	The current line number of the file.
__FILE__	The full path and filename of the file with symlinks resolved. If used inside an include, the name of the included file is returned.
__DIR__	The directory of the file. If used inside an include, the directory of the included file is returned. This is equivalent to dirname(__FILE__). This directory name does not have a trailing slash unless it is the root directory.
__FUNCTION__	The function name.
__CLASS__	The class name. The class name includes the namespace it was declared in (e.g. Foo\Bar). Note that as of PHP 5.4 __CLASS__ works also in traits. When used in a trait method, __CLASS__ is the name of the class the trait is used in.
__TRAIT__	The trait name. The trait name includes the namespace it was declared in (e.g. Foo\Bar).
__METHOD__	The class method name.
__NAMESPACE__	The name of the current namespace.
