---
layout: page
title: English posts on R
lang: en
---

{% for post in site.categories.R %}
  <ul>
        {% if post.lang == 'en' %}
          <li>
            <a href='{{ post.url | absolute_url }}'>{{ post.title }}</a>: {{ post.content | strip_html | truncatewords: 50 }}&nbsp;
            <i>Posted on: <time datetime="{{- post.date | date_to_xmlschema -}}">{{- post.date | date: "%Y-%m-%d" -}}</time></i>
                {% if post.tags.size > 0 %}
                  <div class="blog-tags">
                    Tags:
                    {% if site.link-tags %}
                    {% for tag in post.tags %}
                    <a href="{{ '/tags' | relative_url }}#{{- tag -}}">{{- tag -}}</a>
                    {% endfor %}
                    {% else %}
                      {{ post.tags | join: ", " }}
                    {% endif %}
                  </div>
                {% endif %}
          </li>
        {% endif %}
  </ul>
{% endfor %}