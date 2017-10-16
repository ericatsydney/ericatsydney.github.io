---
layout: post
title:  "PHP Knowledge Map"
date:   2017-10-13 13:30:00 +1000
categories: Geek
---
When checking the [Symphony certificate](https://sensiolabs.com/en/symfony/certification.html), found this list of knowledge area.

I think it's realy good starting point to prepare my php knowledge base for the general MVC framework.

* PHP and Web Security
  - PHP 5.3 to PHP 5.6 API
  - Object Oriented Programming
  - Namespaces
  - Interfaces
  - Anonymous functions and closures
  - Abstract classes
  - [Exception and error handling](http://ericatsydney.github.io/geek/2017/10/10/php-exception-handling.html)
  - Traits
  - PHP extensions ?
  - SPL
  - Web security (XSS, CSRF, etc.)

* HTTP
  - Client / Server interaction
  - Status codes
  - HTTP request
  - HTTP response
  - HTTP methods
  - Cookies
  - Caching
  - Content negotiation
  - Language detection
  
* Framework Architecture
  - Symfony Standard Edition
  - Components (Usually PHP Library managed by Composer)
  - Plugins / Extensions/ Bundles (how to register and inside folder structure?)
  - Bridges?
  - Configuration
  - Code organization
  - Request handling
  - Exception handling
  - Event dispatcher/ Subscriber (Sololearn)
  - Kernel events
  - Official best practices
  
* Standardization
  - Framework interoperability and PSRs
  - Naming conventions
  - Coding standards
  - Third-party libraries integration
  - Composer packages handling
  - Development best practices
  - Framework overloading
  - Semantic versioning
  
* Bundles
  - Naming conventions
  - Code organization
  - Controllers
  - The views
  - The resources
  - Overriding default error pages
  - Bundle inheritance
  - Semantic configuration and compiler passes

* Persistence
  
* Controllers
  - Naming conventions
  - The base Controller class
  - The request
  - The response
  - The cookies
  - The session
  - The flash messages
  - HTTP redirects
  - Internal redirects
  - Generate 404 pages
  - File upload
  - Built-in internal controllers
  - What's front controller? It's used to provide a centralized request handling mechanism so that all the requests will be handled by a single handler.
  
* [Routing](https://symfony.com/doc/current/routing.html)
  - Configuration (YAML, XML, PHP & annotations)
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
  
* Templating with Twig
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
  - Form type extensions

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
  - [Authentication / Users / Roles](https://symfony.com/doc/current/security.html)
  - Authorization
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
  - Unit tests with PHPUnit (test on single class)
  - Functional tests with PHPUnit (request -> test response -> interaction -> test response)
  - Client object
  - Crawler object
  - Profile object
  - Framework objects access
  - Client configuration
  - Request and response objects introspection
  - PHPUnit bridge
  - Handling legacy deprecated code

* Miscellaneous
  - Code debugging
  - Deployment best practices (1.Code 2.Dependency 3.DB 4.Cache)
  - Process and Serializer components (use as DI in the controller, check [this](https://symfony.com/doc/current/serializer.html) out)
  - Data collectors (a composition of other field type as an array)
  - Web Profiler and Web Debug Toolbar
  - Internationalization and localization




