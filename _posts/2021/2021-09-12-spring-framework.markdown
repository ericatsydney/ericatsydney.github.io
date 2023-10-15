---
layout: post
title:  "Spring Framework - second look at that"
date:   2021-09-12 21:59:00 +1000
categories: Geek
---

The following article is a bit long, but it's the good source to understand Spring framework's basic. I like it because it's easy to understand, no jargon, and the example snippets are very helpful as well.

Under the hood, Spring Framework is the container of dependency injection container, it has another name `ApplicationContext`.

It will automatically/ magically initiate the instances according to the dependency.

How could Spring do that?

- entry point to call collect the configurations in the application

- in the configuration, we define the @Bean which need to know the runtime setting (e.g. the credentials)

- Spring will @ComponentScan all the @Component define in the classes

- Spring will link the @Component and @Bean by @Autowired, or modern way, we can skip @Autowired, and rely on the clarification in the class (e.g. the parameter in construction)


[Reference](https://www.marcobehler.com/guides/spring-framework)