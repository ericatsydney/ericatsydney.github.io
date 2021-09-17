---
layout: post
title:  "Artisan and Tinker"
date:   2016-12-19 8:25:52 +1000
categories: Geek
---

{% highlight shell%}
// Create a new resourceful controller
php artisan controller:make [--bench="vendor/package"]
// Seed the database with records
php artisan db:seed [--class[="..."]] [--database[="..."]]
// Set the application key
php artisan key:generate
// Database migrations
php artisan migrate [--bench="vendor/package"] [--database[="..."]] [--path[="..."]] [--package[="..."]] [--pretend] [--seed]
// Create the migration repository
php artisan migrate:install [--database[="..."]]
// Create a new migration file
php artisan migrate:make name [--bench="vendor/package"] [--create] [--package[="..."]] [--path[="..."]] [--table[="..."]]
// Reset and re-run all migrations
php artisan migrate:refresh [--database[="..."]] [--seed]
// Rollback all database migrations
php artisan migrate:reset [--database[="..."]] [--pretend]
{% endhighlight %}

And the composer command Cheat sheet
{% highlight shell%}
composer create-project laravel/laravel folder_name
composer install
composer update
composer dump-autoload [--optimize]
composer self-update
{% endhighlight %}


