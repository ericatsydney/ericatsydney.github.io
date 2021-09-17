---
layout: post
title:  "OO Design Patterns in Java"
date:   2020-03-02 09:55:00 +1000
categories: Geek
---

When I first touched JAVA in 2005, Design Pattern is still the popular terms, the `Head First Design Pattern` was the best seller at that time. Now fast forward to 2020, no one is talking about design pattern anymore, I guess because most of the matured framwork already made the hard lifting for low level structure, so that we could focus on the business logic itself; and sencondly, after Java 8 introduce the lambda function, we can use a different (simpler) way to build the structural scaffold. 

But even so, it's still worthy to re-enforce some basic concept, because we still can find them in different applications. Here's the most common design pattern we will use in our day to day work, asterisk stand for the using frequency.

Creational
================

**The Singleton Pattern**

Using constructor without parameter to create single instance in application, make sure it's thread-safe (using eagerly instance or double checking).

**The Builder Pattern** `*****`

Using preset method to deal with complicated constructor. The stream-ish way make it clear and easy to instantiate object. 

In the modern Java, annotation @Builder can help us do most of the scaffold job. 

**Factory Method Pattern** `*****`

Defer the detail constructor in object subclass, actually the factory is the switch statement and call the subclass constructor. 

factoryClass (parameterized) -> switch statement - (call) -> concreteObject.factoryMethod

baseObject (abstracted) <-(extend)- concreteObject.factoryMethod 

**Abstract Factory Pattern**

The factory of factories, handle complicated use case. Try to avoid this if there's alternative solution, because the complexity make it problematic.

Structural
===========================

**The Adaptor Pattern**

client - (call) ->

Adapter (which inherit Target Interface) - (composite) ->  

Adaptee

**The Composite Pattern**

client -(call)->

Component (interface) <- (implement) - Leaf

Component (interface) <- (implement) - Composite (operation detail goes here)

**The Bridge Pattern**

client: new RefinedAbstraction(concreteImplementorInstance)

Abstraction (abstracted class) <- (inherited) - RefinedAbstraction

Abstraction (abstracted class) <- (parameterized constructor) - Implementor (Interface) <- (implemented) - ConcreteImplementor 

**The Facade Pattern** `*****`

client -(call) -> Facade (simplified method) -> other complicated system

**The Decorator Pattern**

client: new concreteDecoratorA( new concreteDecoratorB( new concreteComponent()))

Component (abstracted class) <- ConcreteComponent

Component (abstracted class) <- Decorator (Interface or Abstracted class) <- ConcreteDecorator

**The Proxy Pattern (security)**

extend reflect.invocation


Behavioral
=================================

**The Command Pattern**

client: instantiate Invoker, Receiver, bind concreteCommand with receiver (as parameter)

Invoker - (call) -> Command execute()

Command <- (inherit) - concreteCommand < - (parameterized) - Receiver instance

client - (call) -> Invoker.execute(concreteCommand instance)

**The Strategy Pattern**

contextClass <- (parameterized constructor) - strategyClass

strategyClass (abstracted) <-(inherit)- concreteStrategy 

**State Pattern**

contextClass - (call)-> state.handleRequest()

stateClass: abstract handleRequest method <- (implement) - concreteStateClass

concreteStateClass (handle request base on state and modify context state afterward) <- (parameterized constructor) - contextClass

**The Observer Pattern**

subjectClass include list of observers and its manage methods, state and its get set method

concreteObserverClass <- (parameterized constructor) - subjectClass 

concreteObserverClass - (call) -> subjectClass.setState()

concreteObserverClass - (call) -> subjectClass.getState()

**Template Method Pattern**

Defer the implementation detail to subclass, but keep the main process in super class.

**Iterator Pattern**

TBC

**The Interpreter Pattern**

**The Visitor Pattern**

**Chain of Responsibility Pattern**

**Mediator Pattern**

**Memento Pattern**

P.S. compared with design pattern, I think the OO principle and its nature is more important, they are still being used in our day-to-day programming live.





