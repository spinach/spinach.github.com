---
layout: post
title: "An architecture for merging fast data and enterprise applications: The SMACK stack"
description: ""
category: 
tags: [oreilly conference, sessions]
---
{% include JB/setup %}

## TL;DR

- SMARK: Spark, Mesos, Akka, Cassandra, Kafka
- Each one has pros and cons. they can work so well together though in same architecture! Each covers a niche that the others don't cover
- Good synergy between Fast data and microservices, same design principles needed
- Streaming pipelines > 3-tier architecture

<br/>

## Full Version

Hadoop:

- Very large data sets
- Batch jobs: table scans
- Job Durations: minutes to hours
- Latencies: minutes to hours

Spark has become very popular.
Yarn is also good.

Job gunna compute something, due some work, and then go away. mapreduce stuff.

We want to get answers asap. Back int the days, Google would scrape every now and then, and update the index. But that is not good for breaking news for example, index won't be up to date! 

There are new ways to solve these problems. As an example, speaker gave an architecture with 4 **streams**. 

Streaming: 

- Never ending sequences (Kafka). Data constantly flowing through the system
- Incremental processing. (for breaking news)
- Job durations: forever! 
- Latencies: usec - seconds

SMACK:

- Spark
- Mesos
- Akka
- Cassandra
- Kafka

Spark: Core is the Apache Spark. On top of it, there are 4 components horizontall:

- Spark SQL: Highly optimized SQL
- Spark Streaming: Stream processing
- MLlib: machine learning
- GraphX: Graph data structures to represent data

Streaming Tradeoffs:

- Latency: is it ok to respond in seconds? minutes? depending on the needs.
- Volune: some engines are very good for low volume. whereas Spark has a lot of overhead to work with a lot of data, so good for large volume.
- Kind of data processing and analytics required?
- Bulk processing of records?
- Individual processing of events?

Akka: For big data streams, built as part of JVM. Think of it as a stream, data flow. Good for:

- Low latency
- Low volume
- Complex flows
- **Per event**

Spark good for:

- Med Latency
- High Volume
- Data flows, SQL
- **En Masse**

Flink good for:

- **Low latency**
- High Volume
- Data flows, correctness
- En masse

Kafka streams:

- Low latency
- Med volume
- **ETL "tables" **
- Data flow / per event

Mesos analgous to YARN. Each framework provides its own scheduler. Mesos offers you resources, and you can either refuse or accept them.

Spark cassandra and kafka work so good together actually.

Kafka has been baked in Netflix for 8 years. Millions of messages go through the kafka queues. It's pretty stable.

Running through Kafka is still a single point of failure, BUT it's a distributed system that is highly available, so can trust it. So we can point pour service and internet through kafka, and in turn it will redirect to the appropriate services.

Fast data and microservices: will they converge?

Synergies: they have similar design. each stream/microservice does one thing. They both encourage async, and they both need to be run for a long time with high availibility. So they have good similarities. 

Example Twitter: used to be 3-tier architecture. Data was 2nd thought. When twitter grew, twitter became more like streaming pieplines (data 1st), goes through different services, eventually they join, and then some callback is called, and request is sent back to browser.