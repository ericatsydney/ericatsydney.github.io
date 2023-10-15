---
layout: post
title:  "Logging and Monitoring"
date:   2021-11-29 19:49:00 +1000
categories: Geek
---

Zipkin: Zipkin is a distributed tracing system. It helps gather timing data needed to troubleshoot latency problems in service architectures.

Sleuth: Spring Cloud Sleuth provides Spring Boot auto-configuration for distributed tracing.

Auctuator:  

Actuator brings production-ready features to our application.  Monitoring our app, gathering metrics, understanding traffic, or the state of our database become trivial with this dependency 

> Actuactor is mainly used to expose operational information about the running application - health, metrics, info, dump, env, etc. It uses http endpoints or JMX beans to enable us to interact with it.


Mirometer: 

Micrometer is a dimensional-first metrics collection facade whose aim is to allow you to time, count, and gauge your code with a vendor neutral API.

> Mircrometer automatically exposes /actuactor/ metrics data into something your monitoring system can understand. All you need to do is include that vendor-specific merometer dependency in your application. Think SLF4J, but for metrics.


Prometheus: 

Prometheus is an open-source systems monitoring and alerting toolkit

> It is time-series database that stores our metric data by pulling it (using a built-in data scaper) periodically over HTTP. It also has a simple user interface where we can visualize/query on all of the collected metrics.

Grafana: 

a visualize framework to present the data

> Grafana can pull data from various data sources like Prometheus and offers a rich UI where you can build up custom graphs quickly and create a dashboard out of many graphs in no time. It also allow you to set rule-based alerts, for notifications.

Consul: service mesh, miroservices based networking.

Zuul: API gateway

Log4J logback-spring.xml

Reference: Master Microservices with Java, Spring, Docker, Kubernetes by Eazy Bytes



