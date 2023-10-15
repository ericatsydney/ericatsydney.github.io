---
layout: post
title:  "Java webflex"
date:   2021-09-04 8:15:00 +1000
categories: Geek
---
The Spring Webflex framework or Reactive Stream is invented for the non-blocking/async working model.

Using the non-blocking call, the caller raise api request, then move on to do other things, when the response come back, the caller will continue working with the response.

The same non-block process can be used in Reactive stream api, to help the multiple thread processing. 

For example, in the `.map()` method, there is a long waiting process, we can use `subscribe()` method to push the result to subscriber, and don't hold the thread on waiting.

The following is an example to se the generic type in before block. 

{% highlight java%}
// We use the type reference here to determine the response type at run time.
public <P extends Response> Mono<Response<P>> search(ParameterizedTypeReference<Response<P>> typeReference) {
    // return in mono/flux, and give client the opportunity to handle the result in reactive way.
    return client.get().uri(uriBuilder -> uriBuilder
             .path(pathFor(xxxxxxxx))
             .queryParams(xxxxxx)
             .build()
         )
         .retrieve()
         .bodyToMono(typeReference);
}
{% endhighlight%}

{% highlight java%}
    ParameterizedTypeReference<Response<ResponseVariationA>> typeReference = new ParameterizedTypeReference<>() {};
    // Client can handle the response in reactive way (e.g. put it into lambda)
    Response response = service.search(typeReference).block();
{% endhighlight%}

[How block method works](https://projectreactor.io/docs/core/release/api/reactor/core/publisher/Mono.html#block--)

[Reference](https://docs.spring.io/spring-framework/docs/current/reference/html/web-reactive.html)

[Reactive way to consume api](https://spring.io/guides/gs/reactive-rest-service/)

WebClient is part of the WebFlux library.
