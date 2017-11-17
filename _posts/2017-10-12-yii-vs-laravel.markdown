---
layout: post
title:  "Yii vs Laravel"
date:   2017-10-12 8:10:00 +1000
categories: Geek
---

here's a table to compare the functions/ configuration between Yii and Laravel.

|	|Yii 2.x|	Laravel 5.x|
|---|-------|--------------|
|Controller|	Yes parameters auto binding	| Yes|
|View|	Yes special syntax for form, widget|	Yes|
|Model|	Yes|	Yes|
|Active Record|	Yes Support most of the popular RDB and redis and MangoDB|	Eloquent|
|DB Version Control|	[Migration](http://www.yiiframework.com/doc-2.0/guide-db-migrations.html)|	Migration|
|Composer Support|	Yes	|Yes|
|Route|	Yes [but not as good as Laravel](http://www.yiiframework.com/doc-2.0/guide-runtime-routing.html)|	Yes and flexible|
|API Support|	[Yes](http://www.yiiframework.com/doc-2.0/guide-rest-quick-start.html) easily swap between XML and JSON Rate limitting versioning solution|	Route, middleware could be separated by Web and API|
|AWS Integration|	NO	|AWS S3|
|Performance| | |		
|Security|	Yes|	CRSF token|
|Fillter|	Filter, Behaviours|	Middleware|
|Generate Code|	Gii - GUI and yii [The yii command come out of the box are insufficient](http://www.yiiframework.com/doc-2.0/guide-tutorial-console.html)|	Artisan make - command|
|Front-end tech|	Need to setup a template system, otherwise it will be cumbersum special syntax for form, widgets|	Blade Vue.js |
|Unit Testing|	Yes but documentation still in development need to setup separated DB for testing|	Yes, and very flexible - there's traits concept, don't need a separated testing DB - could disable middle ware in testing| 
|CLI Interpreter|	No	|Artisan tinker|
|Local environment|	No	|Homestead|
|Modularise|	Modules|	no Keep the MVC layers in whole application|
|Widget|	yes	|no|
|Assets(JS/CSS)|	Yes, and flexible registerCss, registerScriptFile|	Yes, but bound on blade template.Use blade stack, add JS, CSS dynamically in blade template|
|Architect Concept|	Dependency Injection, [Component](http://www.yiiframework.com/doc-2.0/guide-concept-di-container.html)|	Dependency Injection|


Form building
==========


Widget
========

Search Session
=========

Controller to View
==========
render partial
email template
parameter


Pagination
=======

Export result
========

