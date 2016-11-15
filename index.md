---
layout: page
title: Spinach's Blog
tagline: where I jotdown everything 
---
{% include JB/setup %}

### Checkout my notes on the o'reilly software architecture conference in SF, 2016.

<ul class="posts">
  {% for post in site.posts %}
    <li><span>{{ post.date | date_to_string }}</span> &raquo; <a href="{{ BASE_PATH }}{{ post.url }}">{{ post.title }}</a></li>
  {% endfor %}
</ul>


