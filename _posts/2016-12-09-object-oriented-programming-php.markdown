---
layout: post
title:  "PHP - OOP"
date:   2016-12-09 15:47:52 +1000
categories: Geek
---

Namespace
=========
Namespace is the way to avoid the name collision. `namespace`, `use` and `as` are the keywords we use Namespace. The following is an example to show how to use the namespace. 

{% highlight php%}
// Define
namespace App\Lib

// Call
require_once('lib.php');
echo \App\Lib\FunctionName();

// Import namespace
use App\Lib;
require_once('lib.php');
echo Lib\FunctionName();

// Namespace Alias
use App\Lib as L;
require_once('lib.php');
echo L\FunctionName();
{% endhighlight %}

Autoloading Namespaced Classes
==============================
This is an example to show how auto loading works

\classes\App\Lib1\MyClass.php
{% highlight php%}
<?php
namespace App\Lib1;

class MyClass {
	public function WhoAmI() {
		return __METHOD__;
	}
}
?>
{% endhighlight %}

myapp.php:
{% highlight php%}
<?php
use App\Lib1\MyClass as MC;

$obj = new MC();
echo $obj->WhoAmI();

// autoload function
function __autoload($class) {

	// convert namespace to full file path
	$class = 'classes\' . str_replace('\\', '/', $class) . '.php';
	require_once($class);

}
?>
{% endhighlight %}

PSR-4 Autoloader
================
All the key word `require`, `include` or customized function `__autoload` try to fix autoload problem, but we still need a solution which is scallable and standardized, so all the framework and components can work well together. This is the purpose why PSR-4/Autoloader was designed.

> The essensce of PSR-4 is mapping a top-level namespace prefix to a specific filesystem directory.

:: Operator
=====
Double colon operator allow access to static, constant and overriden method of a class.

Interface vs Abstract Class
===========================
TBC

Credit:
Moden PHP
