---
layout: page
title: English posts
lang: en
---
# English posts

{% for post in site.posts %}
  <ul>
      {% if post.lang contains 'en' %}
        <li><a href='{{ post.url }}'>{{ post.title }}</a>: {{ post.content | strip_html | truncatewords: 50 }}</li>
      {% endif %}
  </ul>
{% endfor %}