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

**The Facade Pattern**

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

stateClass: abstract hanleRequest method <- (implement) - concreteStateClass

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





