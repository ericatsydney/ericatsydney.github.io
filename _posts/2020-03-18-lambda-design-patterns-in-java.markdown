---
layout: post
title:  "Functional Programming in Java"
date:   2020-03-18 09:55:00 +1000
categories: Geek
---

Stream Concept
=================

- Stream:

> There are 3 parts in Stream: one data source, zero or more intermediate operations and zero or one terminal operation.

> Intermediate operations get elements one-by-one and process them. All intermediate operations are lazy, and, as a result, no operations will have any effect until the pipeline starts to work.

>Terminal operations mean the end of the stream lifecycle. Most importantly for our scenario, they initiate the work in the pipeline.

Stream Method
======================

- `stream()` Convert the collection (list, array) to a sequential/stream, usually it will be followed by other pure function method as shown below.

- `forEach(element -> element.propertyMethod)` Perform an action for each element of this stream, but this method will not return any result. It usually will be the last method of the chain.

- `map(element -> Foo.bar(element))`  Return a stream consisting of the results of applying the given function to the elements of this stream.

- `peek(element -> sideEffectMethod(element)` Return a stream consisting of the elements of this stream, additionally performing the provided action (debug, side effect etc) which consume the same stream.

- `filter(element -> element.isApplicable().apply(foo)` Return a stream consisting of the elements of this stream that match the given predicate.

- `parallel()` Return the parallel stream, use this when handling a big stream.

- `flatMap(line -> Stream.of(line.split(" +"))` Apply transformation to the stream's element, then flatten the results into a new stream.

- `collect(Collectors.toList())` Convert the stream back to collection, usually it will be the last method of the chain.

- `sorted()` Return the sorted stream according to the Comparator provided.


Pure Function Method
=========================

- apply(single argument)

- Functional interface can be accept the lambda expression, then use this lambda expression apply on the runtime argument.

- Consumer: it's an operation interface can accept a single input and return nothing. So side effect is expected.

- Interface Function: when we define an interface, we could let the implement class pass the function reference 
(i.e. not override/implement method, but an existing function passed as a parameter) dynamically. 
In this situation, we can use interface function in the interface/abstracted class. 

- Predicate

- Supplier

Other Utils Used Together
=========================

- `BeanUtils.copyProperties(source, target, ...ignoreProperties)` It's useful when building a mapper along with some stream method, 


Design Pattern
==============

The following notes will use Jshell to demo how functional programming achieve the typical OO design pattern in a more compact and elegant way. 

**Factory**

**Strategy**

**Observer**

**Decorator**

And the following is the functional programming design pattern.

Reference: https://www.baeldung.com/java-streams-peek-api


