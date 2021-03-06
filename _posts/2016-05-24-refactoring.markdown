---
layout: post
title:  "Refactoring"
date:   2016-05-24 7:05:52 +1000
categories: Geek
---

Javascript
==========

- Change file name to use this pattern: [module].[some]-[function].js.

- Change variable name to camel case.

- Split files according to different purpose: main logic, setting, implementation(callback function), utility, event.

- Performance: reduce the event trigger, listen, make them happen once.

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

Reference： [AirBnB Style Guide](https://github.com/airbnb/javascript/)

- Programmatically trigger events;
{% highlight js%}
$.each(janrain.events, function(event) {
  if (typeof janrain.events[event].addHandler === 'function') {
    janrain.events[event].addHandler(function() {
      // E.g. `onCaptureProfileLink` => `CaptureProfileLink`.
      var eventName = 'fcl.janrain.' + event.replace(/^on/, '', event);
      $(document).trigger(eventName, arguments);
    });
  }
});
{% endhighlight %}
 


PHP (based on Drupal)
=====================

- Setup Drupal variable, create admin UI (form API).

- Split `.inc` files and use `require_once` to import separate files.

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


- Use block to put multiple template together

- Create CTOOL plugin make the block could be controlled in panel
Check the sample [here](/programming/2016/05/24/drupal.html)

Styling
===========

- Setup SASS environment, setup rb file.

- Drupal template file: use class provided by UI framework instead creating customized styling

- Use [BEM](http://getbem.com/introduction/) syntax. Could we use more than 2 level elements in BEM.

- Here's the [BEM guideline in Drupal 8](https://www.drupal.org/coding-standards/css/architecture)
   Never use id selectors in CSS.
   Strictly use ·!important`

- Check it out: the [SMACSS](https://smacss.com/book/categorizing)
  Don't apply the styling to early, so if you see code to reset the border, padding, margin, you need refactoring.

- Use class instead of html tag

- Use mixin with parameter, refer this [sample](http://ericatsydney.github.io/programming/2016/06/27/sass-101.html)