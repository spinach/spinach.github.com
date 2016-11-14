---
layout: post
title: "Docker in Production"
description: ""
category: 
tags: []
---
{% include JB/setup %}

Challenges with modern architectures:

- Multiple tech stacks
- Lots of moving parts
- Complex infrastructure
- Increased released frequency
- Teams unboarding


Containerization: Package everything into a container (depenencies, code etc), which makes it easy for anyone to "transports" this container. 

Deploying on VM is good for isolation, but it's expensive because of the hypervisor layer. On a 16GB RAM machine, we can barely run 3-4 VMs before machine becomes full.

Docker offers the best of both worlds: 

- Running in isolation
- Running in a virtualized system

Each container's processes are visible on the host. 

Containers will run through container engines, such as Docker. They are platform that will offer a lot of tools to build/run/deploy containers and let them talk to each other 

Docker is great at enabling finer-grained, microservice architecture

