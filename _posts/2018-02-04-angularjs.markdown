---
layout: post
title:  "Angular 101"
date:   2018-02-04 14:10:00 +1000
categories: Geek
---

Basic Concepts
==============


Tricky Part
========================

1. @ binding is for passing strings. These strings support {{}} expressions for interpolated values. For example: . The interpolated expression is evaluated against directive's parent scope.

2. = binding is for two-way model binding. The model in parent scope is linked to the model in the directive's isolated scope. Changes to one model affects the other, and vice versa.

3. & binding is for passing a method into your directive's scope so that it can be called within your directive. The method is pre-bound to the directive's parent scope, and supports arguments. For example if the method is hello(name) in parent scope, then in order to execute the method from inside your directive, you must call $scope.hello({name:'world'})
