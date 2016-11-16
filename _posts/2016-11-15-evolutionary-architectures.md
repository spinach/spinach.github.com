---
layout: post
title: "Evolutionary Architectures"
description: ""
category: 
tags: [oreilly conference, sessions]
---
{% include JB/setup %}

## TL;DR
- Dynamic equilibrium: we can't predict the future, so what can we do? We can have a plan that is adaptable, evolvable
- Dimensions of architecture. from 1 in monolith to n in microservices
- Composoability will let you build better evolvable systems
- Apply incremental change: Wire them into continous deployment pipeline. 
- Identify fitness functions, whether atomic or hollistic. Can be automated or manual, but automated is better
- Bring the pain forward
- Consumer driven contracts good for testing
- We have to be `reactive` to unknown unknowns, rather than `predictive`. 
- Switch to domani-centric architectures
- Feature Toggles: A/B testing. Facebook a good example

## Full Version

ilities example:

- Scability
- Resiliency
- Security
- Evolvibility

Dynamic equilibrium problem: If you planned 2 years ago for an architecture for next 5 years, without docker, then after 2 years, you should drop your plan.
Well, we can't predict the future, so what can we do? We can have a plan that is **adaptable**, **evolvable**.

Dimensions of Archietcture:

- Technical/Software arcitecture: what software tools to use to do the job.
- Data Architecture: how it is organised, how things are partiioned. We should focus more on "evolutionary database design"
- Security architecture
- Domain architecture: coming from the domain-driven design

Let's talk more of the technical architecture, which is layered Architecture. presentaiton -> business -> persistence -> database layer. It is a pass-through architecture, which has to go through all of the layers. And what if we want to add business -> service (optional) -> persistence layer, we add one more dependency, so if want to change persistence layer, will have 2 dependencies, which is not evolvable. `dimensions = 1`

Then came Microservices, `dimensions = n`. We can swap out implementation of a part without affecting the other parts. **Composoability** will let you build better evolvable systems. 

**Incremental Change** is when separate components are deployed independently. Dependent components with time route to new deployed component. Then the old component dies once no one is using it. That is incremental. We want to decrease cycle time at the end of the time.

Features are released and then applications consist of routing

**Fitness functions**: determines if the next version is better than last version. It is an objective function that measure some metric. So we define architecture fitness functions in order to make sure we evolved in the positive way, whether it is using metrics or tests.
We have atomic functions, which are application level functions that does one thing. And we have holistic fitness function which runs the interaction between the different services (integration tests are an example).

**Bring the pain forward**: Pain increases exponentially with the time you wait to act (sync codebase, deploy to prod). Hence Continious delivery. 

Deployment pipeline: directly run your build trhought UTs, function test etc.. and automate all these things. 

When changing something in microservie, 2 things to verify: Did I break production? and then did the thing that I add work? Hence came the idea of staging.

Consumer driven contracts good for testing. each consumer defines the contract of what they need, and the producer promises that the test in this contract stays green. So if producer changes and tests are ok, then all good and can keep moving forward, keep evolving. 

- Known unknowns: things we know that we don't know.
- unknown unknown: things we don't know that we don't know.

We have to be `reactive` to unknown unknowns, rather than `predictive`. 

DDD's anti-corruption layer: instead of wiring yourself directly to a library, wire yourself to an interface to that library. 

Switch to domani-centric architectures. 
We rarely change persistence layer, and always change to customer demands. So the layered architecture above is flipped so that a domain encapsulates the 3 other layers (business, persistence, database). So think of your architecture as a domain. 



####Summary

Evolutionary architecture:

- Choose dimensions you care about for evolution, "the ilities"
- Identify fitness functions, whether atomic or hollistic. Can be automated or manual, but automated is better
- Apply incremental change: Wire them into continous deployment pipeline. 
- Feature Toggles: A/B testing. Facebook a good example

Evolutionary architecture opens up the door to more desirable 21st century processes. Can easily A/B test, swap up parts etc. Great quick feedback loop with this kind of architecture, **agile**.
[evolutionaryarchitecture.com](http://evolutionaryarchitecture.com)