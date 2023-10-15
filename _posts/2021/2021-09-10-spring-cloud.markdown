---
layout: post
title:  "Spring Cloud Config"
date:   2021-09-10 8:19:00 +1000
categories: Geek
---

[Spring Cloud](https://spring.io/projects/spring-cloud) provide quite a few features. And I think configuration is the most known and the widely used one.

Spring Cloud Config centralise the configuration into a single place on the cloud, it help you to manage config across all environment, it makes sure the distributes instances can share the same config, and also enables the CI/CD can deploy the code without the messy setting of preset config.

In order to use the Spring Config, the setup is light weight:

- setup the spring config uri in bootstrap.yml

- make sure Spring Boot Actuator and Spring Config Client are on classpath

- make some of the config shared by different application?

[Reference](https://spring.io/projects/spring-cloud-config)
