---
layout: post
title:  "OO Design Patterns in Java"
date:   2020-03-02 09:55:00 +1000
categories: Geek
---

When I first touched JAVA in 2005, Design Pattern is still the popular terms, the `Head First Design Pattern` was the best seller at that time. Now fast forward to 2020, no one is talking about design pattern anymore, I guess because most of the matured framwork already made the hard lifting for low level structure, so that we could focus on the business logic itself; and sencondly, after Java 8 introduce the lambda function, we can use a different (simpler) way to build the structural scaffold. 

Like in [this article](https://www.baeldung.com/spring-framework-design-patterns), Spring Boot already used 4 popular pattern, you use that day-by-day:

- Singelton Pattern (when we autowire the instance) 

- Factory Pattern (Spring Boot create the bean container as the factory)

- Proxy Pattern (Spring use proxy pattern to control underlying beans via parent bean)

- Template Pattern (JDBC template will be one of the use case)

Apart from above
Spring Boot also use observer pattern in [Application Events](https://www.baeldung.com/spring-events)

But even so, it's still worthy to re-enforce some basic concept, because we still can find them in different applications. Here's the most common design pattern we will use in our day to day work, asterisk stand for the using frequency.

| Type        | Pattern Name | Remarks |
| ----------- | -----------  | ------------ |
| Creational  | Singleton    | Using constructor without parameter to create single instance in application, make sure it's thread-safe (using eagerly instance or double checking). |
|             | Builder      | Using preset method to deal with complicated constructor. The stream-ish way make it clear and easy to instantiate object. In the modern Java, annotation @Builder can help us do most of the scaffold job. |
|             | Factory      | Defer the detail constructor in object subclass, actually the factory is the switch statement and call the subclass constructor. |
|             | Abstract Factory | The factory of factories, handle complicated use case. Try to avoid this if there's alternative solution, because the complexity make it problematic.|
| Structural  | Adaptor      | Kotlin use this to connect the layout to data class |
|             | Facade      | We use it very often|
|             | Decorator   | Python use this a lot|
|             | Proxy       | |
|             | Bridge      | |
|             | Component   | |
| Behavioral  | Visitor      | Subject has no idea how to behavior, instead visitor will give the instruction to subject depends on the classes. This pattern centralize all the logic in visitor, and help to prevent distributing the operation into various node classes.|
|             | Template      | Defer the implementation detail to subclass, but keep the main process in super class. |
|             | Observer      | |
|             | Strategy      | |
|             | Command      | |
|             | Interpreter   | |
|             | Mediator      | |
|             | Memento      | |

P.S. compared with design pattern, I think the OO principle and its nature is more important, they are still being used in our day-to-day programming live.
