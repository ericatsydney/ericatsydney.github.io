---
layout: post
title:  "PHP Framework Knowledge Map"
date:   2017-10-13 13:30:00 +1000
categories: Geek
---
When checking the [Symphony certificate](https://sensiolabs.com/en/symfony/certification.html), I found this list of knowledge area.

I think it's realy good starting point to prepare my php knowledge base for the general MVC framework.

* PHP and Web Security
  - PHP 5.3 to PHP 5.6 API
  - Object Oriented Programming
  - Namespaces
  - Interfaces vs Abstract classes
    + Interfaces provide the abstract methods but no implements. It force the developer to follow the blueprint to develop.
    + While Abstract classes could provide both abstract or concrete methods, it could save repeat coding in child class and keep the code centralized. 
  - Anonymous functions and closures
    + Just like the JS, anonymous function could be assign to a variable or passed in method as a callback function parameters.
    + Closures: Check this [code playground](https://code.sololearn.com/w7CDMXDlwCz3/#php)
    + And here's a real good [tutorial](http://culttt.com/2013/03/25/what-are-php-lambdas-and-closures/)
  - [Exception and error handling](http://ericatsydney.github.io/geek/2017/10/10/php-exception-handling.html)
  - Traits
    + Just like a class, but `use` is the keyword. It could make a child class to extends multiple 'class' (Polymorphism)
  - PHP extensions ?
  - SPL
  - Web security (XSS, CSRF, etc.)
    + Yii provide [security solution](http://www.yiiframework.com/doc/guide/1.1/en/topics.security) out of box

* Framework Architecture
  - Components (Usually PHP Library managed by Composer)
    + Yii: component property / event / behavior?
    + Yii: These are the [core components](http://www.yiiframework.com/doc/guide/1.1/en/basics.application#core-application-components) 
  - Plugins / Extensions/ Bundles (how to register and inside folder structure?)
    + Yii: base on the core, components(front-end)/ extensions(back-end) could be added.
  - Bridges?
  - Configuration
  - Code organization
  - Request handling
    + Yii: entry script(index.php)
  - Exception handling
  - Event dispatcher/ Subscriber (Sololearn)
  - Kernel events
  - Official best practices
  
* Bundles
  - Naming conventions
  - Code organization
  - Controllers
  - The views
  - The resources
  - Overriding default error pages
  - Bundle inheritance
  - Semantic configuration and compiler passes

* Persistence/ ORM

* View / Templates
  - Twig
  - Blade
  - Auto escaping
  - Template inheritance
  - Global variables
  - Filters and functions
  - Template includes
  - Loops and conditions
  - URLs generation
  - Controller rendering
  - Translations and pluralization
  - String interpolation
  - Assets management
  - Debugging variables
  - Yii: `widget` is a reusable template group, predefine how the data link to the template variables.
  
* Controllers
  - Naming conventions
  - The base Controller class
  - The request
  - The response
  - The cookies
  - The session
    + Yii: CWebUser provide `setState` method to store info into session.
  - The flash messages
  - HTTP redirects
  - Internal redirects
  - Generate 404 pages
  - File upload
  - Built-in internal controllers
  - What's front controller? 
    + It's used to provide a centralized request handling mechanism so that all the requests will be handled by a single handler.
    + Yii: `CWebApplication` is the front-controller. Either extends or configuration could customize the `CWebApplication`. And all the context could be accessed in the life cycle through this front controller. e.g. Yii::app()->user() and Yii::app()->parameters['param_name']
  
* Routing
  - Configuration 
    + Yii: we can set the url config in front-controller. Its format is either `path` or `get`. And we can set the routing rules using regex.
    + Symfony: provide YAML, XML, PHP & annotations options to config.
    + [Symfony doco](https://symfony.com/doc/current/routing.html)
  - Restrict URL parameters
  - Set default values to URL parameters
  - Generate URL parameters
  - Trigger redirects
  - Special internal routing attributes
  - Domain name matching
  - Conditional request matching
  - HTTP methods matching
  - User's locale guessing
  - Router debugging
  
* HTTP
  - Client / Server interaction
  - Status codes
  - HTTP request
  - HTTP response
  - HTTP methods
  - Cookies
  - Content negotiation
  - Language detection

* Data Validation (Symfony can use annotations for validation)
  - PHP object validation
  - Built-in validation constraints
  - Validation scopes
  - Validation groups
  - Group sequence
  - Custom callback validators
  - Violations builder

* Dependency Injection
  - Service container
  - Built-in services
  - Configuration parameters
  - Services registration
  - Tags
  - Semantic configuration
  - Factories
  - Compiler passes
  - Services autowiring

* Security
  - Authentication / Users / Roles
    + [Symfony doco](https://symfony.com/doc/current/security.html)
  - Authorization
    + Symfony: use the [expression language](https://symfony.com/doc/current/components/expression_language.html) to implement to complex business logic
    + Yii: business rule is the association of roles, operations and tasks. Here's an example:
        {% highlight shell%}
            $auth=Yii::app()->authManager;
         
            $auth->createOperation('createPost','create a post');
            $auth->createOperation('readPost','read a post');
            $auth->createOperation('updatePost','update a post');
            $auth->createOperation('deletePost','delete a post');
             
            // This is like Symfony's expression language.
            $bizRule='return Yii::app()->user->id==$params["post"]->authID;';
            $task=$auth->createTask('updateOwnPost','update a post by author himself',$bizRule);
            $task->addChild('updatePost');
             
            $role=$auth->createRole('reader');
            $role->addChild('readPost');
             
            $role=$auth->createRole('author');
            $role->addChild('reader');
            $role->addChild('createPost');
            $role->addChild('updateOwnPost');
             
            $role=$auth->createRole('editor');
            $role->addChild('reader');
            $role->addChild('updatePost');
        {% endhighlight %}
  - Configuration
  - Providers
  - Firewalls
  - Passwords encoders
  - Access Control Rules
  - Guard authenticators
  - Voters and voting strategies

* [HTTP Caching](https://symfony.com/doc/current/http_cache.html)
  - Cache types (browser, proxies and reverse-proxies)
  - Expiration (Expires, Cache-Control)
  - Validation (ETag, Last-Modified)
  - Client side caching
  - Server side caching
  - Edge Side Includes

* Console
  - Built-in commands?
  - [Custom commands](https://symfony.com/doc/current/console.html)
  - Configuration
  - Options and arguments
  - Input and Output objects
  - Built-in helpers
  - Console events
  - Verbosity levels

* [Automated Tests](https://symfony.com/doc/current/testing.html)
  - Unit tests with PHPUnit 
    + test on single class
  - Functional tests with PHPUnit 
    + flow: request -> test response -> interaction -> test response
  - Client object
  - Crawler object
  - Profile object
  - Framework objects access
  - Client configuration
  - Request and response objects introspection
  - PHPUnit bridge
  - Handling legacy deprecated code

* Forms
  - [Forms creation / Forms handling](https://symfony.com/doc/current/forms.html)
  - Form types
  - Forms rendering with Twig
  - Forms theming
  - CSRF protection
  - Handling file upload?
  - Built-in form types
  - Data transformers
  - Form events (submission?)
    + Yii: `action` in form controller
  - Form type extensions
  - Yii: form has its own model extends from `CFormModel`, why?

* Miscellaneous
  - Code debugging
  - Deployment best practices 
    + flow: 1.Code 2.Dependency 3.DB 4.Cache
  - Process and Serializer components 
    + Symfony: use as DI in the controller, check [this](https://symfony.com/doc/current/serializer.html) out
  - Data collectors 
    + a composition of other field type as an array
  - Web Profiler and Web Debug Toolbar
  - Internationalization and localization

* Standardization
  - Framework interoperability and PSRs
  - Naming conventions
  - Coding standards
  - Third-party libraries integration
  - Composer packages handling
  - Development best practices
  - Framework overloading
  - Semantic versioning