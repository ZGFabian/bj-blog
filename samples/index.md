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
  {% for post in site.pages %}
    <li>
      <a href="{{ site.url }}{{ page.url }}">{{ page.title }}</a>
    </li>
  {% endfor %}
</ul>

<div>
    site: {{ site | jsonify | escape }}
    page: {{ page | jsonify | escape }}
    layout: {{ layout | jsonify | escape }}
    content: {{ content | jsonify | escape }}
    paginator: {{ paginator | jsonify | escape }}
</div>