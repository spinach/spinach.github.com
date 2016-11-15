---
layout: post
title: "Serverless architectures: what, why, why not, and where next?"
description: ""
category: 
tags: [oreilly conference, sessions]
---
{% include JB/setup %}

The Serverless area is getting bigger and bigger. It is not just a fad. 

Evolution of cloud:

- Infrastructure-as-a-service: AWS, Google Cloud Platform, private cloud
- Platform-as-a-service: Think of hosting application rather than OS. Heroku, private cloud
- Container-as-a-service: Came 3 years ago. Takes away also OS. Docker.
- Serverless: Backend-as-a-service + Function-as-a-service. 

Example for Serverless

- Client -> BaaS for auth or database (firebase)
- Client -> API Gateway -> FaaS.

We have no service of our own, we rely on 3rd party services. FaaS is good for http request and timely cron jobs as well.

### Case studies

For a small company with 1 request/min

- Traditional EC2 m1.small = 245$ / year
- Lambda Solution with 1GB RAM = 1.75$ / year

Some small companies reduce their infrastructure costs to nearly 0, especially when using free tier.

Another example:

Mean utilizzation: 5 request / sec.

- Traditional EC2: 2x EC2 m3.medium = 841$ / year
- Lambda solution with 1GB RAM = 557$ / year
- Conclusion: Lambda 33$ cost savings. And that is not talking about decreased Ops costs!

### Advantages

- Reduced Labor Cost
- Reduced Infrastructure cost
- Increased scaling flexibility, where Amazon does everything all the scaling for you, no need to think about anything. 
- Shorter lead time
- UTs is brilliant

Serverless can accelerate a lean business

- Code actual app logic
- Configure API Gateway
- Deploy your code

Serverless Vs Containers: When thinking containers, we still have to think about resource allocation, scaling etc. But containers are getting better so this might go away soon.

But at the end of the day, it's really Servless AND CaaS, AND PaaS. It's not by itself.

#### Disadvantages

- Tooling and configuration: API Gateway has no source code, it's more manual, and no version controls! Also dealing environment variables is tough. For versioning, it's tough! tough to revert back to older versions
- Integration test locally is very hard to do. You have to deploy them to test, which is hard if you're working on a plane 
- Limit to number of concurrent lambdas at any one time (500). Example, if you want to do load testing with 500 machines, you just DDoS your self!
- Can't store in-memory state! So should think about that
- Can't run lambda for more than 5 min

#### The future

- Better and more vendors
- Better Processes and Tooling like Serverless Framework. 
- So much to learn architecture wise. The structure of building app as independent functions is different, and you can learn a lot.

#### Contact information

- [http://bit.ly/mr-serverless](http://bit.ly/mr-serverless)
- [http://www.mikebroberts.com](http://www.mikebroberts.com)
- [http://www.acanthis.io](http://www.acanthis.io)