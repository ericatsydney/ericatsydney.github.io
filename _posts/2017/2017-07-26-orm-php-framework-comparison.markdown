---
layout: post
title:  "ORM - PHP Framework Comparison"
date:   2017-07-26 8:10:00 +1000
categories: Geek
---

ORM is my favourite part of the MVC framework. It make it so easy to access data anywhere. We use it mainly in the `Controller`, only sometime inside `Model` when need to access other model data (e.g. relations) , but seldom in side the view (we can always prepare it in controller and pass it to view).

ORM provide a very handy/ quick syntax to access data in DB base on the model. We can add extra query to filter result, sort result, and it's very easy to access the other model using relations.

Here's some example I used ORM in different PHP frameworks.

Yii 1.1
=======

{% highlight php%}
// Useful query building base on model.
User::model()->findByPk($id);
User::model()->findAll();
// We don't need the % here like we do in sql.
User::model()->findAll('name like :name', array(':name' => 'Eric');
$criteria=new CDbCriteria();
$criteria->content = 'role = :role AND active = :active';
$criteria->params = array(':role' => 'admin',  ':active' => 1);
$criteria->order = 'role asc, created_date desc';
User::model()->findAll($criteria);
{% endhighlight %}

Yii's Active Record is powerful and flexible. It support `lazy loading` `eger loading` and custom join with relationship.

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
// N + 1 Query will be executed when there are N object instance returned.
$temp = $object->VarName;

// Eager loading:
// Prepopulate the `VarName` for all the objects before being accessed
// with single join sql. Performance is better for a big table.
$temps = Object::model()->with('VarName')->findAll();
{% endhighlight %}

In order to handle the `MANY_MANY` relationship, we need to write explicit update method in relation class, and call this method in the object class.
{% highlight php%}
// In Teacher.php, delete and create relations method is needed
public function clearStudentAssoc() {
    TeacherStudent::model()->deleteAll("teacher_id = :id", array(':id' => $this->id));
}

public function createStudentAssoc($id) {
    $relation = new TeacherStudent();
    $relation->teacher_id = $this->id;
    $relation->student_id = $id;
    $relation->save();
}
{% endhighlight %}

Named scope is very handy to save time build custom query.
{% highlight php%}
public function scopes() {
  return array(
    'active' => array(
      'condition' => 'active = 1'
    ),
  );
}

// Use the scope in chain.
$user = User::model()->active()->findByPk($user);
{% endhighlight %}


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

And this is how the Eloquent handle the updates for `MANY_MANY` relationship:
{% highlight php%}
$comment = new App\Comment(['message' => 'A new comment.']);

$post = App\Post::find(1);

$post->comments()->save($comment);

// And detach the relationship like this:
// Detach a single role from the user...
$user->roles()->detach($roleId);

// Detach all roles from the user...
$user->roles()->detach();
{% endhighlight %}

Eloquent's scope usage:
{% highlight php%}
// Define scope in User Class as a method.
public function scopeActive($query)
{
  return $query->where('active', 1);
}

// Utilize the scope in chain style.
$users = App\User::popular()->active()->orderBy('created_at')->get();
{% endhighlight %}


And the sql generated is not tuned [prove it]

Symfony - Doctrine
===================
While other solutions are using Active Record patern, `Doctrine` is using Data Mapper patern, it means it will only cater the abstraction in Domain Object, doesn't know how the objects stored in the database. So it's lighter, it benefit the automate testing.
