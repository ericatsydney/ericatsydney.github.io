---
layout: post
title:  "重构"
date:   2016-05-24 7:05:52 +1000
categories: Programming
---

h3.JS:

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

- DRY: use object notation, callback function name, jQuery `each` function to simplify logic and decouple modules.
{% highlight js %}
eventHandlers = {
  event1: callBack1,
  event2: callBack2,
}

$.each(eventHandlers, function(eventName, callback) {
  janrain.events[eventName].addHandler(callback);
});
{% endhighlight %}

h3.PHP (based on Drupal):

- Setup Drupal variable, create admin UI (form API).

- Slip `.inc` files and use `require_once` to import separate files.

- Use PHP iterator to register theme (so cool~).
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

- Use `array_map` function to call a function multiple times according to array value.

- Use `array_fill_keys` ????

- Use block to put multiple template together


Styling:

- Setup SASS environment, setup rb file.
- Drupal template file: use class provided by UI framework instead creating customized styling, use "BEM":http://getbem.com/introduction/ syntax.



Devops, Data Structure, Style Practise, React, Restful API, CSS box model in-depth
