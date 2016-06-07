---
layout: post
title:  "Drupal Hook"
date:   2016-05-25 7:05:52 +1000
categories: Programming
---

Understanding Hook:

HOOK is the theme, module

Hook's Sequence
hook_preprocess_theme -> template
hook_preprocess_block

## hook_menu ##
This is the router of Drupal, link the url and callback function together, please note the Drupal bootstrap will be called.

That's why the graupal (lightweight service) is created.

## hook_preprocess_theme ##
The the 'theme' here is the theme name already in registry.
{% highlight php%}
   // This sample create variable in the preprocessor, and pass them to template.
   // Make it possible to override the variable in sub-theme, sub-module
   // Code goes here.
{% endhighlight %}

## hook_preprocess_view ##

## hook_preprocess_block ##

## hook_preprocess_pane ##

## hook_form ## && ## hook_form_alter ##
