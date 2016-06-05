---
layout: post
title:  "重构"
date:   2016-05-24 7:05:52 +1000
categories: Programming
---

Java Script
===========

- Change file name to use this pattern: [module].[some]-[function].js.

- Change variable name to camel case.

- Split files according to different purpose: main logic, default setting, implementation, utility, event sequence.

- Use object literal to setup variable, so we could use jQuery `extend` function to override the configuration in the future.
{% highlight js %}
defaultSetting = {
  variable1: value1,
  variable2: value2,
  // More variables .....
}

$.extend(defaultSetting, overrideSetting)
{% endhighlight %}

- DRY: use object literal to organize code

**Example 1:** callback function name, jQuery `each` function to simplify logic and decouple modules.
{% highlight js %}
eventHandlers = {
  event1: callBack1,
  event2: callBack2,
}

$.each(eventHandlers, function(eventName, callback) {
  janrain.events[eventName].addHandler(callback);
});
{% endhighlight %}

**Example 2:** Use object literal to replace switch, it could better the performance.
{% highlight js %}
conditions = {
  condition1: 'result1',
  condition2: 'result2',
  ....
}

if (conditions.hasOwnProperty(value) {
  returnResult = conditions[value];
})
else {
  returnResult = defaultResult;
}
{% endhighlight %}

**Example 3:** Use object literal to create DOM
{% highlight js %}
$dom = $.create('<div />', {
  attribute1: 'value1',
  attribute2: 'value2',
  attribute3: 'value3',
}).attr({
  attribute4: 'value4',
  attribute5: 'value5',
}).appendTo('#anotherDiv');
{% endhighlight %}

参考资料： [AirBnB Style Guide](https://github.com/airbnb/javascript/)


PHP (based on Drupal)
=====================

- Setup Drupal variable, create admin UI (form API).

- Slip `.inc` files and use `require_once` to import separate files.

- Use pre-processor hook to add the JS.

- To keep the code `DRY`, we could use these techniques:
-- Use PHP iterator and `foreach ($array as $key => $value)`, you don't need the counter $i any more.
{% highlight php%}
   // Define a theme per template.
   $templates = new RecursiveIteratorIterator(new RecursiveDirectoryIterator(
     __DIR__ . '/templates', FilesystemIterator::SKIP_DOTS
   ));
   $template_themes = [];
   foreach ($templates as $template) {
     $template_basename = $template->getBasename('.tpl.php');
     $theme_name = 'janrain_' . str_replace('-', '_', $template_basename);
     $template_themes[$theme_name] = [
       'template'  => str_replace(__DIR__ . '/', '', $template->getPath()) . '/' . $template_basename,
       'variables' => [],
     ];
   }
{% endhighlight %}

-- Use `array_map` function to call a function multiple times, every time one element will be assign as parameter.
{% highlight php%}
// Drupal 'theme' function will get the corresponding template back.
// The result will be stored in array.
$rendered_html = array_map('theme', [
    'theme1',
    'theme2',
    'theme3',
]);
{% endhighlight %}

-- Use `array_reduce` function to call a function iteratively, reduce the array to single value.

-- Use `array_merge` function to override default value in array (e.g. extend/override configuration).
{% highlight php%}
  $block_default = ['cache' => DRUPAL_NO_CACHE, 'category' => t('CATEGORY')];
  $blocks['BLOCK1'] = array_merge($block_default, [
    'info' => t('BLOCK ONE'),
  ]);
  $blocks['BLOCK2'] = array_merge($block_default, [
    'info' => t('BLOCK TWO'),
  ]);
  $blocks['BLOCK3'] = array_merge($block_default, [
    'info' => t('BLOCK THREE'),
  ]);
{% endhighlight %}

-- Use `array_fill_keys` to assign same value to all the elements in an array
{% highlight php%}
$keys = array('Batman', 'Superman', 'Spiderman', 'Ironman');
$a = array_fill_keys($keys, 'Marvel Comics');
{% endhighlight %}


- Use block to put multiple template together

- Create CTOOL plugin make the block could be controlled in panel


Styling
===========

- Setup SASS environment, setup rb file.

- Drupal template file: use class provided by UI framework instead creating customized styling

- Use [BEM](http://getbem.com/introduction/) syntax. Could we use more than 2 level elements in BEM.

- Here's the [BEM guideline in Drupal 8](https://www.drupal.org/node/933976)

- Check out the [SMACSS](https://smacss.com/book/categorizing)


Devops, Data Structure, Style Practise, React, Restful API, CSS box model in-depth
