---
title: Node.js
author: Dongs
date: 2023-01-18 00:00 +09:00
category: Node
layout: post
---

# 📙 Node.js 공부

백엔드 개발자를 할건 아니지만, 어느정도 이해를 해야 좋다고 생각하고, 프론트엔드를 하고 있기에  
익숙한 JavaScript로 서버를 배워서 간단한 회사소개 사이트 정도는 만들 수 있는 실력을 목표로 합니다.

{% for category in site.categories %}
{% if category[0] == 'Node' %}

  <ul>
    {% for post in category[1] reversed %}
      <li><a href="{{ post.url }}">{{ post.title }}</a></li>
    {% endfor %}
  </ul>
	{% endif %}
{% endfor %}
