---
layout: page
title: Bejegyzések
lang: hu
---
{% for post in site.posts %}
  <ul>
      {% if post.lang contains 'hu' %}
        <li><a href='{{ post.url }}'>{{ post.title | absolute_url }}</a>: {{ post.content | strip_html | truncatewords: 50 }}&nbsp;
          <i>Posted on: <time datetime="{{- post.date | date_to_xmlschema -}}">{{- post.date | date: "%Y-%m-%d" -}}</time></i>
        </li>
      {% endif %}
  </ul>
{% endfor %}
