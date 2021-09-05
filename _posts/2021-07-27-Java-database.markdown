---
layout: post
title:  "Java - Database Integration"
date:   2021-07-27 22:40:00 +1000
categories: Geek
---

Hibernate / JPA / ORM
============
Hibernate is one of the most famous ORM framework. The purpose of ORM is let the developer to write cleaner domain logic.

But the drawback is the lack of type safety. The config to build the mapping is very annoying, The query tool (HQL or [JPA criteria queries](https://www.baeldung.com/hibernate-criteria-queries)) is very verbose and hard to read.

To address the above issue, jOOQ is borned. 

As side note, QueryDSL is also a good JPA based candidate to solve above issue. 


jOOQ / JDBC / SQL
======

jOOQ help to use database schema to generate Java classes, avoid the normal ORM pattern.

***config***
In the config, we put the jOOQ in as the required dependency, then link to related DB and tables. Also we need to indicate where will the generated targets be stored.

***code gen***
In the `compile` phase, pojo classes will be generated for each table, then we can use the class to access DB schema in the type safe way.

***usage***
Example:
{% highlight java%}
Result<Record3<Integer, String, Integer>> result = dsl
  .select(author.ID, author.LAST_NAME, DSL.count())
  .from(author)
  .join(authorBook)
  .on(author.ID.equal(authorBook.AUTHOR_ID))
  .join(book)
  .on(authorBook.BOOK_ID.equal(book.ID))
  .groupBy(author.LAST_NAME)
  .fetch();
{% endhighlight%}
for detail [check here](https://www.jooq.org/doc/2.6/manual/getting-started/use-cases/jooq-as-a-sql-executor/)

***Benefits***

- write the query in SQLish syntax, the powerful querying helps you to have better control on data

- compiler make sure the sql syntax correct and type safe, no more runtime error 

- code generation is efficient and make sure your code always sync with schema


[jOOQ vs Hibernate](https://blog.jooq.org/jooq-vs-hibernate-when-to-choose-which/)
[why jOOQ?](https://www.jooq.org/)
[jOOQ intro](https://www.baeldung.com/jooq-with-spring)