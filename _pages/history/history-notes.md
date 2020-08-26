---
layout: single
author_profile: true
permalink: /history/
title: History Notes
---

<ul>
  {% for post in site.categories.history %}
    {% if post.url %}
        <li><a href="{{ post.url }}">{{ post.title }} - {{ post.date }}</a></li>
    {% endif %}
  {% endfor %}
</ul>