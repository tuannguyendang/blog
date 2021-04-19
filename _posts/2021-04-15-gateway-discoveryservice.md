---
layout: post
title: Gateway and Discovery Service
---

Discovery service [Eureka](https://cloud.spring.io/spring-cloud-netflix/multi/multi_spring-cloud-eureka-server.html) registry services

Application Gateway [NextFlix Zuul](https://github.com/Netflix/zuul) implement in your application

Sidecar Gateway [Kong](https://konghq.com/) install independent with application

### Discovery Service

Discovery service auto detection of devices and services

* Discovery service , client
* [More information](https://microservices.io/patterns/server-side-discovery.html)
* [My Sample](https://github.com/tuannguyendang/microservice/tree/master/registry)
* ![http://localhost:8761/](https://tuannguyendang.github.io/blog/public/img/20210415/eureka.png)

### Application Gateway

Gateway router request to services, implementation in application

* [NextFlix Zuul](https://github.com/Netflix/zuul)
* [My Sample](https://github.com/tuannguyendang/microservice/tree/master/gateway)

### Sidecar Gateway

Install independent with application and language.
* [King Kong](https://konghq.com/)

### Next post

* More information about Kong Gateway

### Download

* All the code you need [here](https://github.com/tuannguyendang/microservice)

Thanks!
