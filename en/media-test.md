---
layout: page
title: media test page
subtitle: samples
tags: [video, image, image gallery, google fonts]
lang: en
---

<div class="row">
    <div class="col-xl4">
    1 of 3
    </div>
    <div class="col-xl4">
    2 of 3
    </div>
    <div class="col-xl4">
    3 of 3
    </div>
</div>


- Hello, this is a [yt video link](https://youtu.be/s0uawtiiNY4), created with lightbox.js. (Credit: [Jekyll Codex](https://jekyllcodex.org/without-plugins/)) Lightbox is included in `base.html` in `_layouts folder`.
- Picture of a [SHEEPCOW](/img/fa_album/image1.jpg) & [blablabla](/img/blabla_av_white_bg.png) - Art by FaFa / Also lightbox.js and credit goes to [Jekyll Codex](https://jekyllcodex.org/without-plugins/).
- This is going to be an image gallery. You should download `image-gallery.html` to your `_includes` folder, and follow the [instructions](https://jekyllcodex.org/without-plugin/image-gallery/). Image captions are derived from `filename` in `alt=""` tags.  Credits: FaFa / [Jekyll codex](https://jekyllcodex.org/without-plugins/) Wow!

{% include image-gallery.html folder="/img/fa_album" %}