<!-- ---
title: Node.js
author: Dongs
date: 2023-01-18 00:00 +09:00
category: Node
layout: post
---

# ๐ย Node.js ๊ณต๋ถ

๋ฐฑ์๋ ๊ฐ๋ฐ์๋ฅผ ํ ๊ฑด ์๋์ง๋ง, ์ด๋์ ๋ ์ดํด๋ฅผ ํด์ผ ์ข๋ค๊ณ  ์๊ฐํ๊ณ , ํ๋ก ํธ์๋๋ฅผ ํ๊ณ  ์๊ธฐ์
์ต์ํ JavaScript๋ก ์๋ฒ๋ฅผ ๋ฐฐ์์ ๊ฐ๋จํ ํ์ฌ์๊ฐ ์ฌ์ดํธ ์ ๋๋ ๋ง๋ค ์ ์๋ ์ค๋ ฅ์ ๋ชฉํ๋ก ํฉ๋๋ค.

{% for category in site.categories %}
{% if category[0] == 'Node' %}

  <ul>
    {% for post in category[1] reversed %}
      <li><a href="{{ post.url }}">{{ post.title }}</a></li>
    {% endfor %}
  </ul>
	{% endif %}
{% endfor %} -->
