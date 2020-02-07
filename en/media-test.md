---
layout: page
title: media test page
subtitle: samples
tags: [video, image, image gallery, google fonts]
lang: en
---

[Beautiful Jekyll structure goes about here.] It uses the following js libraries.


- Hello, this is a [yt video link](https://youtu.be/s0uawtiiNY4), created with lightbox.js. (Credit: [Jekyll Codex](https://jekyllcodex.org/without-plugins/)) Lightbox is included in `base.html` in `_layouts folder`. It "is a solution that loads your image links, your Youtube links and your Vimeo links automatically in a minimalistic and responsive pseudo window/overlay. No adjustment to your links is required, just follow the installation instructions below." [Source.](https://jekyllcodex.org/without-plugin/lightbox/)

- Picture of a [SHEEPCOW](/img/fa_album/image1.jpg "sheep cow alias Busó") & [blablabla](/img/blabla_av_white_bg.png) - Art by FaFa / Also lightbox.js and credit goes to [Jekyll Codex](https://jekyllcodex.org/without-plugins/). Lightbox handles jpg, png and [gif](/img/20-01-09/forkit.gif) images.

![gif with animation](/img/20-01-09/forkit.gif)

- A self-generated (css-styled) thumbnail image linked to the original picture that is displayed via lightbox.js:
[![Click to view large image](/img/fa_album/image1.jpg#thumbnail "sheep cow alias Busó #thumbnail")](/img/fa_album/image1.jpg)
[![SHEEPCOW](/img/fa_album/image1.jpg#thumbnail2 "sheep cow alias Busó #thumbnail2")](/img/fa_album/image1.jpg)
[![blabla](/img/blabla_av_white_bg.png#thumbnail2 "blablabla ...")](/img/blabla_av_white_bg.png)


These images from [weserv.nl](https://images.weserv.nl/docs/#how-it-works)
```html
<img src="//images.weserv.nl/?url=images.weserv.nl/lichtenstein.jpg&w=300&h=300&fit=cover&a=focal-0-20">
```
<img src="//images.weserv.nl/?url=images.weserv.nl/lichtenstein.jpg&w=300&h=300&fit=cover&a=focal-0-20">

Animated WebP:
```
<details> 
  <summary>Q1: WebP image with animation?</summary>
   <img src="//images.weserv.nl/?url=images.weserv.nl/banana.webp&h=300&output=gif&n=-1"> 
</details>
```

<details> 
  <summary>Q1: WebP image with animation?</summary>
   <img src="//images.weserv.nl/?url=images.weserv.nl/banana.webp&h=300&output=gif&n=-1"> 
</details>

	<img align="right" width="200" height="183" src="https://cloud.githubusercontent.com/assets/532272/21507867/3376e9fe-cc4a-11e6-9350-7ec4f680da36.gif">

<img align="right" width="200" height="183" src="https://cloud.githubusercontent.com/assets/532272/21507867/3376e9fe-cc4a-11e6-9350-7ec4f680da36.gif">

- This is going to be an image gallery. You should download `image-gallery.html` to your `_includes` folder, and follow the [instructions](https://jekyllcodex.org/without-plugin/image-gallery/). Image captions are derived from `filename` in `alt=""` tags.  Credits: FaFa / [Jekyll codex](https://jekyllcodex.org/without-plugins/) Wow!

{% include image-gallery.html folder="/img/fa_album" %}

<details> 
  <summary>Q1: What is the best Language in the World?</summary>
   A1: JavaScript 
</details>