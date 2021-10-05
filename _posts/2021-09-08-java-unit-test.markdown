---
layout: post
title:  "Java Testing"
date:   2021-09-07 8:32:00 +1000
categories: Geek
---

System Integration Test
=======
When we setup a test, annotation @SpringBootTest can help to create the entire context without starting the server.

And then we can use webTestClient or MockMvc class to mimic a request call.

It's very suitable for the system integration tests, for example test controller's response with the DB connection. 


Mockito
===========
Basics go first: Mockito is mocking framework to help to virtually create the instances for your tests.
 
It will create a stub instance, rather than a fully functional one, so it means memory saving and faster test results.

When we write the test case, the following few ways we can use to create the testing object.

- @Mock provide a stub instance in the test, will be equivalent to `mock()`.
    - `when().thenReturn()` specify a behavior you want when the method get called, the method will not be executed when test.
    - `verify().methodname` checks if the method have been called, will only work on mocked object.

- @InjectMocks will creat an mock instance (parent), which contain a few fields has been mocked using @Mock. And runtime, it will automatically inject all the fields and spy on that. So that we can call the method define in the parent object.

- @Spy/spy() will create a partially mock instance, so that we can mock some of the method and run the real method when needed. Chec this [example](https://javadoc.io/doc/org.mockito/mockito-core/latest/org/mockito/Mockito.html#spy-T-)

- `new` keyword in test will run same thing as runtime: allocate memory and trigger the constructor.
    - `AsertEqual()` will work on the object created by `new` 

p.s. Argument matcher: we can use the matcher to the method's parameter, but we have to cover all parameters with these choices: any() eq().


Junit 4 vs Junit 5
============
Junit is the most popular Java testing framework. It will manage tests executions, assertion and provide the readable results to us.

Benefits migrating from Junit 4 to 5 are:

- Can use Stream/Lambda, as Junit 5 is Java 8 ready.

- Can use a few new assertion method, can simplify the logic a bit

- Have display name feature, make the report more readable.

- Can use conditioal test, can extend from multiple runners, dynamic tests etc.

test content with CSV
================
Junit 5 Test runner will execute the same test multiple times with different inputs.

It's very handy feature to go through sever permutations in the more readable ways. Other than CSVSource, we can use @ValueSource, @EnumSource as well.

{% highlight java%}
@ParameterizedTest
@CsvSource({
    "input 1", "result 1",
    "input 2", "result 2"
})
@DisplayName("should get expected results")
voild shouldGetExpectedResults(String input, String expected) {
    assertThat(object.callMethod(input)).isEqualTo(expected);
}
{% endhighlight%}

