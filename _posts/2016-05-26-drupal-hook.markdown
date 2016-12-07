---
layout: post
title:  "Drupal Hook"
date:   2016-05-25 7:05:52 +1000
categories: Geek
---

Understanding Hook:

HOOK is the theme, module

In many situations, we use the hook as pre-processor,  

Hook's Sequence
hook_preprocess_theme -> template
hook_preprocess_block

## Creating Hook ##
Drupal's hook system is the way let modules interact with each other.

At first, define a hook in the host module (automatically it will be called in place):
{% highlight php%}
  // Let's say the name of module to define the hook is "host_module"
  // Sample 1, intercepting hook
  $result = array();
  foreach (module_implements('hook_name_1') as $module) {
    // Calling all modules implementing hook_hook_name_1 and 
    // Returning results than pushing them into the $result array:
    $result[] = module_invoke($module, 'hook_name');
  }

   // Sample 2, alter hook
   $data = array(
     'key1' => 'value1',
     'key2' => 'value2',
   );
   
   // Calling all modules implementing hook_my_data_alter():
   drupal_alter('hook_name_2', $data);
{% endhighlight %}

And then implement hook in other modules
{% highlight php%}
// The name of module to implement the hook is "other_module".
// Here we try to modify the variables in "host_module".
function other_module_host_module_hook_name_1() {
  //Implementation code goes here
}

function other_module_host_module_hook_name_2_alter() {
  //Implementation code goes here
}
{% endhighlight %}

## preprocess theme hook ##

This is a [reference](https://www.drupal.org/docs/7/theming/overriding-themable-output/setting-up-variables-for-use-in-a-template-preprocess-and)  about the sequence of running pre-process hook.

When we using a preprocessor without specify a theme hook, a second parameter could be passed as current hook.

{% highlight php%}
function sample_module_preprocess(&$variables, $hook) {
  // Use the theme hook name to set the base class, used for BEM modifiers.
  $varaibles['base_class'] = drupal_html_class($hook);
}
{% endhighlight %}


## hook_menu ##

This is the router of Drupal, link the url and callback function together, please note the Drupal bootstrap will be called.

## Theme Hook ##

- `<module_name>_theme`: This is the place to store theme registration, also you can put the template file here.

- `theme_<theme_name>`: After <theme_name> is registered above, this default function will be provided to implement (return html markup).
 
- `theme()` function: Route it to either the template file or theme function.

- `<module_name>_preprocess_<theme_name>` / `hook_preproces_HOOK`
Please refer the preprocess hook above.

## hook for Node/ Field/ View ##

- `hook_preprocess_node`, `hook_preprocess_field`, `hook_preprocess_view`  

We need these hooks when we would like to set the `themes_hook_suggestion` or pass the variables to the template like `node__<content_type>__<teaser>.tpl.php`.

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

- template system: @todo 


## Page Hook ##

- `hook_preprocess_page`

- TBC


## hook_library ##
`hook_library` will register the library, but it will not add this library automatically. so the following code is needed:
{% highlight php%}
form['#attach']['library'][]=library('module_name', 'library_name');
{% endhighlight %}


## Ajax framework ##

The drupal provide the Ajax form out of box, this is an example to show how to use it.
<TBC>
