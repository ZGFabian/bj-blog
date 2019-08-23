---
layout: page
title: English posts on R
lang: en
---
# English posts

{% for post in site.posts %}
  <ul>
        {% if post.lang contains 'en' %}
            <li>
              <a href='{{ post.url }}'>{{ post.title }}</a>: {{ post.content | strip_html | truncatewords: 50 }}&nbsp;
              <i>Posted on: <time datetime="{{- post.date | date_to_xmlschema -}}">{{- post.date | date: "%Y-%m-%d" -}}</time></i>
            </li>
        {% endif %}
  </ul>
{% endfor %}


{%- capture site_cat -%}
    {%- for cat in site.categories -%}
        {{- cat | first -}}{%- unless forloop.last -%},{%- endunless -%}
    {%- endfor -%}
{%- endcapture -%}
{%- assign cat_list = site_cat | split:',' | sort -%}

{%- for cat in cat_list -%}
    <a href="#{{- cat -}}" class="btn btn-primary tag-btn"><i class="fa fa-tag" aria-hidden="true"></i>&nbsp;{{- cat -}}&nbsp;({{site.categories[cat].size}})</a>
{%- endfor -%}

<div id="full-tags-list">
{%- for cat in cat_list -%}
    <h2 id="{{- cat -}}" class="linked-section">
        <i class="fa fa-tag" aria-hidden="true"></i>
        &nbsp;{{- cat -}}&nbsp;({{site.categories[cat].size}})
    </h2>
    <div class="post-list">
        {%- for post in site.categories[cat] -%}
            <div class="tag-entry">
                <a href="{{ post.url | relative_url }}">{{- post.title -}}</a>:&nbsp;{{- post.subtitle -}}
                <div class="entry-date">
                    <time datetime="{{- post.date | date_to_xmlschema -}}">{{- post.date | date: "%Y-%m-%d" -}}</time>
                </div>
            </div>
        {%- endfor -%}
    </div>
{%- endfor -%}
</div>




jsdhfkjhdsasda
<div>
{% for post in site.categories.R %}
  <ul>
        {% if post.lang == 'en' %}
          <li>
            <a href='{{ post.url }}'>{{ post.title }}</a>: {{ post.content | strip_html | truncatewords: 50 }}&nbsp;
            <i>Posted on: <time datetime="{{- post.date | date_to_xmlschema -}}">{{- post.date | date: "%Y-%m-%d" -}}</time></i>
          </li>
        {% endif %}
  <ul>
{% endfor %}
</div>