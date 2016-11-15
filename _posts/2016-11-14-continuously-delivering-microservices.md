---
layout: post
title: "Continuously Delivering Microservices"
description: "My notes at the o'reilly software architecture conference"
category: 
tags: [oreilly conference, tutorials]
---
{% include JB/setup %}

Miroservice Overview: Software architectural style where applications are composed of small, independent processes communicating with each other using language-agnostic APIs. Check online for characteristics.

Got started by the team giving us a workshop folder containing a box, and we used Vagrant to get it up and ssh into it. Just going through the steps in the slides to setup everything... The journey is the following: 

<img src="https://s3.amazonaws.com/oreilly-conference/Journey+Today.png" alt="Journey today" style="width: 600px;"/>

### Purpose

Purpose of using Microservice with CD (in this workshop Go-CD pipeline):
Can we actually deploy with confidence the monolith before being confident to deploy 100 microservices? That's what we're gunna go through.

Problems we usually face: It can be challenging to know when something is broken when you have 50 microservices. Is it version related? Is it because of a commit? Etc. That's why a good CI pipeline is important here to be able to quickly visualize all our microservice. With Go-CD, we have a **visual** representation of our CD system.

<img src="https://s3.amazonaws.com/oreilly-conference/go-pipeline-visual-diagram.png" alt="Go-CD Visual Representation" style="width: 600px;"/>


### Tutorial

We're taking a Musik Shop monolith app, and will it break it down into microservices. 

### Key takeaways Module 1

- Use CD Pipelines to automate your build process and provide feedback on production readiness of software
- Model your build process as a series of stages for improved feedback
- Provide scripts for building, testing, packaging and deploying your apps:
	- Store these with your app code
	- Call them from your CI/CD tool
- Build artifacts once and use them in downstream stages / pipelines
- Always tag your build artifacts with a build number
- Extend your CD pipeline to automate deployment into your environments
- Monolithic apps can be easy to build and deploy as they have less moving parts

### Module 2
The overview of our system can be seen here:

<img src="https://s3.amazonaws.com/oreilly-conference/Overview+Module+2.png" alt="Overview Module 2" style="width: 600px;"/>

Basically, in order to extract our review service in our shop-app, we change from `getStarRatingsLocalMethod()` to `getStarRatingsFromReviewService()`. 
Notice as well the difference in Ports (8090 Vs 8082)

### Domain Driven Design (DDD)
To have ubiquitous language between tech and business logic. 

#### Exercice
Airways exercise: Sort out what do our domains look like. 

Feature:

- Rewards Program
- Car Rental
- Book a flight

Possible Domains: 
- Bookings
- Customer accounts
- Flights
- Rewards
- Cars

Purpose of microservice is: we can take down a microservice and still have a running service. What if you destoy the customer accounts microservice? Everything will fall apart! so it should **not** be a domain.
So we can change our design where we put accountId and Credit card details on Flight bookings, Driving License in Car rentals, and AccountId and mailing Address in Rewards. Our source of truth will be found in each of these domains.

Also, if you have 2 domains constantly talking to each other, maybe that is a signal that they should be merged into one cohesive domain (microservice)

### Consumer Driven Contracts (CDC)
When having a lot of microservices, we have more overhead for testing since a lot of components talk to each other (when we seperated them using domain driven design). This is where consumer drivent contracts enters. 

Now for consumer dirven contracts, we have a producer that provides `{"name": "Guy", age: "24"}` and then some consumers that has a contract with the producer. Consumer A might only use the name through contract A, consumer B uses age only through contract B, and consumer C uses both through Contract C. Now if Consumer C wants to change the contract so that it gets `firstName` instead of `name`, producer can definitely do that. But that will make contract A fail! So with CI, we can catch the test failing very quickly before production, and fix the bug.

### Wrap up
Remember that extracting a lot of microservices is not always good! Sometimes it causes more problems than it solves. Remember that you'll have more error handling to do for example.
With Microserice, you can chose the right tool/tech for the problem. Microservices have an advantage that the communication done through agnostic APIs. REST JSON is one of the most popular ways, but there are other ways. 

Why micrservice now?

- Infrastructure automation
- Virtualization on demand
- Continous Delivery
- DDD

Monolith: 
It's actually a great starting point. Don't have to deal with more complicated complex. I just have one app. But as my app grows, my complexity increases and hard to work together with a team of 10 devs. The drawbacks for monolith is:

- Complexity increases
- Difficult to change
- Low reusability
- Slow to deploy
- Testing takes time
- High cognitive load (so many things that can break a whole monolith codebase, but for microservice, you focus more on specific domain)
- Reliability and scale is hard

Advantages of Microservice:

- Decentralized governance
- Flexibility of tool/tech
- Standardize on integration, not platform 

<img src="https://s3.amazonaws.com/oreilly-conference/decentralized+goverance.png" alt="Decentralized governance" style="width: 600px;"/>

Following Conway's law, we change the way team in a company are structured. Intead of having a service team, UX team, dev team etc (which don't know much about each other), we now have "features team" consisting of devs, devops, UX etc... Each team owns a feature, and not an area of expertise. For example, we can have a feature team that takes care of payments.