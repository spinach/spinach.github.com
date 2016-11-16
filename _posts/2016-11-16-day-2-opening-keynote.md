---
layout: post
title: "Day 2 Opening Keynote"
description: ""
category: 
tags: []
---
{% include JB/setup %}

### Design Pressures
We tend to

- Fashion/trends
- REsume Driven Development
- Vendor Marketing
- Expressing Identities 

This will pressure the design to go in certain ways. 

Quality attributes: 

- Exectution (Service): Security, performance, usability, reliability
- How extensible is it, debuggable, testable. 

Typical requests:
`IO -> Decode -> Compute -> Archive -> Encode -> IO`

But had to do concurrency in that "pool of thread" model request. Plus we get contention in database, or race condition.

Solution: **Pipelines architecture**, and not **coarsed grained parallelism**

#### Pro Tips

- Queues are everywhere, let's make use of them
- Coupling & Cohesion -> performance and adaptable.
- Be Deliberate with dependencies
- Measure Everything, stop guessing

**Feature Envy** is what usually causes messes in codebases. Put fields in classes they belong, Make them cohesion intead of introduction coupling. That inherently makes performance 30% better just by making things cohesive. 

Synchrous communications is the crystal meth of distributed computing. 

Monitoring and telemetry will tend to drive performance and good observibility. Especially for microservices. You have to build the following from the very very start. 

- profiling
- counters
- histograms
- event logs
- tracers

Averages are bad for telemetry, as this hides the outliers and the errors that are going on. Better to use percentile distributions.

What skills should we be practicing everyday? Focus on buildng good systems that are cohesive, decoupled, instead of just learning the new fads. 
