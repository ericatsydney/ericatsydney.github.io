---
layout: post
title:  "重构"
date:   2016-05-23 7:05:52 +1000
categories: Programming
---

PHP based on Drupal:
- setup variable, and admin form
- template file: use framework class, with BEM syntax


SASS:
setup sass, rb file


JS:
- once vs one
- separate file according to the function, e.g. setting, eventHandler, utility, main
- Setting use this pattern, and use $.extend() for further enhancement by branding
defaultSetting = {
  variable1: value1,
  variable2: value2,
  .....
}
- Setting use this pattern to set dependency
defaultSetting = {
  variable1: value1,
  variable2: value2,
  .....
}
