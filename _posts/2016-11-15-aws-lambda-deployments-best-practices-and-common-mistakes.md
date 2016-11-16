---
layout: post
title: "AWS Lambda deployments: Best practices and common mistakes"
description: ""
category: 
tags: [oreilly conference, sessions]
---
{% include JB/setup %}

## TL;DR
- AWS Lambda is the first in the FaaS world
- Plenty of Lambda Event Sources from http request to chron jobs to emails
- Good for tasks such as image processing, scheduling batch work and low volume website features

## Full Version

Serverless framework of Amazon.

Lambda Event Sources:

- API Gateway
- SNS messaging
- Schedule
- Storage writes on S3, dynamodb
- SES Email receipt
- CloudWatch
- Cognito
- CloudFormation

Check my Serverless post for the pros and cons. Applies to Lambda

Drawbacks specifically for Lambda:

- Documentation is not so good. For Java Lambdas, you are almost on your own. 
- Startup time is sometimes inconsistent. Python fastest, Java slowest.

#### Implementation tips

- Seperation of concerns: Keep Lambda and business logic seperately.
- Ensure you can always tie AWS request Id to your business transaction.

#### Common use cases

- Processing for uploaded data: Image processing. Lambdas are cheap ways to do it
- Low-volume web site features
- Scheduled Batch Work

#### Performance

Startup Time: Python > Node.js > Java.

Trhoughtput: Java > Node.js

Lambda can be used as a microservice deployment mechanism. However, remember that Lambdas don't have state, which is expected in microservices. 


#### Contact
Derekshmore: check slideshare and blog.