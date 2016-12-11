---
layout: post
title:  "Laravel - Dependency Injection"
date:   2016-03-05 22:00:52 +1000
categories: Geek
---

As my understanding

> Dependency Injection is about how to defer concreting service class, create service instance along with the client instance.
> But we still need to clarify the **dependency** between client and service, so we **inject** the service into the client as a parameter.  

1. This is the implementation without DI
{% highlight php%}
class Brush {
  private $color;
  private $texture;
  public function _construct($color, $texture) {
    $this->setColor($color);
  }
  public function setColor($color) {
    $this->color = $color;
  };
  public function getColor() {
    print $this->color;
  };
  public function setTextture($texture) {
    $this->texture = $texture;
  };
  public function getTextture() {
    print $this->texture;
  };
}
class Painter {
  public function draw($color, $texture) {
    $brush = new Brush($color, $texture);
    $brush.getColor();
    $brush.getTexture();
  }
}
$picasso = new Paiter();
$picasso.draw('red', 'soft');
{% endhighlight %}

2. Use Dependency Injection.
{% highlight php%}
class Painter {
  private $brush;
  public function _construct(Brush $brush) {
    $this->brush = $brush;
  }
  public function draw() {
    $this->brush.getColor();
    $this->brush.getTexture();
  }
}
$picasso = new Paiter(new Brush('blue', 'hard'));
{% endhighlight %}

3. Laravel: use service container (Inversion of Control)
Sample 1: for the normal class 
{% highlight php%}

// We don't need to bind method here, as Laravel is smart enough to 
// detect we need an instance and use PHP Reflection to new the Brush 
// class for us automatically.
// App:bind( 'Brush', function() {
//  return new Brush;
//});

class Painter {
  private $tool;
  public function _construct(Brush $brush) {
    $this->tool = $tool;
  }
}
{% endhighlight %}

Sample 2: for the interface
{% highlight php%}
interface Tool {
}
class Brush implement Tool{
}
class Pencil implement Tool{
}
// App is the Facade of Application extend from Container
// Without this binding, the Painter construct function will get error 
// for binding a interface class. 
App:bind( 'Tool', 'Pencil' );

class Painter {
  private $tool;
  public function _construct(Tool $tool) {
    $this->tool = $tool;
  }
}
{% endhighlight %}

Reference: sitepoint [blog](http://www.sitepoint.com/dependency-injection-laravels-ioc).

4. Symfony, use service container
{% highlight php%}
// Register brush in container as a service.
use Symfony\Component\DependencyInjection\ContainerBuilder;
$container = new ContainerBuilder();
$container
    ->register('brush', 'Brush');

class Painter {
  private $brush;
  public function _construct(\Brush $brush) {
    $this->brush = $brush;
  }
}
{% endhighlight %}

5. Drupal 8
TBC
