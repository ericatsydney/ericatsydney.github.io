---
layout: post
title:  "盒型模型的巧（er）妙（xin）"
date:   2016-05-31 6:05:52 +1000
categories: Programming
---

盒型模型有很多奇怪的地方。

**negative margin**

比父容器更宽


**border box的计算**

将padding，border都计算到width里

content box反之

**position可以改变一切**

absolute 会找最近的父类作为参照物。
position: absolute;
left: 100%;
absolute之后，parent会collapse（高度由没有absolute的内容决定）

**置中的方法**

parent relative
child absolute, left: 100%, margin-left: 50%;

关于floating， float之后collapse height失效
Clear empty div or after psudo class

**动态**

transition: all, .5s, ease-out;
定义:hover 状态

**关于foundation grid的一些使用技巧**

Row可以放在一个固定width的div里，再使用column。

Fixed Width带来的麻烦

Chrome的辅助：颜色吸取器，实时效果，固定悬停效果，DOM的位置