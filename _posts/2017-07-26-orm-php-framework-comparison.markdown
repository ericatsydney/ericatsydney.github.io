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

{% highlight php%}
// Define the relations
public function relations()
{
  return array(
    'VarName'=>array('RelationType', 'ClassName', 'ForeignKey', ...additional options)
  );
}

// Lazy loading:
// The sql will be executed when the related object is accessed.
$temp = $object->VarName;

// Eager loading:
// Prepopulate the `VarName` for all the objects before being accessed
// with single join sql. Performance is better for a big table.
$temps = Object::model()->with('VarName')->findAll();

// Performing Relational query without getting related models.
// High flexibility.
public function byUserGroups($user_id) {
  $criteria = new CDbCriteria;
  $criteria->join = 'INNER JOIN (user_group AS UG1, user_group AS UG2)';
  $criteria->condition = 'UG1.group_id = UG2.group_id
    AND t.id = UG2.user_id
    AND UG1.user_id = ' . $user_id;
  $this->getDbCriteria()->mergeWith($criteria);
  return $this;
}
{% endhighlight %}

how to handle the many to many? We need to write explitit update method in relation class, and call this method in the class.
{% highlight php%}
@todo
{% endhighlight %}


close-button

Yii 2
=====
Compared with Yii1, version 2's syntax is more institued.

like:


Laravel - Eloquent
===================
`Eloquent` syntax is most institue and easiest to learn in these solutions. But the some of the area is not very flexible, e.g.

Eloquent `eager loading` example:
{% highlight php%}
$books = App\Book::with('author')->get();

foreach ($books as $book) {
    echo $book->author->name;
}
{% endhighlight %}

And this is how the Eloquent handle relationship save action:
{% highlight php%}
$comment = new App\Comment(['message' => 'A new comment.']);

$post = App\Post::find(1);

$post->comments()->save($comment);
{% endhighlight %}

And detach the relationship like this:
{% highlight php%}
// Detach a single role from the user...
$user->roles()->detach($roleId);

// Detach all roles from the user...
$user->roles()->detach();
{% endhighlight %}




And the sql generated is not tuned [prove it]

Symfony - Doctrine
===================
While other solutions are using Active Record patern, `Doctrine` is using Data Mapper patern, it means it will only cater the abstraction in Domain Object, doesn't know how the objects stored in the database. So it's lighter, it benefit the automate testing.
