---
title: JavaScript
author: Tao He
date: 2023-01-02 00:00 +09:00
category: JavaScript
layout: post
---

# πΒ μλ°μ€ν¬λ¦½νΈ κ³΅λΆ

### μλ°μ€ν¬λ¦½νΈ Deep Dive Study μ λ¦¬

λλ¬΄λλ μ’κ³ , μμ²­λκ² λ°©λν μμ΄λ€β¦ μ¬μ€ μ¬κΈ°μλ μ±μ λͺ¨λ μΈμλ²λ¦¬λ©΄ μ’κ² μ§λ§,  
κ·Έλ₯ μ½λλ§ μ§λκ² μλ, μλ¦¬μ λν΄ μμκ°λ©΄μ μ½λλ₯Ό μμ±νλκ² λμ± λ μλ―Έκ° μλ€.  
μ€ν°λλ₯Ό μ§ννλ©΄μ κ° μ±ν°λ€λ§λ€ μ λ¦¬λ₯Ό ν΄λ³΄λ €κ³  ν©λλ€!

μΆμ² - [μλ°μ€ν¬λ¦½νΈ Deep Dive](https://wikibook.co.kr/mjs/)  
λ§ν¬ - [μΉ νν λ¦¬μΌ μ΄μλͺ¨](https://poiemaweb.com/)  
μ μ - μ΄μλͺ¨  
μΆνμ¬ - μν€λΆμ€

{% for category in site.categories %}
{% if category[0] == 'JavaScript' %}

  <ul>
    {% for post in category[1] reversed %}
      <li><a href="{{ post.url }}">{{ post.title }}</a></li>
    {% endfor %}
  </ul>
	{% endif %}
{% endfor %}
