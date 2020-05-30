---
layout: post
title:  "Refactoring in Java"
date:   2020-03-03 09:55:00 +1000
categories: Geek
---

OO Design Principle
=======================

SOLID 

- Single responsibility 
    - move common method out

- Open-closed principle: open for extend, closed for modification
    - write an interface/abstract class and implement/extend class from there, this way can avoid keep modifying a class, after we have tested a class, we should try to extend rather than modify that.

- Liskov substitution: object can be replace by subtype, still correct

- Interface segregation: small specific interface better than single generic one.

- Dependency inversion: depend on abstraction but not concretions.
    - avoid using new keyword in method,make the test easier





