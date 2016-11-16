---
layout: post
title: "Kubernetes"
description: ""
category: 
tags: []
---
{% include JB/setup %}

We must treat the datacenter itself as one massive warehouse-scale computer. We want our application to be global now. 

In the cloud, you need to care about resource utilities

The goal is to get fully automated deployment. 

Kubernetes makes intelligent way of resource utilization. It takes care of tracing, logging, policies, metrics, storage, security. Kubernetes is a central place that will do all of these things for you. Containers become implementation detail.

Demo on how to deploy a set of application using Kubernetes. Run clone of HackerNews. kubectl get svc. Things are deployed in kubernetes, all IP visibility is taken care of for you. We run MySql and Lobsters. run jobs to setup login and database. In order to scale, we can just increase replicas from 1 to 5. You don't worry about machines, let kubernetes handle that for you

