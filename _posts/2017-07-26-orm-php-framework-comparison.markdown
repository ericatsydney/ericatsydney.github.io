---
layout: post
title:  "ORM - PHP Framework Comparison"
date:   2017-07-26 8:10:00 +1000
categories: Geek
---

Yii 1.1
=======
Yii's Active Record is powerful and flexible. It support `lazy loading` `eger loading` and custom join with relationship.

Here's some examples:


Yii 2
=====
Compared with Yii1, version 2's syntax is more institued.

like:


Laravel - Eloquent
===================
`Eloquent` syntax is most institue and easiest to learn in these solutions. But the some of the area is not very flexible, e.g.

And the sql generated is not tuned [prove it]

Symfony - Doctrine
===================
While other solutions are using Active Record patern, `Doctrine` is using Data Mapper patern, it means it will only cater the abstraction in Domain Object, doesn't know how the objects stored in the database. So it's lighter, it benefit the automate testing.
