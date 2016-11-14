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

Containers will run through container engines, such as Docker. They are platform that will offer a lot of tools to build/run/deploy containers and link components together. Docker is great at enabling finer-grained, microservice architecture

Docker Images contains:
- a minimal OS distribution
- dependencies
- a single application or service

Docker Images: Immutable Layers that build on top of each other. 
Docker registries are where you can push and pull your docker images

### Takeaways

- Try to keep your Docker images small (e.g. base them on busybox, alpine, or debian base images)
- Don't use Docker containers like full blown VMs - Run a single process/service in each Docker container
- Use Docker Networks as an alternative to legacy links for communicating between containers
- Consider using OS service scripts* (e.g. Upstart, Systemd) to manage your containers (e.g. pass environment variables, keep them running, start on boot and/or in a specific order)