---
layout: post
title: "Application caching at Netflix"
description: ""
category: 
tags: [oreilly conference, sessions]
---
{% include JB/setup %}

## TL;DR
- Netflix Pioneer of microservices
- Caching team consists of 4 senior engineers, that handles caching for literally everything at Netflix (whether logins, profile movie etc)
- EVCache is what they're currently using
- Build resilient system because even AWS can fail on us.
- Working on Moneta to reduce costs to 70%. 

<br/>

## Full Version

90 seconds to impress you when using Netflix. This moment of truth. 

Caches touch:

- Signup
- login
- choosing a profile
- picking liked videos
- personalization
- loading home page
- A/B tests
- video image selection
- and many many more

Netflix uses EVCache: Ephemeral Volatile Cache, key-value store.

Why optimize for AWS. well, AWS kills more machines than the crazy monkey. 

- instances disappear
- zones fail
- regions become unstable
- network is lossy
- customer requests bounce between regions
- failutre happen and we have to be ready

EVCache:

- 100s TB of data
- triollions of ops/day
- 10s billions of items stored
- 10s millions ops/sec
- millions of replications/sec
- thousands of servers
- 100s of instances per cluster
- 100s of microservice clients
- 3 regions 
- 4 engineers

To keep home personal page up to date, there is offline compute time every day that will do the computation and will put it in the EVCache. The EVCache is the boundary beetween the offline services and online services. 

<img src="https://s3.amazonaws.com/oreilly-conference/netflix+cache.JPG" alt="Netflix cache" style="width: 600px;"/>

Polyglot clients: They've always been using Java that talks directly to EVCache. but they now put an http proxy so that anyone internally can write apps in python, ruby, go or anything, and talks through http rest to the EVCache.

EVCache is the state, and the app are stateless. 

Moneta: evolution of EVCache. It is EVCache on SSD.

EVCache: All data stores in RAM in Memcached

Rend project
get get github netflix

Menmonic: open source soon
Manages data storage on SSD, reuses rend server libraries, and maps memcached ops to RocksDB ops.

EVCache and rend are Open source project. Can also check techblog of Netflix.