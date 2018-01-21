---
layout: default
title: Blog
permalink: /blog/
---

<ul>
  {% for post in site.posts %}
    <li>
      <a href="{{ post.url }}">{{ post.title }}</a> {{ post.date | date_to_string }}
      {{ post.excerpt }}
    </li>
  {% endfor %}
</ul>
