---
layout: post
title:  "Design Patterns in Java"
date:   2020-03-02 09:55:00 +1000
categories: Geek
---


Creational
================

**The Singleton Pattern**

Using constructor without parameter to create single instance in application, make sure it's thread-safe (using eagerly instance or double checking).

**The Builder Pattern**

Using preset method to deal with complicated constructor. The stream-ish way make it clear and easy to instantiate object. 

**Factory Method Pattern**

Defer the detail constructor in object subclass, actually the factory is the switch statement and call the subclass constructor. 

**Abstract Factory Pattern**

The factory of factories, handle complicated use case. Try to avoid this if there's alternative solution, because the complexity make it problematic.

Structural
===========================


**The Adaptor Pattern**


**The Facade Pattern**


**The Decorator Pattern**


Performing and representing tasks
=================================


**The Interpreter Pattern**


**The Strategy Pattern**


**The Observer Pattern**


**The Visitor Pattern**


**The Command Pattern**


