---
title: HTML
author: Tao He
date: 2023-01-11 00:00 +09:00
category: HTML
layout: post
---

{% for category in site.categories %}
{% if category[0] == 'HTML' %}

  <ul>
    {% for post in category[1] reversed %}
      <li><a href="{{ post.url }}">{{ post.title }} ({{ post.date }})</a></li>
    {% endfor %}
  </ul>
	{% endif %}
{% endfor %}
