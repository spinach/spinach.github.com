---
layout: post
title: "Introduction to reactive applications and reactive streams"
description: ""
category: 
tags: [oreilly conference, sessions]
---
{% include JB/setup %}

### Problem

1- Thread pool: Performance demands are always increasing. 

Site performance is very important. A study was done on user behavior showing that: 

- 0-100 ms: instant
- 100-300 ms: slight perceptible delay
- 300-1000ms: Perceptible delay
- 1s: Mental context switch
- 10s+: I'll come back later

2- The rise of microservice: Increase of distributed systems, where there are multiple integration points. A lot of interfaces: DB, 3rd party APIs, other services. 

### Solution

Embrace Reactive Applications. This word was made famous in Sept.2014 in the Reactive Manifesto. 

4 principles in order to properly fulfill user demand. 
Being reactive is not a library or framework. It is a set of design principles that your app should meet.

1- Responsive. It should respond to user interaction asap. Whether it is http request, or button click etc. 
Amazon experimented with added 100ms to each interaction -> 1% decrease in sale

2- Resilient. Embrace Failure. Everything can break, so should guard against it. Independent things should fail independently. 

3- Elastic (scalable)

4- Message-Driven. Free up resources with Async operations & non-blocking I/O

Now do all of this at ALL levels of your stack

Async is hard for humans! But One excellent tool is reactive streams. 

#### Reactive streams (Rx)

- Single abstraction over data from many sources. 
- Observer pattern: with push and (pull based) iterators
- Stream-based functional programming
- Makes async behavior easy
- Provides (Reactive pull) backpressure: ability for subscribers to communicate through observables.

Rx simplifies complex work. At the beginning it is challenging and complicated. But once you get the hang of it, becomes good.

### Deep dive

An observable is like a promise ++. Observables are most powerful when wrapping an external input. An observable epushes down an items to the observers. Observables and subscribers operate on a scheduler. 

Observable pattern is a core part of Rx.

Streams are composable. Don't need to have subscribers all the time.

5 main functions that we usually use

- filter returns a bool 
- map returns Object that you define
- reduce returns Object that you want
- groupBy. split streams into n number of steams, based on your criteria.
- flapMap. from n observables to 1 observable. 

Cold streams/observable: Finite data, on demand. only emits data on.subscribe

Hot observable: infinite data, as it's ready. emits always data.

Asnychronous streams: can use Observe**On** and subscribe**On** to run things in background

Stream interactions:

- Don't unsubscribe from observables. Programmatically complete them when another observable fires. Example of searching in search box, and if have 2 queries happening for "mo" and "movi", need to kill the first one "mo".. Rx will help you with just 5 lines of code to do that. use throttle/debounce and stuff like that. 

Flowable is an observable, with some extra apis that you can use.

Focus on Intra-Service operations, for JVM. Some popular libraries:

- RxJava
- Akka
- Reactor
