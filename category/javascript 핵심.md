---
title: JavaScript ํต์ฌ
author: Tao He
date: 2023-01-13 00:00 +09:00
category: JavaScript ํต์ฌ
layout: post
---

# ๐ย ์๋ฐ์คํฌ๋ฆฝํธ ํต์ฌ๋ด์ฉ

### ์๋ฐ์คํฌ๋ฆฝํธ ํต์ฌ๋ด์ฉ ์ ๋ฆฌ

์๋ฐ์คํฌ๋ฆฝํธ์์ ํต์ฌ์์ฃผ๋ก ๋ด๊ธด ๋ด์ฉ๋ค์ ์ ๋ฆฌํ๊ณ  ์๋ ํฌ์คํธ ์๋๋ค.  
๊ฐ์ฅ ์ค์ํ ๋งํผ ๋ง์ด ์ฝ๊ณ  ์์์ ์ผ๋ก ์ฐ์ต(์ฝ๋ฉ)์ ํด์ผํฉ๋๋ค.

<span class="bg_strong">๐ก ๋ฉด์  ์ง๋ฌธ๊ณผ ์ฐ๊ด์ด ์๋ ๋ถ๋ถ์ด๋ ๋งค์ฐ ์ค์ํฉ๋๋ค.</span>

{% for category in site.categories %}
{% if category[0] == 'JavaScript ํต์ฌ' %}

  <ul>
    {% for post in category[1] reversed %}
      <li><a href="{{ post.url }}">{{ post.title }}</a></li>
    {% endfor %}
  </ul>
	{% endif %}
{% endfor %}
