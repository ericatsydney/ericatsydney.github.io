---
layout: post
title:  "Redux Insight"
date:   2019-05-03 14:10:00 +1000
categories: Geek
---

Core Concepts
==============

### Actions

Actions are used to tell Redux that something in an application has changed, or that the user has interacted with the application in some way. Actions in Redux are plain objects with a `type` property.

### Reducers

In Redux, reducers are used to facilitate state transformations based on actions. It use current state and action object to compute a new state.

### Store

The store in Redux is what coordinates passing actions to your reducer, notifying you of changes to your state. It encapsulates the state and offers an interfaace that you can use to interact with it. This interface is comprised of the following:
- dispatch(action)
- getState()
- subscribe(listener)

### Middleware

Middleware acts as a pipeline that all dispatched actions go through before reaching the store. And actually middleware in Redux provide a interface to make a plugin-system possible.

### Selector
Selectors are functions that accept a state from the Redux store and compute data that will eventually be passed as props to React. 

Redux Patterns
========================

{% highlight shell%}
{% endhighlight %}

##### Reference and credit:

*Developing a Redux Edge* - by Johannes Lumpe; Karl Purkhardt; Darío Cravero; Troy Mott; Art Muller; Ezekiel Chentnik - Published by Bleeding Edge Edge Press, 2016
