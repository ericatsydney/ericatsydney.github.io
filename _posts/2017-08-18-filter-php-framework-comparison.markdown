---
layout: post
title:  "Filter - php frameork comparison"
date:   2017-08-18 9:01:00 +1000
categories: Geek
---

Yii - Filter
=======
{% highlight php%}
// The filters are used in controller.

/**
 * Define the sequence of filters.
 */
public function filters() {
  return array(
    'accessControl',
    'Custom',
  );
}

/**
 * Define the custom filters.
 */
public function filterCustom() {
}
{% endhighlight %}

Laravel - Middleware
=======
Middleware are used in route.

{% highlight php%}
Route::get('/', function () {
    //
})->middleware('web');

Route::group(['middleware' => ['web']], function () {
    //
});
{% endhighlight %}


