---
title: Hyper Text Markup Language
author: Tao He
date: 2023-01-13 00:00 +09:00
category: CSS
layout: post
---

{% for category in site.categories %}
{% if category[0] == 'CSS' %}

  <ul>
    {% for post in category[1] %}
      <li><a href="{{ post.url }}">{{ post.title }}</a></li>
    {% endfor %}
  </ul>
	{% endif %}
{% endfor %}
