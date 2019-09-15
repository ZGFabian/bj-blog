---
layout: page
title: About the site
lang: en
galleries:
  - title: Jekyllrb.com
    image: /img/site/jekyll_logo.jpg
    url: https://jekyllrb.com/
  - title: Blabalabla
    image: /img/blabla_av_orange.png
    url: /img/blabla_av_orange.png
  - title: GitHub
    image: /img/site/github-icon.png
    url: https://github.com/
---

zgfabian.github.io is my personal blog and portfolio website. I made it with [Jekyll](https://jekyllrb.com/), a static site generator. [GitHub Pages](https://pages.github.com/) is also using Jekyll, so one can easily deploy a site using [GitHub](https://github.com/) (or other hosting company) for free. I adopted [Dean Attali](https://deanattali.com/)’s Beautiful Jekyll theme. The Blablabla logo is based on a sticker created by my daughter. Image galleries use lightbox.js, and I downloaded it from [Jekyll Codex](https://jekyllcodex.org/without-plugins/). 

{% if page.galleries %}{% include image-gallery-index.html %}{% endif %}
