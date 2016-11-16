---
layout: post
title: "Opening keynote: Going Serverless"
description: ""
category: 
tags: [oreilly conference, sessions]
---
{% include JB/setup %}

## TL;DR
- Serverless: Function-as-a-service. We remove host instance and application process. We're kept with just operations
- At Netflix: you build it, you run it. Prefer iteration over Big Bang. 
- Chaos Engineering: Run crazy monkey that randomly kills services

## Full Version

Serverless is truly facinating, and will shake up the way we do things. 

- Back to 1996, Servers were inside the office of the company offering the web service. 
- In 2001, company moves their servers from their offices to datacenter companies: to reduce costs and have better expertise people
- In 2006, Amazon announced Elastic cloud computing EC2: Any company can rent machine on demand. Why was that good? With infrastructure as a service, the lead time goes from months to minutes. Also, it offers scalability. Amazon was able to do it due to economies of scale
- Now Serverless: Next evolution of cloud computing. 

BaaS (Backend-as-a-service) came up lately: Products like Firebase and Auth0. They build these functionalities so that we don't have to worry about them. We can use them and bundle them in our app.
FaaS (Function-as-a-servie) came now: that gave rise to "Serverless"

- in BaaS, we have a host instance, an application process, and then operation.
- in FaaS, we remove host instance and application process. We're kept with just operations. 

FaaS trigerring events
- Message Bus
- Network File System
- Time Event
- Http Request

FaaS = No management of Server Hardware or Server Processes. Teams don't have concerns over servers, or hosts etc. 

AWS Lambda is the first one that offered FaaS.

`Serverless = BaaS + FaaS`

Why Serverless:

- Reduced Labor Cost
- Reduced Infrastructure cost
- Increased Scaling Flexibility (they only use precisely what they need, and they scale automatically, no need for preventation. No planning.
- Shorter Lead Time. 

Short Cycle time is good, but shorter lead time is even better. Serverless considerably reduced development and setup time to try out experiments and MVPs.
Not than this does not mean that we have NoOps, we still have to take care of security among other things. 

This stuff is really new, and still under construction.

Drawbacks:
- Infrastructure outsroucing = Loss of Control. The more tech you outsource, the  more your success depends on your vendor. You better trust your vendors.
- Tools
- Latency 

Serverless is not good for everything ofc. It's great for building MVP and experimenting for sure, because in 1h you can have an experiment up and running.

--- 
Dianne Marsh from Netflix Director of Engineering.
Balancing Bias to Action and PLanning. 

We're gunna hear a lot of things from microservices to containers to serverless. 
At Netflix, they master the microservice model, and that makes team independent an be able to innovate independently of other teams. 

At Netflix: you build it, you run it. They don't have rules about how to run, test coverage, or things to do inside service. You are responsible to run the service. That is aligning developer's freedom with his responsibility.
The teams:

- are Resilient to failures
- Own the default behavior of the service. If something bad happens, they still should show default list of movies. 
- use Hystrix open source (they don't expect teams to do everything ofc..)
- acknowledge the risks. There are risks in the cloud, especially in distributed systems.

Chaos Engineering: the discipline of experimenting on a distributed system in order to build confidence in the systems capability to withstand turbulent conditions in production. They run this monkey that kills services randomly at random times, and see if we're resilient. 

Prefer iteration over Big Bang. 

Netflix made sure to share what they're ve built: spinnaker, chaos, vizceral, eureka, ribbon, hystrix, zuul. Can check `techblog.netflox.com`
