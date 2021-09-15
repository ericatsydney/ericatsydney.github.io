---
layout: post
title:  "Spring Boot - API Exception Handling"
date:   2021-09-09 8:32:00 +1000
categories: Geek
---

Spring Boot simplify the exception handling a lot. 

There are 2 ways to handle the exception, first one is controller base, we define the exceptions in the controller:

{% highlight java%}
@ResponseStatus(value=HttpStatus.NOT_FOUND, reason="No such Order")
public class OrderNotFoundException extends RuntimeException {
     // ...
 }
{% endhighlight%}

{% highlight java%}
@RequestMapping(value="/orders/{id}", method=GET)
 public String showOrder(@PathVariable("id") long id, Model model) {
     Order order = orderRepository.findOrderById(id);

     if (order == null) throw new OrderNotFoundException(id);

     model.addAttribute(order);
     return "orderDetail";
 }
{% endhighlight%}

Another solution is the global exception handling, we used @ControllerAdvice to apply the @ExceptionHandler to the whole application.

On top of that, we could use the [Problem Framework](https://github.com/zalando/problem-spring-web) to specify the standardized error format for your application.

{% highlight java%}
@ControllerAdvice
public class SpringExceptionHandlerAdvice  implements ProblemHandling {

    @ExceptionHandler
    public ResponseEntity<Problem> handleFooException(final FooException exception, final NativeWebRequest request) {
        final var problemBuilder = Problem.builder().withStatus(Status.BAD_REQUEST).withTitle("Foo Exception");
        final var problem = getProblem(exception.getBindingResult(), problemBuilder);
        return new ResponseEntity<>(problem, HttpStatus.BAD_REQUEST);
    }

}
{% endhighlight%}

[Global exception handling - solution 3](https://www.baeldung.com/exception-handling-for-rest-with-spring)

[Spring boot error handling](https://spring.io/blog/2013/11/01/exception-handling-in-spring-mvc)

