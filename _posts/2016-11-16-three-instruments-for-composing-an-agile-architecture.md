---
layout: post
title: "Three instruments for composing an Agile architecture"
description: ""
category: 
tags: [oreilly conference, sessions]
---
{% include JB/setup %}

## TL;DR

- Organize, customise, scrutinize, repeat
- Organize: Get resuable parts, Modular characteristics, component interactions
- Customise: Production variations techniques, Instance attributes, Startup Variations Examples
- Scrutinize: Monitor growth

<br/>


## Full Version

Overreacting to changes leads to:

- Duplication
- Ambibuous interfaces
- Inflexible
- Disorganized
- Tight coupling

What is not Software architecture:

- Component design
- System design
- Component selction

But it makes the above easier. 

Agile software architecture: How?

#### 1- Organize

Function follows form:

- Organize for modularity
- Modularity facilitates evolution
- Evolution over reinvention

Get reusable parts

- Components specification
- Interface profiles
- Protocols
- General scenarios

System specific parts (not general), that will change when moving systems

- Startup, Shutdown
- Monitoring, Logging, Analytics
- Error Handling

Modular characteristics:

- Cohesive functionality
- Precise interfaces
- Limited knowledge of servers
- No knowledge of clients

Component interfactions:

- Strongly typed interfaces. The stronger the better.
- Task protocol (session, broadcast, subscription). 
- Preconditions

#### 2- Customize

Making the most of your software asset. One agile archecture that give us:

- Many environments
- Many technologies
- Many designs

Production variations techniques

- Conditional compilation
- make files
- code generation

Instance attributes

- Min and max values
- Physical sizes
- Environment constraints

Startup Variations Examples

- Robots
- Sleep management system
- Self driving vehicles

Slides: http://conferences.oreilly.com/software-architecture/engineering-business-ca/public/schedule/proceedings

#### 3- Scrutinize (examine and inspect thoroughly)

Monitor growth

- Creeping component complexity
- Interdependent knowledge
- Over specialization
- Subject matter leaking

Ways to Scrutinize:

- Inspect: documentation, tests, construction, defects, requirements
- Reuse: UTs, drivers, simulators, vary environment
- Measure: changes, multiple owners, growth, defects

Organize, customise, scrutinize. REPEAT

> The only thing that never changes is that everything changes.

