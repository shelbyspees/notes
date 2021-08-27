---
aliases: [web services]
---

aka: programs running on other people's computers but you can use them.

## what is a web service

I remember reading that "the cloud is just someone else's computer" and not really getting it for a long time. Like, I vaguely understood that there existed giant warehouses of server rooms with walls of racks containing lots of fans and lights and probably some computer parts. I didn't understand *how* things got from my computer to these warehouse servers and back, just that it somehow happened.

I want to reference the classic interview question and the amazing community effort at putting together a thorough response: [https://github.com/alex/what-happens-when](https://github.com/alex/what-happens-when)

When I started reading through that repo however many years ago, I quickly got super frustrated trying to parse all this terminology and all these concepts. I'm not the kind of person who can just sit down and read technical things straight through and remember them. (I used doubt it was even possible, until I met a few people who could do so. Literally, wizards.) When I'm learning, I need to interact with the system in context and question it like, why does this even exist? what problem is it trying to solve?

So that's how I want to approach thinking about web services. For each piece of the system, what's even the point? Maybe I can demystify things for someone who's stuck like I was.

## what's a service though

A service is a kind of software program that keeps running continuously. There are many reasons to do this:

- the user can interact with the program immediately without waiting for it to start up
- a program running on a single machine can be accessed by many users, instead of having a separate instance for each user
- allows for efficient use of memory and disk storage for different goals
- program is available for synchronous tasks, and can delegate asynchronous tasks elsewhere
- lots of other reasons

You interact with many web services every day, and as a user you never have to think about starting up or configuring that software. The teams running these services use additional tooling to automate those steps, which becomes especially important when you're releasing changes for millions of users.

## service reliability

The term *reliability* refers to this idea of making sure the overall software service experience meets expectations for users. In distributed systems where a service might have many components across many different machines, it can be difficult to measure service reliability, let alone guarantee it. Still, a lot of really good work has gone toward improving reliability across software systems.

Softwares teams have improved testing, version control practices, build tooling, release processes. See:

[The Twelve-Factor App](https://12factor.net/)

Infrastructure teams lean on auto-remediation strategies, such as autoscaling and failovers, to ensure that isolated errors can't take down the whole system.

## resources

[What happens when you type a URL into your browser?](https://aws.amazon.com/blogs/mobile/what-happens-when-you-type-a-url-into-your-browser/) by [Jenna Pederson](https://twitter.com/jennapederson)

[The RED Method: key metrics for microservices architecture](https://www.weave.works/blog/the-red-method-key-metrics-for-microservices-architecture/)


further reading:
- [production excellence](tech/production%20excellence.md)
- [service level objectives (SLOs)](tech/service%20level%20objectives.md)