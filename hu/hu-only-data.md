---
layout: page
title: Bejegyzések
subtitle: adatokról
lang: hu
---
{% for post in site.posts %}
  <ul>
      {% if post.lang contains 'hu' and post.categories contains 'data' %}
        <li><a href='{{ post.url | absolute_url }}'>{{ post.title }}</a>: {{ post.excerpt | strip_html | truncatewords: 50 }}&nbsp;
          <i>Posted on: <time datetime="{{- post.date | date_to_xmlschema -}}">{{- post.date | date: "%Y-%m-%d" -}}</time></i>
        </li>
      {% endif %}
  </ul>
{% endfor %}
