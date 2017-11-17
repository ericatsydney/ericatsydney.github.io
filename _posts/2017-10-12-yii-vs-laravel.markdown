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
|Front-end tech|	Need to setup a template system, otherwise it will be cumbersome special syntax for form, widgets|	Blade Vue.js |
|Unit Testing|	Yes but documentation still in development need to setup separated DB for testing|	Yes, and very flexible - there's traits concept, don't need a separated testing DB - could disable middle ware in testing|
|CLI Interpreter|	No	|Artisan tinker|
|Local environment|	No	|Homestead|
|Modularise|	Modules|	no Keep the MVC layers in whole application|
|Widget|	yes	|no|
|Assets(JS/CSS)|	Yes, and flexible registerCss, registerScriptFile|	Yes, but bound on blade template.Use blade stack, add JS, CSS dynamically in blade template|
|Architect Concept|	Dependency Injection, [Component](http://www.yiiframework.com/doc-2.0/guide-concept-di-container.html)|	Dependency Injection|


**Yii's Tricks**

Form Model
==========
Form Model is very unique concept across the MVC framework. Mainly it provide another layer to connect controller and the view. The form in View is pretty much built following the form model field. Form model provide the standard validation, custom validation (by mode) and label definition.

Usually, in the controller we will check the get the submission data from `$_POST`, use `model->setAttributes()` to cast the info into the form model, then perform validation, if passed then use the real model to persistent data.

Widget
========
`Widget` is self-contained front-end component.
{% highlight php%}
// Create a widget in widgets folder.
class MyCaptcha extends CCaptcha
{
   public $model;
   public $attribute;

   public function run(){

       parent::run();
       echo CHtml::activeTextField($this->model, $this->attribute);
    }
}

// In the view render the widget.
$this->widget('application.components.widgets.MyCaptcha', array(
    'model' => $model,
    'attribute' => 'captcha',
));


// In the controller.
public function actions() {
    return array(
        'captcha'=>array(
            'class'=>'CCaptchaAction',
            'backColor'=>0xFFFFFF,
        ),
    );
}


// In the form model.
public function rules() {
   return array(
       array('username, password, email', 'required'),
       array('email', 'email'),
       array('captcha', 'captcha'),
   );
}
{% endhighlight %}

Search Session
=========
In order to save search criteria or for the pagination jumping, we need to find a way to persistent the search criteria.
  + create model to save the criteria
  + assign unique ID for every record
  + generate a record for search, and save the criteria in the table
  + carry the search ID when jumping around, and retrieve the criteria

Controller to View
==========
{% highlight php%}
// Render partial, this how we break the template down into small parts.
<?php $this->renderPartial('_side_bar'); ?>

// email template
// Use the output buffer and extract function to get the template and assign the variables.
{% endhighlight %}

Pagination
=======
{% highlight php%}
// Use the same criteria to retrieve model
// and create the pagination.
$count = User::model()->count($criteria);
$pages = new CPagination($count);
$pages->pageSize = 10;
$pages->applyLimit($criteria);
$this->vars->pages = $pages;


// In View, render the pagination like this
$this->widget('PageWidget', array(
    'pages' => $pages,
));
{% endhighlight %}

Export result
========
The solution to export/download result as a file is pretty generic.

{% highlight php%}
// Download result as csv.
header("Cache-Control: public");
header("Content-Description: File Transfer");
header("Content-Disposition: attachment; filename=".$fileName);
header("Content-Type: application/octet-stream");
header("Content-Transfer-Encoding: binary");
echo $title_line;
echo $data_line_1;
echo $data_line_2;
{% endhighlight %}
