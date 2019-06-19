# Microservice Interfaces

This is a collection of Swagger documents describing some "building blocks" -style microservices.

## Motivation
We're working a lot with Microservices these days. Designing a complex constellation of microservices is made easier by thinking in terms of common interfaces, just like we do in Object Oriented Programming. If you can decompose your requirements enough, you can start to see how composing extremely simple Microservices can yield very robust systems. Each individual microservice is allowed to evolve on it's own, and it's very easy to reason about them in isolation. 

## Related Thinking
These interfaces are just one peice of the puzzle. We also need a "Microservice Runtime", and to think about our software in terms of the confluence of cloud technology and traditional runtime conerns (for example, the runtime concern of _linking_ maps well to _service discovery_ (or more simply, network routing), and thinking this way can help us design cloud systems that afford us the runtime dynamicism that we intrinsicly feel is possible.

More work on this topic, including a reference implementation in a Kubernetes environment, is forthcoming.

## Project Status
This is honestly just a scratch pad that I use when communicating cloud designs to my engineers. Consider all interfaces to be in Draft status.