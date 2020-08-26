---
layout: single
author_profile: true
permalink: /compsci/notes/
title: Computer Science Notes
---

<p>Notes in category Computer Science are:</p>

<ul>
  {% for post in site.categories.compsci %}
    {% if post.url %}
        <li><a href="{{ post.url }}">{{ post.title }}</a></li>
    {% endif %}
  {% endfor %}
</ul>