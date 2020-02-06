---
layout: post
title: youtube-dl 
subtitle: A CLI tool to download videos and subtitles from the web
categories: [tools]
tags: [CLI, ascii, subtitle, youtube-dl]
lang: en
---
[youtube-dl](https://ytdl-org.github.io/youtube-dl/index.html) is a command-line program CLI tool to download videos and subtitles from youtube. It works not only on youtube.com, but on many more sites. [Supported sites](https://ytdl-org.github.io/youtube-dl/supportedsites.html)
To download the most recent version [visit project](https://github.com/ytdl-org/youtube-dl) page and follow the install instructions. 
<div class="alert alert-dark" role="alert">Caveat: see a recent issue/bug raised on <a href="https://www.reddit.com/r/youtubedl/comments/cjilhz/fyi_since_googleyoutube_just_broke_youtubedl/">r/youtubedl!</a></div>

# Example 1 - download English subtitles only
I borrowed from this [discussion](https://superuser.com/questions/927523/how-to-download-only-subtitles-of-videos-using-youtube-dl).

When you need to download only subtitles in a given or all languages you have the following options according to the [documentations](https://github.com/ytdl-org/youtube-dl/blob/master/README.md#options) (`man youtube-dl` or `youtube-dl -h`).
[![screenshot](/img/20-02-04/yt-man.jpg)](/img/20-02-04/yt-man.jpg)

The following command will download subtitles this [video](https://youtu.be/gDqAnOyAgt4) (America's Great Divide: Steve Bannon, 2nd Interview)
Note: You can check the available languages and formats with `youtube-dl --list-subs YOUR_URI`. `--sub-lang en` specifies **English** langugage, and `skip-download` is the **only** part, that is an opt for subtitles only. In this way video content will not be downloaded.

```sh
youtube-dl --write-sub --sub-lang en --skip-download https://youtu.be/gDqAnOyAgt4                 
```

The result will be a WebVTT (with .vtt extension) text file, that can be process or use for one's purpose. 


	WEBVTT
	Kind: captions
	Language: en

	00:00:00.000 --> 00:00:03.580
	 So we’re in the summer of 2017. 

	00:00:03.580 --> 00:00:06.416
	The president is waffling on DACA [Deferred Action for Childhood Arrivals]. 

	00:00:06.416 --> 00:00:08.048
	You recognize that. 

# Example 2 [Get only part of a video - TBC](#)


