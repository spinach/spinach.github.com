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

