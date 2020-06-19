---
layout: post
title:  "Functional Programming in Java"
date:   2020-03-18 09:55:00 +1000
categories: Geek
---

Important Method & Concept
=================

- Stream:

> There are 3 parts in Stream: one data source, zero or more intermediate operations and zero or one terminal operation.

> Intermediate operations get elements one-by-one and process them. All intermediate operations are lazy, and, as a result, no operations will have any effect until the pipeline starts to work.

>Terminal operations mean the end of the stream lifecycle. Most importantly for our scenario, they initiate the work in the pipeline.


- peek()
> This method exists mainly to support debugging, where you want to see the elements as they flow past a certain point in a pipeline 

> With this method we could alter the inner state of an element

- apply(single argument)

Functional interface can be accept the lambda expression, then use this lambda expression apply on the runtime argument.

Consumer

Function

Functional Interface

Stream, filter & Lambda

Predicate

Supplier

Design Pattern
==============

The following notes will use Jshell to demo how functional programming achieve the typical OO design pattern in a more compact and elegant way. 

**Factory**

**Strategy**

**Observer**

**Decorator**

And the following is the functional programming design pattern.

Reference: https://www.baeldung.com/java-streams-peek-api


