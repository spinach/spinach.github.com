---
layout: post
title: "FrenchKit Quick Notes"
description: ""
category: 
tags: []
---
{% include JB/setup %}

Attended the [FrenchKit](http://frenchkit.fr/) conference in Paris. Here are my notes:**Day 1:**Talk 1: kickstarter have a quick dev loop by using playgrounds for nearly each screen (check their OSS project). That makes development much faster, but Playground can be very buggy and there are some edge cases to take care of from time to time.Idea: Use playgrounds for each widget for InstantSearch to test them quickly (PDD)Can even do UI regression tests with screenshot testing of what appears in the playground. Talk 2: UITableView and UICollectionView: for better performance, offload some work from CPU to GPU and vice versa. CPU for performance and GPU for rendering the views.
 Talk 3: Ember is opiniated, projects follow same structure. Should Swift follow this? Open question.
 Talk 4: Mock Swift using sourcery automock, because Swift is not dynamic like Objc and it's hard to mock on the fly.
 Talk 5: BuddyBuild stats around iOS: Pods 70% vs Carthage 7%. 55% of projects have no tests, and only 16% run tests.
 Talk 6 from IBM dude: Openwhisk for Serverless swift. Serverless vs Servers, and you can use a combination for optimal.
 Talk 7: Automate code reviews, Schedule time of team CR, use linters, use danger.ci
 Talk 8: Ada and spark used for critical software like aviation with emphasis on safety, more than swift.
 Khanlou: u deserve nice things:1- More expressiveness with extension, 2-reduce noise with overloaded operator3- hidden optimisation **Day 2:**

Advanced Notification: be a good citizen don t spam. Make use of content extension, title of the notif for more context.

Sketch: one step at a time. Implementation of the undo feature: moved from undo manager which redoes the steps to building an array to custom implementation using immutable trees. 
Perf tools on linux: can help find iOS perf issues by measuring, check the Callstack. Use instruments app as much as possible!!Swift 5: ABI, generics and new concurrency model are the main expectations
Scaling with CI: use jenkins/Travis then Fastlane for a lot of things: checking GH labels of PR to know if we do a beta distribution or not. Also DangerFiles. Also, for faster build time, use new Xcode build system, analyse heaviest functions by adding flags to compiler to compute timing, break ur project into components so that u only build the ones changed.But dynamic library take time to load! Butttt Swift now supports static lib in xcode9 so code modularisation is actually a good ideaCoreML: awesome-coreml-models to check online for models by communityPython converter library of models tool offered by apple  It's ok, be lazy: swiftgen, sourcery, gyro by realm. Used for constants, equatable, hashable and much more.