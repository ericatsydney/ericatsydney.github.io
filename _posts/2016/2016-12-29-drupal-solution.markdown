---
layout: post
title:  "Drupal Solution"
date:   2016-12-29 16:05:52 +1000
categories: Geek
---

This article is about how to put all the information together, and how to organize the things.

Entity type/ content type is basic of information, it provide the place to store the raw data.

`View` is the core thing we try to put different content together. In view, we could define

- What kind of information we would like to get (entity type, content type)

- How it going to look like (display mode, formatter)
 
- How could we filter the content (exposed filter: user interaction; context filter: show relevant things according to main content)
 
- How we sort the result

`panel` is the container to organise the content as a page. In panel, we could define

- What block we need to show (block pane, ctool plugin pane - configurable)

- How it looks like (display)

- How to filter / pass information from page/ url (Use URL section to get the parameter)

`preprocessor` is the ultimate way to modify the output

- We can use `hook_preprocess_HOOK` to target the different layer of data flow before it's rendered. e.g. we can target node, view, block, pane or template

- We can modify the data structure, enrich information, change theme suggestion in the preprocess

tpl file is also a stable way to get the custom layout. but Drupal template need to fulfill the naming convention. At this point, the theme debug is very helpful, when we turn that on. We can get the tpl name suggestion printed in html markup.

Admin UI 
========

Admin UI is another field Drupal is very good at. We could easily setup a admin panel using system setting form API.

The field in system form will be saved as Drupal variable using `variable_set`. It means we need to use module name as part of the field name to make it unique across the whole system.

