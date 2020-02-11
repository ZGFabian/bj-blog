---
layout: post
title: Formatting demo
subtitle: Styling pages using markdown, html and liquid formatting tags
# gh-repo: daattali/beautiful-jekyll
# gh-badge: [star, fork, follow]
tags: [markdown, html, css, liquid, todo]
comments: true
lang: en
---

# <H1> Using markdown, <b>**html** and liquid formatting tags

## Here is a secondary heading

Here's a useless & ugly .md table:

	| Number | Next number | Previous number |
	| :------ |:--- | :--- |
	| Five | Six | Four |
	| Ten | Eleven | Nine |
	| Seven | Eight | Six |
	| Two | Three | One |

Which is rendered to .html like this:

| Number | Next number | Previous number |
| :------ |:--- | :--- |
| Five | Six | Four |
| Ten | Eleven | Nine |
| Seven | Eight | Six |
| Two | Three | One |


<div class="alert alert-success">
  <i class="fa-lightbulb"></i> <strong>Tip:</strong> Creating tables in markdown can be a pain without advanced editor tools like sublime-text or the infamous vim. In such situations one can try the <a href="https://www.tablesgenerator.com/markdown_tables">Markdown Tables Generator</a>. 
</div>


A markdown picture

![BlaBlaBla](/img/site/blabla_av_orange.png#thumbnail2)

Images can also be centered like this `![BlaBlaBla](/PATH/){: .center-block :}`

![BlaBlaBla](/img/site/blabla_av_white_bg.png#thumbnail){: .center-block :}
<img align="right" src="/img/site/blabla_av_orange.png#thumbnail2">

Here's a code chunk:

~~~
var foo = function(x) {
  return(x + 5);
}
foo(3)
~~~

And here is the same code with syntax highlighting:

```javascript
var foo = function(x) {
  return(x + 5);
}
foo(3)
```

And here is the same code yet again but with line numbers:

{% highlight javascript linenos %}
var foo = function(x) {
  return(x + 5);
}
foo(3)
{% endhighlight %}

## Boxes
You can add notification, warning and error boxes like this:

### Notification

{: .box-note}
**Note:** This is a notification box. `{: .box-note}`

### Warning

{: .box-warning}
**Warning:** This is a warning box. `{: .box-warning}`

### Error

{: .box-error}
**Error:** This is an error box.

## Related:

[todo](https://github.com/adam-p/markdown-here/wiki/Markdown-Cheatsheet)