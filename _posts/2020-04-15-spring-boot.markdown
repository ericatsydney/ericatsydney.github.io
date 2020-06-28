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

@ConfigurationProperties Spring Boot 2.2 will add the corresponding field as bean into the application context.

- then the config can be got from the either the application config or Spring Boot Admin  

**Constructor**
@RequiredArgsContructor will generate a contructor with `final` fields. If customed logic is needed (e.g. setup a custom mapping for later usage), we need to create a explicit constructor manually.


**JPA**
With Spring Boot's help, all the manual tedious works will be saved, e.g. setup the DB driver, open and close DB, SQL statement, convert result set to objects, etc. As a result, we can concentrate on the business logic.

**DAO and Enity**


**JUnit Test**

@Mock vs @InjectMocks vs new

- @Mock provide a stub instance in the test.
    - `when().thenReturn()` help us mock the behaviors.
    - `verify().methodname` help us to make sure some of the methods have been called, will only work on mocked object.

- @InjectMocks provide a fully functioned instance, so that we can call its method.

- `new` keyword in test will run same thing as runtime: allocate memory and trigger the constructor.
    - `AsertEqual()` will work on the object created by `new` 

p.s. Argument matcher: we can use the matcher to the method's parameter, but we have to cover all parameters with these choices: any() eq().

**Actuator**

Auctuator module provide production ready features, like monitoring, health, metrics gathering. To use that, we could just add `spring-boot-starter-actuator` in the dpendency.

And we could use endpoint `private/actuator/refresh` to refresh the config

**Links/ Pagination**

HATEOAS is a standard/way to do the links in JAVA.

>REST architectural style lets you use hypermedia links in the response contents so that the client can dynamically navigate to the appropriate resource by traversing the hypermedia links. 

{% highlight java%}
"_links": {
        "first": {
            "href": "http://localhost:8080/api/albums-list?page=0&size=2&sort=title,desc"
        },
        "prev": {
            "href": "http://localhost:8080/api/albums-list?page=0&size=2&sort=title,desc"
        },
        "self": {
            "href": "http://localhost:8080/api/albums-list?page=1&size=2&sort=title,desc"
        },
        "next": {
            "href": "http://localhost:8080/api/albums-list?page=2&size=2&sort=title,desc"
        },
        "last": {
            "href": "http://localhost:8080/api/albums-list?page=4&size=2&sort=title,desc"
        }
    }
{% endhighlight%}

**Log config**

