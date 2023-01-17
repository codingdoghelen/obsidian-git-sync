- Decoupling
- Decentralize
- Use of RESTful API
- Independently Deployed
- Individual Loosely Coupled services


---

## How Microservices communicate with each other?
Use of HTTP/REST with JSON payload



兩個最常被 Microservices 使用的 protocol 是 HTTP (request-response with resource API) 還有 ==lightweight== messaging。前者非常的 cache-friendly (?) ，常常被使用到的 resource 可以被輕易地快取。至於第二種方法，則常常使用像是 [RabbitMQ](https://www.rabbitmq.com/) 或是 [ZeroMQ](https://zeromq.org/) 。這些機制都只是提供一個訊息傳遞的路由器（message router），自己並不會保留資訊，而資訊都存在於 endpoint 中。

CDC - Consumer-Driven Contract. Consumer tells what they need.

**API should never return list** - Should return a map

How microservices communicate in [[Java]]?
- [[Spring Cloud]] [[Eureka]]
- [[Kubernetes]]









