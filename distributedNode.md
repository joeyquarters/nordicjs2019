# Building Distributed Systems with Node.js

by James Simpson

## Why go distributed?

- You'll outgrow a single server (hopefully)
- Minimize downtime

## Layers

1. **Load Balancer** (HAProxy, NGINX, Envoy, Cloud Services, etc.): Routes requests to different nodes running the same application
2. **Application** (Node.js, Python, etc.): Whatever your application runs, there are multiple nodes of this
3. **Messaging** (Redis, RabbitMQ, ZeroMQ, democracy.js): Makes those application nodes appear as though they are a single application

## Takeaways

Doing this from the start prevents a lot of headache late when you outgrow a single server.

These libraries make setting up a distributed system pretty simple.
