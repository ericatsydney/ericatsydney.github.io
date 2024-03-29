---
layout: post
title:  "Refactoring in Java"
date:   2020-03-03 09:55:00 +1000
categories: Geek
---

Quote from Robert C. Martin in the *Book Clean Architecture: A Craftsman's Guide to Software Structure and Design*.

> OO is the ability, through the use of polymorphism, to gain absolute control over every source code dependency in the system. It allows the architect to create a plugin architecture, in which modules that contain high-level policies are independent of modules that contain low-level details.

OO's nature
=================
- encapsulation: put the boundary around the cohesive data and function, only expose the minimum interface to outside. By using this way, a better protection and lower maintenance to the program itself.

- inheritance: provide a convenient way to redeclare the data and function to the derivatives.

- polymorphism: provide a safe and convenient way to let the concrete derivatives be defined at runtime. (actually it's implemented by different function tables can be loaded on the flight, and the pointer can call the diffrent version of method ) 

OO Design Principle
=======================

SOLID 

- Single Responsibility Principle
    - A module should have one and only one reason to change.
    - move common method out

- Open-closed principle: open for extend, closed for modification
    - partition the system into component in a hierarchy, protect the higher level component from the changes of lower level 
    - write an interface/abstract class and implement/extend class from there, this way can avoid keep modifying a class, after we have tested a class, we should try to extend rather than modify that.

- Liskov substitution: object can be replaced by subtype, still correct

- Interface segregation: small specific interface better than single generic one.

- Dependency inversion: depend on abstraction but not concretions.
    - avoid using new keyword in method,make the test easier
    
Data Flow of Application
========================
controller - (request) -> service - (other service initiatives) -> Repo method - (get response ) -> service - (post processor, response convertion) -> controller

Data flow is like the map of architecture, using this map we can decide where should we put the logic in and where can we get/reuse the same data. Here's some use case in my day to day work:

- when we found two unrelated logic block putting in same class, it's the smell that we need to check data flow upward, and create another peer class and call it overthere. 

- before we initiate a new resource, check data flow upward to see any existing data we can reuse.

Best Practices
=================
- Don't use * in import

- Remove the unused import
 
- Make sure the function is small (cohesive and decoupled)

Reference:

[Clean Architecture: A Craftsman's Guide to Software Structure and Design](https://www.amazon.com.au/Clean-Architecture-Craftsmans-Software-Structure/dp/0134494164/ref=sr_1_1?dchild=1&keywords=Clean+Architecture%3A+A+Craftsman%27s+Guide+to+Software+Structure+and+Design&qid=1591422658&sr=8-1)





