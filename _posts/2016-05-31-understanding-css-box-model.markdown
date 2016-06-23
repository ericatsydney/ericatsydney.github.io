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

将padding，border都计算到width里

content box反之

**position可以改变一切**

- absolute 会找最近的relative父容器作为参照物。
{% highlight css%}
position: absolute;
left: 100%;
{% endhighlight %}

- absolute 中child DOM会继承absolute的特性，需要添加relative才能显示在正确位置。

- absolute之后，parent会collapse（高度由没有absolute的内容决定）

**置中的方法**

parent relative
child absolute, left: 100%, margin-left: -50%;

**floating**
子元素floating之后父容器collapse， height=0.
1. 父容器 直接设定 height
2. 子元素 empty div or after psudo class clear：both
3. 父容器 float 
4. 父容器 overflow： auto

**动态**

transition: all, .5s, ease-out;
定义:hover 状态

**关于foundation grid的一些使用技巧**

Row可以放在一个固定width的div里，再使用column。

**Fixed Width带来的麻烦**

Chrome的辅助：颜色吸取器，实时效果，固定悬停效果，DOM的位置
