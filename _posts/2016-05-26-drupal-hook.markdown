---
layout: post
title:  "Drupal Hook"
date:   2016-05-25 7:05:52 +1000
categories: Programming
---

Understanding Hook:

HOOK is the theme, module

In many situations, we use the hook as pre-processor,  

Hook's Sequence
hook_preprocess_theme -> template
hook_preprocess_block

## hook_menu ##

This is the router of Drupal, link the url and callback function together, please note the Drupal bootstrap will be called.

## Theme Hook ##

- `<module_name>_theme`: This is the place to store theme registration, also you can put the template file here.

- `theme_<theme_name>`: After <theme_name> is registered above, this default function will be provided to implement (return html markup).
 
- `theme()` function: Route it to either the template file or theme function.

- `<module_name>_preprocess_<theme_name>` / `hook_preproces_HOOK`
{% highlight php%}
   // This sample create variable in the preprocessor, and pass them to template.
   // Make it possible to override the variable in sub-theme, sub-module
   // Code goes here.
{% endhighlight %}

##Field Type API##

This is the field type API [DOC](https://api.drupal.org/api/drupal/modules%21field%21field.api.php/group/field_types/7.x)
 
- `hook_field_info`: define the name, description, formatter and widget. 

## Form Hook ##

- `hook_form` 

- `hook_form_alter`: update the render array before form is rendered.

- TBC


## Block Hook ##

- `hook_block_info()`: define the block's name.  

- `hook_block_view()`? define the block's render array.

- `hook_preprocess_block()`: modify the variable before the block get rendered.

## View Hook ##

- `hook_preprocess_view` 

- TBC


## Page Hook ##

- `hook_preprocess_page`

- TBC


## hook_library ##