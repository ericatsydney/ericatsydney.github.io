---
layout: post
title:  "Spring Boot"
date:   2020-04-15 1:25:00 +1000
categories: Geek
---

**Bean in Spring Boot**

Spring Context is the corner stone of Spring, it represents Spring Container of Dependency Injection. It
s the power house of initiating and wiring.

@Configuration is equivalent to the `Configuration.xml`, it use the class style to store the Java Bean definition.
  
In @Configuration we define the bean explicitly using @Bean annotation, we can use name and scope.

{% highlight java%}
@Bean(name = "foo")
public Foo foo() {
   return new Foo(); // add any customized initiate step here.
}
{% endhighlight%}

Another way to add the bean to context is using Spring Boot auto scan with these annotation @Component , @Repository, @Service and @Controller etc.

Here's the difference among the 4 annotations:

- @Component is the basic version with Bean auto scan and registration.

- @Controller special form of @Component, which has exact same function. And it also indicate it's the controller in Spring MVC, which provide the routing and wiring up services.

- @Service, @Repository are also the special form of @Component is service and persistent layer.

When it comes to Dependency Injection stage, there are 3 different choices, all of them support field and setter injection. And the details  are:

- @Resource: resolves dependencies by name first.
{% highlight java%}
// matched by name
@Resource(name="bar")
private Foo foo;
// matched by type
@Resource
private Foo foo1;
// matched by qualifier
@Resource
@Qualifier("foo")
private Foo foo2;

{% endhighlight%}

- @Inject: resolve dependencies by type as default.

{% highlight java%}

@Inject
private Foo foo1;

@Inject
@Qualifier("foo")
private Foo foo2;

@Inject
@Named("foo")
private Foo foo;
{% endhighlight%}

- @Autowired: similar as @Inject, and it's part of the Spring framework.

**Configuration**
@SpringBootApplication is the composed annotation, actually it includes the following annotations:
- @Target({ElementType.TYPE})
- @Retention(RetentionPolicy.RUNTIME)
- @Documented
- @Inherited
- @SpringBootConfiguration
- @EnableAutoConfiguration
- @ComponentScan

Then all the @Component will be scanned and put it as bean in Context, @Autowired will help to initiate the bean and dependency injection.

And if we need to scan package not in default component scanning, we need to explicitly to add `@ComponentScan` annotation.

**JPA**
With Spring Boot's help, all the manual tedious works will be saved, e.g. setup the DB driver, open and close DB, SQL statement, convert result set to objects, etc. As a result, we can concentrate on the business logic.

**DAO and Enity**


**Unit Test**

@Mock vs @InjectMocks

- @Mock provide a stub instance in the test.

- @InjectMocks provide a fully functioned instance, so that we can call its method.

`when().thenReturn()` help us mock the behaviors.

Argument matcher: we can use the matcher to the method's parameter, but we have to cover all parameters with these choices: any() eq().

`verify().methodname` help us to make sure some of the methods have been called.

**Actuator**

use endpoint `private/actuator/refresh` to refresh the config

**Pagination**

Hateos

**Log config**

