---
layout: post
title: "Continuously Delivering Microservices"
description: ""
category: 
tags: []
---
{% include JB/setup %}

Miroservice Overview: Software architectural style where applications are composed of small, independent processes communicating with each other using language-agnostic APIs. Check online for characteristics.

Got started by the team giving us a workshop folder containing a box, and we used Vagrant to get it up and ssh into it. Just going through the steps in the slides to setup everything... The journey is the following: 

![Journey Today](https://s3.amazonaws.com/oreilly-conference/Journey+Today.png?X-Amz-Date=20161114T185935Z&X-Amz-Expires=300&X-Amz-Algorithm=AWS4-HMAC-SHA256&X-Amz-Signature=3799c5016484cc2bc456b5fb8a7291f7006ef88d7f7fcd50469f89c3f74cd549&X-Amz-Credential=ASIAJSU6I3JQPV6SKENQ/20161114/us-east-1/s3/aws4_request&X-Amz-SignedHeaders=Host&x-amz-security-token=FQoDYXdzEMT//////////wEaDDLa0GkZn6Ub0xMimSL%2BAYiI1UpqXGacFQLxYQ941uMEBVEAPsCrRj35eDU7BcVGZonJvCz5fzKopij7mkMZj6yktsS3B5KtzXPUcJiBIuPqXiWRkyT71CZr8YihJjZiYO0Ch3aoogmH0OwpO/yv0ha/iYVoZ89%2BS6ngBDFh5nOilMWQYunARvBsOVES%2Bg3ODuMBY/B5kaqKa/QiplZZQKxYdfLCaRoAUIPaolT3i1ULBxcsic77U2jDwLDBuQntBPJfUzUj8%2B2AK6MrMadJIbihgUmDkAlMmgT9eZsbHVUDQPOxi7yydigRwgd6%2BIe0x8aZpExrg9AsNcenDcmF3linNxfcT282%2BIafvpRTKKiSqMEF)

### Purpose

Purpose of using Microservice with CD (in this workshop Go-CD pipeline):
Can we actually deploy with confidence the monolith before being confident to deploy 100 microservices? That's what we're gunna go through.

Problems we usually face: It can be challenging to know when something is broken when you have 50 microservices. Is it version related? Is it because of a commit? Etc. That's why a good CI pipeline is important here to be able to quickly visualize all our microservice. With Go-CD, we have a **visual** representation of our CD system.

![Image of Go-CD Visual Representation](./go-pipeline-visual-diagram.png)


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

![Overview Module 2](./Overview Module 2.png)

Basically, in order to extract our review service in our shop-app, we change from getStarRatingsLocalMethod() to getStarRatingsFromReviewService(). 
Notice as well the difference in Ports (8090 Vs 8082)



