---
layout: post
title:  "BDD terminology and sample"
date:   2016-07-14 20:30:52 +1000
categories: Programming
---

- PhantomJS: For headless website testing.

- Gherkin: A language for documentation and automated testing. 

- Cucumber: It use plain language to run automated testing, cucumber's feature is written in `Gherkin` syntax
{% highlight js%}
Given an established state
When an action occurs
Then an assertable state is achieved
{% endhighlight %}

- Chimp: A testing framework integrated with Jasmin, Cucumber.js, Selenium and WebdriverIO. 
 
- Selenium2.O / Webdriver: testing framework for web application, it provide record/ playback tool.
![Selenium RC Architecture](/assets/chapt5_img01_Architecture_Diagram_Simple.png) 
[Image Credit](http://www.seleniumhq.org/docs/05_selenium_rc.jsp) 

- Webdriverio: a implementation of Selenium, it basically send request to a Selenium server via the WebDriver Wire Protocol and handle the response.
 -- browser: a global variable, through this we can access session and all information using this [API](http://webdriver.io/api.html)
{% highlight js%}
 this.Given(/^I am on "([^"]*)" page$/, function (page) {
   browser.url(common.siteSettings[page]);
 });
{% endhighlight %}

 
- Jasmin: A BDD testing framework for Javascript, it provide a `expect()` function for assertion.
 -- expectation: true or false
 -- spec: passing or falling 
{% highlight js%}
describe('Hello world', function() {
  it('says hello', function() {
    expect(helloWorld()).toEqual('Hello world!');
  });
});
{% endhighlight %}
