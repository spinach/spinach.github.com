---
layout: post
title: "Opening keynote: Going Serverless"
description: ""
category: 
tags: []
---
{% include JB/setup %}

Serverless is truly facinating, and will shake up the way we do things. 

- Back to 1996, Servers were inside the office of the company offering the web service. 
- In 2001, company moves their servers from their offices to datacenter companies: to reduce costs and have better expertise people
- In 2006, Amazon announced Elastic cloud computing EC2: Any company can rent machine on demand. Why was that good? With infrastructure as a service, the lead time goes from months to minutes. Also, it offers scalability. Amazon was able to do it due to economies of scale
- Now Serverless: Next evolution of cloud computing. 

BaaS (Backend-as-a-service) came up lately: Products like Firebase and Auth0. They build these functionalities so that we don't have to worry about them. We can use them and bundle them in our app.
FaaS (Function-as-a-servie) came now: that gave rise to "Serverless"

- in BaaS, we have a host instance, an application process, and then operation.
- in FaaS, we remove host instance and application process. We're kept with just operations. 

FaaS trigerring events
- Message Bus
- Network File System
- Time Event
- Http Request

FaaS = No management of Server Hardware or Server Processes. Teams don't have concerns over servers, or hosts etc. 

AWS Lambda is the first one that offered FaaS.

`Serverless = BaaS + FaaS`

Why Serverless:

- Reduced Labor Cost
- Reduced Infrastructure cost
- Increased Scaling Flexibility (they only use precisely what they need, and they scale automatically, no need for preventation. No planning.
- Shorter Lead Time. 
