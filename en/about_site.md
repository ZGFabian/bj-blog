---
layout: page
title: About the site
lang: en
galleries:
  - title: Link to Jekyll
    image: /img/site/jekyll_logo.jpg
    url: https://jekyllrb.com/
  - title: Link to image gallery
    image: /img/blabla_av_orange.png
    url: /img/blabla_av_orange.png
---

zgfabian.github.io is the personal blog and portfolio website created by me. It is made with Jekyll, and GitHub Pages are powered by Jekyll, so one can easily deploy a site using GitHub (or other hosting company) for free. The theme (BeautifulTheme) was a little bit customized. The Blablabla logo is besed on sticker created by my daughter. The image galleries use lightbox.js which was adapted to Jekyll's templating language (Liquid) by [Jekyll Codex](https://jekyllcodex.org/without-plugins/). 

{% if page.galleries %}{% include image-gallery-index.html %}{% endif %}
