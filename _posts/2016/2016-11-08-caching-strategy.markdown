---
layout: post
title:  "caching strategy"
date:   2016-11-08 7:40:52 +1000
categories: Geek
---

In order to maximize the performance, we could have several layer caching when user access the conent.

Block and Page Cache 
======
This the caching built in Drupal. Instead of executing the SQL command, it provide the caching to anonymous user. The configuration stay in configuration / performance.

We could use `Clear all cache` button or `drush cc all` to clean that up.

HTTP Header `X-Drupal-Cache` to see if this cache is HIT.

JS and CSS Cache
================
We could use `drush cc css-js` to flush JS cache.

Varnish
=======
It's a caching HTTP reverse proxy. It will store the anonymous page or static page. 

Akamai
======
It's the CDN. Akamai provide the API endpoint to flush cache, so it's possible to integrate the CDN cache flushing in Drupal admin UI.

If the expected result's not showing up, we could use cache busted to tell it's related to CDN caching or not.