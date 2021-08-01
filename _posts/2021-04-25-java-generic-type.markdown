---
layout: post
title:  "Java - generic type"
date:   2021-04-16 19:45:00 +1000
categories: Geek
---

Imagine you have a list, the data type of the list item might be Integer or String, and you want to check if a provided value exist in the list or not.

Could you write one logic to fix all data type, considering Float, Double will be added in.

Generic type will be the way to go. We can use generic type in method, class to abstract the same logic with different sub class inherited from the same parent class.  

We use the generic type <T> in application logic, and when call it in runtime, we pass in the class type as the parameter.




