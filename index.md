---
layout: page
title: Spinach Blog
tagline: jotting down my notes 
---
{% include JB/setup %}

### Just taking notes of the conferences I go to.

<ul class="posts">
  {% for post in site.posts %}
    <li><span>{{ post.date | date_to_string }}</span> &raquo; <a href="{{ BASE_PATH }}{{ post.url }}">{{ post.title }}</a></li>
  {% endfor %}
</ul>


