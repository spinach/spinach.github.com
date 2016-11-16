---
layout: post
title: "Microservices pros and cons"
description: ""
category: 
tags: [oreilly conference, sessions]
---
{% include JB/setup %}

## TL;DR

- Great talk to summarize pros and cons of microservices
- For MS: Decentralised Governance, Scale & resilience, Replaceable services, Conway's law. If you chose MS: You need to be really good at CD, Quality assurance, monitoring. 
- Vs MS: Cognitive complexity, monitoring hell, configuration complexity, Integration difficulties
- Whether For MS or Vs MS, make sure to follow the more general principles such as seperation of concerns or SRP.

## Full Version

The famous ball of mud. The common architecture pattern.

Microservices are awesome Vs Microservices WTF! 

- For MS: Decentralised Governance: The right tool for the job
- Vs MS: Cognitive Complexity: More microservices to deal with, more languages to learn, harder to refactor, extra work! Without MS, we get one single codebase straightforward
- Vs MS: Monitoring becomes hell! Have to log everything now and use correlationId. leads to more complexity. 
- For MS: Scale & Resilience. Can Scale independently (for big holdiays for example). Design for failure.
- For MS: Deployment independence. Components are deployed, features are released, and we're not gunna take everything down. Plus easier to kill old code.
- Vs MS: Configuration complexity, because deployment is independent. In Monolith, it s one deployment. More tools for people to learn. BUT, for MS point, you can unify deployment and tools used. 
- For MS: Replaceable services. Easy to replace modules. Much harder for monolith. Being **agile**.
- Vs MS: Integration difficulties. MS promote coupling from application to integration architecture. Have to think about network, boundaries, latencies. It's Vs cohesion and coupling. We have to build modular monolith system in the fisrt place, no need to have distributed systems. 
- For MS: Conway's law: Teams design are your first draft of your archtiecture. We want to think of teams first. Build team that reflects your software architecture

If you chose MS: You need to be really good at CD, Quality assurance, monitoring. 

Products, not Projects. Teams will keep on rotating. 

Whether For MS or Vs MS, make sure to follow the more general principles such as seperation of concerns or single responsibility principle. Else, you are moving complexity to your architecture which is the worst thing that could happen to your product. 