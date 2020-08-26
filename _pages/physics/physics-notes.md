---
layout: single
author_profile: true
permalink: /physics/
title: Physics HL Notes / Work
---


All the Physics notes below are categorised by date: 

<ul>
  {% for post in site.categories.physics %}
    {% if post.url %}
        <li><a href="{{ post.url }}">{{ post.title }}</a></li>
    {% endif %}
  {% endfor %}
</ul>