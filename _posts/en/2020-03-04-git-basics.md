---
layout: post
title: Git basics
subtitle: from CLI
image: /img/20-03-04-git/git-post-img.png
categories: [Linux]
tags: [git, CLI]
# comments: true
lang: en
# common-js: "https://ajax.googleapis.com/ajax/libs/jquery/1.12.4/jquery.min.js"
# js: /js/bootstrap.js
# ext-css: "//oldhungarian.eu/stylesheets/oldhungarian.css"
---
git status - to check local repo

Example output:

![git status](/img/20-03-04-git/git-status.png)

### To see all the diff in tracked files but are in unstaged state:

    git diff

or

    git diff path/to/a/given/file


Stage files

    git add . # add all files from current local repo (e.g. from "master" branch)

### If you have already staged the changes with git add, you can see what patch you have staged with[^note1]

    git diff --staged


### Notes

[^note1]: How to see changes to a file before commit? [SO](https://stackoverflow.com/questions/13787109/how-to-see-changes-to-a-file-before-commit/13787903)

### Bonus

[Academic Writing in Markdown](https://youtu.be/hpAJMSS8pvs) with special reference to its advantages and features like creating footnotes, bibliographical references.