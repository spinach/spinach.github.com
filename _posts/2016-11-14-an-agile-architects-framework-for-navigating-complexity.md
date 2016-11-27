---
layout: post
title: "An Agile Architect's framework for navigating complexity"
description: "My notes at the o'reilly software architecture conference"
category: 
tags: [oreilly conference, tutorials]
---
{% include JB/setup %}

First before tackling any problem and trying to solve it, first make sure to identify exactly what the problem is. 

## TL;DR
- System: `Fragile < Robust < Resilient < Antifragile`
- Differient betwen problem domains: complex, complicated, obvious and chaotic
- Dealing with complex domain using experiment design

<br/>

## Full Version

### the Cynefin Framework

Systems, in order of how good they are

`Fragile < Robust < Resilient < Antifragile`

- Fragile: Can withstand only small challenges
- Robust: Can withstand good challenges
- Resilient: Can bounce back from challenges
- AntiFragile: Can get stronger due to challenges

#### Domain model vs category model

Category model: Have the category before even phrasing the problem. Then depending on the what the problem is, we put the category

Domain model: We create the domains from the problem, not the other way around.

#### Problem domains:

- Complex domain (Enabling constraints) (probe-sense-respond): We know what is the problem. we don't know exactly what are the exact steps to solve the problem.
Example: Immagine a very difficult problem you solve. It is a problem you solved, but looking back, you couldn't have predicted the exact way to solve the problem. In order to tackle these, cut the problem into smaller chuncks, through series of trial/errors and experimentations. "Probing the environment, and then respond and take appropriate action"
- Complicated domain (Governing constraints) (sense-analyse-respond): I don't know what the exact problem is. I want to sense what is the problem: I do some analysis on what the problem is, and then I respond.
- Obvious domain (Rigid constraints) (sense-categorise-respond): It is an obvious problem, there is a best practice to deal with it, no need to think too much about it. 
- Chaotic domain (Absense of constraints) (act-sense-respond): Immagine there is a room on fire. We're not gunna do analysis on why. We have to act quickly, "go to exit door quickly". Later on, you come back and analyse. 

Disorder: When there is a problem and no one is dealing with the problem. 

#### Closer look in Complex domain

We look at experiment design:

- Where are the actions you will take?
- What are the expected signs of success?
- What will you do to encourage more of these things?
- What are some possible signs of failure?
- What will you do when you encounter these?
- How does this experiment support your overall objective?

## Slides
[www.softwarearchitecturecon.com/slides](softwarearchitecturecon.com/slides)