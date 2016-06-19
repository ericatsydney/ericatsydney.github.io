---
layout: post
title:  "Phpstorm"
date:   2016-06-04 21:30:52 +1000
categories: Programming
---
Some Short Cut
==============
- `Alt + Enter` could help to call the intention action for the classes.

- `Ctrl + D` duplicate the selection.

- `Ctrl + K` commit and push changes.

- Double-press `Shift` search by file name.

- `Shift + F6` refactoring change file name.

- `Ctrl + Tab` switch between opened tabs.

- `Shite + Escape` \ `Alt + 1` Hide / Show project tool window.

- `Ctrl + Shift + F` Search keyword in folder.

- `Ctrl + Alt + Left/Right` Jump backward / forward through places you have been in the code base.
 

Live template
==============
1. Add context by installing plugins (e.g. the Storm does not support Markdown by default)

2. Setting -> Live Template -> in the context(e.g) Add -> Set abbreviation -> Set template

{% highlight php%}
foreach ($ITERABLE$ as $VAR_KEY$ => $VAR_VALUE$) {
    $END$
}
{% endhighlight %}

3. After setup, you could use `ctrl + j` or type the abbreviation to call the template.

This is link to setup [Drupal Template](https://www.drupal.org/project/phpstorm_templates) in Phpstorm. 

Linting
=======
scss-lint, jshint

How to install Plugin?
===========================
setting -> plugin

Hide the folder
===============
- Marked folders as 'Excluded'

- little 'cog' -> Uncheck 'Show Excluded Folder'

Xdebug (copied from Mavericks Wiki)
===================================
Xdebug will enable you to debug Drupal sites effectively. The setup explained here is called "zero-configuration debugging", which is not quite accurate.

1. Setup xdebug.ini

Update `/etc/php5/apache2/conf.d/20-xdebug.ini` with the following code and restart apache service.

{% highlight php%}
zend_extension=/usr/lib/php5/20121212/xdebug.so 
xdebug.remote_enable=1 
xdebug.remote_handler=dbgp 
xdebug.remote_host=192.168.50.1 
xdebug.remote_port=9000 
xdebug.remote_autostart=0
{% endhighlight %}

2. Install xdebug plugins for your browsers

Chrome: [Xdebug helper](https://chrome.google.com/webstore/detail/xdebug-helper/eadndfjplgieldjbigjakmdgkmoaaaoc?hl=en) extension.

3. Setup phpstorm

   - Go to File > Settings > Languages & Frameworks > PHP > Debug > Xdebug

   - Set Debug port to 9000

   - Check Can accept external connections.

4. Start debuging: click phone icon in storm, enable Chrome xdebug plugin, set breakpoint, refresh page.