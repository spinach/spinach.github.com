---
layout: post
title: "How to increase software development agility"
description: ""
category: 
tags: [oreilly conference, sessions]
---
{% include JB/setup %}

## TL;DR

- Agility is moving quickly with mental acuity
- Talking about deployment history, and its evolution
- Security policies will help you in securing your system
- Event Driven Design the way to go

<br/>

## Full Version

Agility:

1- Moving quickly
2- Mental acuity


When breaking monolith into a lot of microservices: if they end up all talking to each other, you end up with Polylith, basically like a ball of mud :)

Other mindset: Cut monolith into 2 hemilith: Frontend and Backend! Then if this goes successfully, than split each in 2, get 4 tetartolith. Get 6 connections in between.

Software components: Only the giants survive. Big components of more than 500 lines of code will need documentation, and the cost is high. Else they die. 

Deployments:

- machine
- app + dependency (like npm)
- appstore
- incremental updates, 'patches'

Google Trends: `Software` is decreasing linearly. `App` is increasing linearly. Now obviously an app is software, and vice versa. 

We want to do democratization for deployments: let everyone deploy. If you made software deployment easy so that everybody can do it, then anyone will do it. 

- It used to be just copying file to machine. boom, deployed.
- After, you push to github, and then there is a hook in github that will push the changes to prod. But what if it fails? you get a mail that it fails. and you have to do it again...

Security policies: use to define who can access what. Like this, no one will be able to illegally put stuff in your database without permissions. 

You should store everything. and not in spreadsheet ofc. But let's say we want to migrate from spreadsheet to db.

`user -> spreadsheet -> AWS Gateway -> AWS Lambda -> PostgreSQL` 

And what if something goes wrong? there has to be a return path. Maybe some rows went in, and some didn't...

But we'll need to create the database from a public area. Which is not good practice. 

Which brings us to: Event Driven Designs: Add a cloudwatch, that will send from postgres to spreadsheet(?). Event Driven Designs:

- Incremental algorithms
- non-blocking I/O
- callbacks or return paths

Use SNS and Lambda in your stack.