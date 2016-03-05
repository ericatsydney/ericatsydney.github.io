---
layout: post
title:  "Denpendency Injection"
date:   2016-03-05 22:00:52 +1000
categories: Promgramming
---
{% highlight php %}
interface ConnectionInjector{
    public function injectConnection( Connection $con );
}

class UserProvider implements ConnectionInjector{
    protected $connection;

    public function __construct(){
        ...
    }

    public function injectConnection( Connection $con ){
        $this->connection = $con;
    }
}
{% endhighlight %}
