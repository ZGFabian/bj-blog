---
layout: page
title: Markdown példák
subtitle: Teszt oldalak
permalink: /samples/
tags: [markdown]
lang: hu
---

Tartalom

samples/2015-01-04-first-post.md  
samples/2015-01-15-pirates.md  
samples/2015-01-19-soccer.md  

<ul>
  {% for page in site.page %}
    <li>
      <a href="{{ page.url }}">{{ page.title }}</a>
    </li>
  {% endfor %}
</ul>