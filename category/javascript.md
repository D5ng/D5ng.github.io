---
title: JavaScript
author: Tao He
date: 2023-01-13 00:00 +09:00
category: JavaScript
layout: post
---

# 📙 자바스크립트 공부

### 자바스크립트 Deep Dive Study 정리

책으로 한 챕터씩 보고있기때문에, 내용이 비어있는 부분도 있습니다.
Deep Dive스터디가 끝난 이후에 중요한 내용들을 다시 정리해서 다른 카테고리에 올릴예정입니다.

{% for category in site.categories %}
{% if category[0] == 'JavaScript' %}

  <ul>
    {% for post in category[1] reversed %}
      <li><a href="{{ post.url }}">{{ post.title }}</a></li>
    {% endfor %}
  </ul>
	{% endif %}
{% endfor %}
