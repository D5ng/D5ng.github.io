---
title: JavaScript
author: Tao He
date: 2023-01-02 00:00 +09:00
category: JavaScript
layout: post
---

# 📙 자바스크립트 공부

### 자바스크립트 Deep Dive Study 정리

너무나도 좋고, 엄청나게 방대한 양이다… 사실 여기있는 책을 모두 외워버리면 좋겠지만,  
그냥 코드만 짜는게 아닌, 원리에 대해 알아가면서 코드를 작성하는게 더욱 더 의미가 있다.  
스터디를 진행하면서 각 챕터들마다 정리를 해보려고 합니다!

출처 - [자바스크립트 Deep Dive](https://wikibook.co.kr/mjs/)  
링크 - [웹 튜토리얼 이웅모](https://poiemaweb.com/)  
저자 - 이웅모  
출판사 - 위키북스

{% for category in site.categories %}
{% if category[0] == 'JavaScript' %}

  <ul>
    {% for post in category[1] reversed %}
      <li><a href="{{ post.url }}">{{ post.title }}</a></li>
    {% endfor %}
  </ul>
	{% endif %}
{% endfor %}
