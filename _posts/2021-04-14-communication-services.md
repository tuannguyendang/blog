---
layout: post
title: Communication between services
---

<div class="message">
  Communication between services and client (web app, mobile app) to services
</div>

- **REST API**
- **GRPC**
- **KAFKA**
- **OUTBOX pattern**

[Communication In Microservice](https://tuannguyendang.github.io/blog/public/img/20210414/Communication.png)

## REST API
[Best practice design rest api](https://www.vinaysahni.com/best-practices-for-a-pragmatic-restful-api)
<table>
  <thead>
    <tr>
      <th>HTTP Method</th>
      <th>Use For</th>
      <th>Description</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td>GET</td>
      <td>READ</td>
      <td>Get resource state</td>
    </tr>
    <tr>
      <td>POST</td>
      <td>CREATE</td>
      <td>Create new resource</td>
    </tr>
    <tr>
      <td>PUT</td>
      <td>UPDATE</td>
      <td>Update exist resource</td>
    </tr>
    <tr>
      <td>DELETE</td>
      <td>DELETE</td>
      <td>Delete resource</td>
    </tr>
  </tbody>
</table>

## GRPC
[gRPC](https://grpc.io/docs/what-is-grpc/introduction/) is a binary message-based protocol

### KAFKA
Message Queue

### Some Questions
- What is ACID ? Atomic, Consistent, Isolated, Durable
- How can we apply Saga pattern in microservices ?
- Why Kafka ?

### OUTBOX pattern
https://tuannguyendang.github.io/blog/public/img/20210414/outboxtransaction.png

JMS message sent out will insert to the outbox table in the same transaction with the service table. Using debezium or some other data event tool to publish messages to kafka. Or use scheduler job reading and send messages to kafka.

For more information [here!](https://microservices.io/patterns/data/transactional-outbox.html)

-----

Want to more information? <a href="https://google.com/">ask Google</a> || contact me **tuan193@gmail.com**
