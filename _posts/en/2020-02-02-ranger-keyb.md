---
layout: post
title: "Cheatsheet for ranger FM"
subtitle: Some keybindings
categories: [Linux]
tags: [Ranger FM, CLI, todo]
image: /img/20-02-02/ranger-logo.png
lang: en
---

[ranger](https://github.com/ranger/ranger), is a console based file manager (fm) on Unix/Linux. It has a special three-column view features (that is called [Miller columns](/2019-07-17-miller-columns/)), but it is also able to behave as a dual-pane fm, like Midnight Commander (MC), total commander, etc. (Actually many keys work like MC does. It is really a great tool with many features that can be customized according to one's need. However, users who are not familiar with terminal commands and vim flavour editors, may find it difficult to learn Ranger's functioning. This is because a lot of keybindings and terms like "[yank](https://ell.stackexchange.com/questions/14632/why-does-yank-in-vim-mean-copy)" or "[pager](https://unix.stackexchange.com/questions/144016/what-is-a-pager)" have long history in computing.

Notable features of ranger are: 
 - image preview [demo](https://youtu.be/DJhDMxMgzC0) / [instrucion]()
 - integration with fzf fuzzy searching tool. [instructions](https://github.com/gotbletu/shownotes/blob/master/ranger_file_locate_fzf.md) and [demo](https://youtu.be/C64LKCZFzME).

When you hit <kbd>?+k</kbd> in ranger, you will get your predefined keybindings set in `~/.config/ranger/rc.conf` file. The only thing I changed right after installing ranger, was the <kbd>Delete</kbd> and <kbd>F8</kbd> keys. It is now binded to `trash-put` command rather than `console delete` (that is rm command in a shell). In this way files that are deleted/removed with del key, can be restored from `~/.local/share/Trash` folder either manually or with `trash-restore` command. I got this idea from this [video](https://www.youtube.com/channel/UCkf4VIqu3Acnfzuk3kRIFwA) by Gotbletu, who is one of the greatest evangelist for ranger and CLI.

| actions           |                             			keys |
| :---              |                             			--: |
| new directory 	| <kbd>F7</kbd> or :mkdir 					|
| new file 			| <kbd>insert</kbd> or :touch newfile.txt 	|
| change directory 	| <kbd>:</kbd>`cd /PATH/YOURIR/`			|
| go to ~ 			| <kbd>g+h</kbd>  							|

Note: `c` denotes <kbd>Ctrl</kbd>, so `<c - c>` reads: <kbd>Ctrl+c</kbd>.  



Related applications: 
 - [lf - file manager](https://github.com/gokcehan/lf)
 - [nnn](https://github.com/jarun/nnn#features) file manager, available from repos

