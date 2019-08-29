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

zgfabian.github.io is the personal blog and portfolio website created by me. It is made with [Jekyll](https://jekyllrb.com/) a static site generator. [GitHub Pages](https://pages.github.com/) are powered by Jekyll, so one can easily deploy a site using [GitHub](https://github.com/) (or other hosting company) for free. The theme (BeautifulTheme) was a little bit customized. The Blablabla logo is besed on sticker created by my daughter. The image galleries use lightbox.js which was adapted to Jekyll's templating language (Liquid) by [Jekyll Codex](https://jekyllcodex.org/without-plugins/). 

{% if page.galleries %}{% include image-gallery-index.html %}{% endif %}
