---
layout: post
title:  "盒型模型的巧（er）妙（xin）"
date:   2016-05-31 6:05:52 +1000
categories: Programming
---

CSS box model has many tricky thing.
 
> CSS is a hack.

> ** by someone **

**negative margin**

Without seting the child width and floating, `negative margin` make the child wider than the parent.

{% highlight html%}
<div class='parent'> 
  <div class='child'></div>
</div>
{% endhighlight %}

{% highlight css%}
div {
  display: block;
  border: 1px solid #000;
}

.parent {
  background-color: red;
  width: 300px;
  height: 100px;
  position: absolute;
  top: 0;
  left: 300px
}

.child {
  background-color: blue;
  height: 50px;
  position: relative;
  margin: 0 -20px;
}
{% endhighlight %}

**border box的计算**

`box-sizing: border-box` 将padding，border都计算到width里。

`box-sizing: content-box` 则反之。

**position可以改变一切**

- absolute 会找最近的relative父容器作为参照物。
{% highlight css%}
position: absolute;
{% endhighlight %}

- absolute 中child DOM会继承absolute的特性，需要添加relative才能显示在正确位置。

- absolute之后，parent会collapse（高度由没有absolute的内容决定）

**置中的方法**

当元素需要在父容器里置中，而且父容器里只有该元素。这很容易实现：
{% highlight css%}
.child {
  display: block;
  margin: 0 auto;
  width: 99px;
}
{% endhighlight %}

当元素需要在同一层的元素中置中，或者父容器有多个元素需要重叠置中（例如fliping effect）。就可以这样实现
{% highlight css%}
.peer-div {
  position: relative;
}
.center-div {
  position: absolute;
  left: 50%;
  margin-left: -45.5%; // margin left to peer-div is 0.5%;
}
{% endhighlight %}

当需要将`:before`, `:after` 元素一起置中时，可以使用无敌的`calc` 函数。
{% highlight css%}
.center-div {
  width: 40px;
  
  &:before {
    width: 40%;
    position: absolute;
    right: calc(50% - 20px);
  }
  
  &:after {
    width: 40%;
    position: absolute;
    left: calc(50% - 20px);
  }
}
{% endhighlight %}


**floating**

子元素floating之后父容器collapse， `height=0`. 解决方法有下面几个：

1. 父容器 直接设定 `height`;

2. 子元素 后面添加一个空的 div 或者 after pseudo class，赋值 `clear：both`;

3. 父容器 也float起来;

4. 父容器 赋值 `overflow： auto`。

**Animation**

transition: all, .5s, ease-out;

定义:hover 状态

**关于foundation grid的一些使用技巧**

Row可以放在一个固定width的div里，再使用column。

**Fixed Width带来的麻烦**




