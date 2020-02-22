---
layout: page
title: Posts
subtitle: about data
lang: en
---
{% for post in site.posts %}
  <ul>
      {% if post.lang contains 'en' and post.categories contains 'data' %}
        <li><a href='{{ post.url }}'>{{ post.title }}</a>: {{ post.content | strip_html | truncatewords: 50 }}&nbsp;
          <i>Posted on: <time datetime="{{- post.date | date_to_xmlschema -}}">{{- post.date | date: "%Y-%m-%d" -}}</time></i>
        </li>
      {% endif %}
  </ul>
{% endfor %}