---
layout: post
title: "Cheatsheet for Ranger FM"
subtitle: Keybindings of my current vanilla config
categories: [Linux]
tags: [Ranger FM]
image: /img/20-02-02/ranger-logo.png
lang: en
---

[Ranger](https://github.com/ranger/ranger), is a console based file manager (fm) on Unix|Linux. It has a special three-column view features (that is called [Miller columns](#)), but it is also able to behave as a dual-pane fm, like Midnight commander (MC), total commander, etc. (Actually many keys work like MC does. It is really a great tool with many features that can be customized according to one's need. However, users who are not familiar with terminal commands and vim flavour editors, may find it difficult to learn Ranger's functioning. This is because a lot of keybindings and terms like "[yank](https://ell.stackexchange.com/questions/14632/why-does-yank-in-vim-mean-copy)" or "[pager](https://unix.stackexchange.com/questions/144016/what-is-a-pager)" have long history in computing, especially in Unix/Linux domains. 

A notable feature of Ranger are: 
 - image preview [demo](https://youtu.be/DJhDMxMgzC0) / [instrucion]()
 - integration with fzf fuzzy searching tool. [instructions](https://github.com/gotbletu/shownotes/blob/master/ranger_file_locate_fzf.md) and [demo](https://youtu.be/C64LKCZFzME).

When you hit `?+k` in ranger, you will get your predefined keybindings set in `~/.config/ranger/rc.conf` file. Here comes my recent config. The only thing I changed right after installing Ranger, was the `delete` and `F8` keys. It is now binded to `trash-put` command rather than `console delete` (that is rm command in a shell). In this way files that are deleted/removed with del key, can be restored from `~/.local/share/Trash` folder either manually or with `trash-restore` command. I got this idea from this [video by Gotbletu](https://www.youtube.com/channel/UCkf4VIqu3Acnfzuk3kRIFwA), who is one of the greatest evangelist for Ranger and CLI.

 **Emphases** and notes (`#!`) were added by me. Note: `c` denotes `<Ctrl>` (Control key), so `<c - c>` reads: <Ctrl - c>.  

<div>
	<pre>
	Keybindings in 'browser'
	           Q quitall
	           <b>q quit</b>
	          ZZ quit
	          ZQ quit
	           R reload_cwd
	           F set freeze_files!
	       <c-r> reset
	       <c-l> redraw_window
	       <c-c> abort
	    <escape> change_mode normal
	           <b>~ set viewmode!</b>
	           i display_file
	           <b>? help</b>
	           W display_log
	           w taskview_open
	           S shell $SHELL
	           : console
	           ; console
	           ! console shell%space
	           @ console -p6 shell  %%s
	           # console shell -p%space
	           s console shell%space
	           <b>r chain draw_possible_programs; console open_with%%space #!app menu</b> 
	           f console find%space
	          cd console cd%space
	          <b>cw console rename%space</b> #!same as :rename 
	          ct search_next order=tag
	          cs search_next order=size
	          ci search_next order=mimetype
	          cc search_next order=ctime
	          cm search_next order=mtime
	          ca search_next order=atime
	       <c-p> chain console; eval fm.ui.console.history_move(-1)
	          <b>Mf linemode filename
	          Mi linemode fileinfo
	          Mm linemode mtime
	          Mp linemode permissions
	          Ms linemode sizemtime
	          Mt linemode metatitle</b>
	           t tag_toggle
	          ut tag_remove
	          uv mark_files all=True val=False
	          uV toggle_visual_mode reverse=True
	          ud uncut
	          uy uncut
	          uq tab_restore
	     um<any> unset_bookmark %any
	      um<bg> draw_bookmarks
	      "<any> tag_toggle tag=%any
	     <space> mark_files toggle=True
	           v mark_files all=True toggle=True
	           V toggle_visual_mode
	        <b><f1> help
	        <f2> rename_append
	        <f3> display_file
	        <f4> edit
	        <f5> copy
	        <f6> cut
	        <f7> console mkdir%space
	        <f8> shell trash-put %s
	       <f10> exit
	        <up> move up=1
	      <down> move down=1
	      <left> move left=1
	     <right> move right=1
	      <home> move to=0
	       <end> move to=-1
	  <pagedown> move down=1   pages=True
	    <pageup> move up=1     pages=True</b> #!mc-like bindings
	       <c-j> move right=1
	    <insert> console touch%space
	           k move up=1
	           j move down=1
	           h move left=1
	           l move right=1
	          gg move to=0
	          gh cd ~
	          ge cd /etc
	          gu cd /usr
	          gd cd /dev
	          gl cd -r .
	          gL cd -r %f
	          go cd /opt
	          gv cd /var
	          gm cd /media
	          gi eval fm.cd('/run/media/' + os.getenv('USER'))
	          gM cd /mnt
	          gs cd /srv
	          gp cd /tmp
	          gr cd /
	          gR eval fm.cd(ranger.RANGERDIR)
	          g/ cd /
	          g? cd /usr/share/doc/ranger
	          gt tab_move 1
	          gT tab_move -1
	          gn tab_new
	          gc tab_close
	           G move to=-1
	       <c-f> move down=1   pages=True
	       <c-b> move up=1     pages=True
	           J move down=0.5  pages=True
	           K move up=0.5    pages=True
	       <c-d> move down=0.5  pages=True
	       <c-u> move up=0.5    pages=True
	           H history_go -1
	           L history_go 1
	           ] move_parent 1
	           [ move_parent -1
	           } traverse
	           { traverse_backwards
	           ) jump_non
	           E edit
	          du shell -p du --max-depth=1 -h --apparent-size
	          dU shell -p du --max-depth=1 -h --apparent-size | sort -rh
	          dD console delete
	          dd cut
	          da cut mode=add
	          dr cut mode=remove
	          dt cut mode=toggle
	         dgg eval fm.cut(dirarg=dict(to=0), narg=quantifier)
	          dG eval fm.cut(dirarg=dict(to=-1), narg=quantifier)
	          dj eval fm.cut(dirarg=dict(down=1), narg=quantifier)
	          dk eval fm.cut(dirarg=dict(up=1), narg=quantifier)
	          dc get_cumulative_size
	          yp yank path
	          yd yank dir
	          yn yank name
	          y. yank name_without_extension
	          yy copy
	          ya copy mode=add
	          yr copy mode=remove
	          yt copy mode=toggle
	         ygg eval fm.copy(dirarg=dict(to=0), narg=quantifier)
	          yG eval fm.copy(dirarg=dict(to=-1), narg=quantifier)
	          yj eval fm.copy(dirarg=dict(down=1), narg=quantifier)
	          yk eval fm.copy(dirarg=dict(up=1), narg=quantifier)
	           = chmod
	           a rename_append
	           A eval fm.open_console('rename ' + fm.thisfile.relative_path.replace("%", "%%"))
	           I eval fm.open_console('rename ' + fm.thisfile.relative_path.replace("%", "%%"), position=7)
	          pp paste
	          po paste overwrite=True
	          pP paste append=True
	          pO paste overwrite=True append=True
	          pl paste_symlink relative=False
	          pL paste_symlink relative=True
	         phl paste_hardlink
	         pht paste_hardlinked_subtree
	           / console search%space
	           n search_next
	           N search_next forward=False
	       <c-n> tab_new
	       <c-w> tab_close
	       <c-i> tab_move 1
	     <s-tab> tab_move -1
	<alt><right> tab_move 1
	 <alt><left> tab_move -1
	      <alt>1 tab_open 1
	      <alt>2 tab_open 2
	      <alt>3 tab_open 3
	      <alt>4 tab_open 4
	      <alt>5 tab_open 5
	      <alt>6 tab_open 6
	      <alt>7 tab_open 7
	      <alt>8 tab_open 8
	      <alt>9 tab_open 9
	      <alt>r tab_shift 1
	      <alt>l tab_shift -1
	          or set sort_reverse!
	          oz set sort=random
	          os chain set sort=size;      set sort_reverse=False
	          ob chain set sort=basename;  set sort_reverse=False
	          on chain set sort=natural;   set sort_reverse=False
	          om chain set sort=mtime;     set sort_reverse=False
	          oc chain set sort=ctime;     set sort_reverse=False
	          oa chain set sort=atime;     set sort_reverse=False
	          ot chain set sort=type;      set sort_reverse=False
	          oe chain set sort=extension; set sort_reverse=False
	          oS chain set sort=size;      set sort_reverse=True
	          oB chain set sort=basename;  set sort_reverse=True
	          oN chain set sort=natural;   set sort_reverse=True
	          oM chain set sort=mtime;     set sort_reverse=True
	          oC chain set sort=ctime;     set sort_reverse=True
	          oA chain set sort=atime;     set sort_reverse=True
	          oT chain set sort=type;      set sort_reverse=True
	          oE chain set sort=extension; set sort_reverse=True
	          zc set collapse_preview!
	          zd set sort_directories_first!
	          zh set show_hidden!
	          zI set flushinput!
	          zi set preview_images!
	          zm set mouse_enabled!
	          zp set preview_files!
	          zP set preview_directories!
	          zs set sort_case_insensitive!
	          zu set autoupdate_cumulative_size!
	          zv set use_preview_script!
	          zf console filter%space
	          zz console filter%space
	       <c-h> set show_hidden!
	 <backspace> set show_hidden!
	<backspace2> set show_hidden!
	          .n console filter_stack add name%space
	          .m console filter_stack add mime%space
	          .d filter_stack add type d
	          .f filter_stack add type f
	          .l filter_stack add type l
	          .| filter_stack add or
	          .& filter_stack add and
	          .! filter_stack add not
	          .r console filter_stack rotate
	          .c filter_stack clear
	          .* filter_stack decompose
	          .p filter_stack pop
	          .. filter_stack show
	      `<any> enter_bookmark %any
	       `<bg> draw_bookmarks
	      '<any> enter_bookmark %any
	       '<bg> draw_bookmarks
	      m<any> set_bookmark %any
	       m<bg> draw_bookmarks
	         +ur shell -f chmod u+r %s
	         +uw shell -f chmod u+w %s
	         +ux shell -f chmod u+x %s
	         +uX shell -f chmod u+X %s
	         +us shell -f chmod u+s %s
	         +ut shell -f chmod u+t %s
	         +gr shell -f chmod g+r %s
	         +gw shell -f chmod g+w %s
	         +gx shell -f chmod g+x %s
	         +gX shell -f chmod g+X %s
	         +gs shell -f chmod g+s %s
	         +gt shell -f chmod g+t %s
	         +or shell -f chmod o+r %s
	         +ow shell -f chmod o+w %s
	         +ox shell -f chmod o+x %s
	         +oX shell -f chmod o+X %s
	         +os shell -f chmod o+s %s
	         +ot shell -f chmod o+t %s
	         +ar shell -f chmod a+r %s
	         +aw shell -f chmod a+w %s
	         +ax shell -f chmod a+x %s
	         +aX shell -f chmod a+X %s
	         +as shell -f chmod a+s %s
	         +at shell -f chmod a+t %s
	          +r shell -f chmod u+r %s
	          +w shell -f chmod u+w %s
	          +x shell -f chmod u+x %s
	          +X shell -f chmod u+X %s
	          +s shell -f chmod u+s %s
	          +t shell -f chmod u+t %s
	         -ur shell -f chmod u-r %s
	         -uw shell -f chmod u-w %s
	         -ux shell -f chmod u-x %s
	         -uX shell -f chmod u-X %s
	         -us shell -f chmod u-s %s
	         -ut shell -f chmod u-t %s
	         -gr shell -f chmod g-r %s
	         -gw shell -f chmod g-w %s
	         -gx shell -f chmod g-x %s
	         -gX shell -f chmod g-X %s
	         -gs shell -f chmod g-s %s
	         -gt shell -f chmod g-t %s
	         -or shell -f chmod o-r %s
	         -ow shell -f chmod o-w %s
	         -ox shell -f chmod o-x %s
	         -oX shell -f chmod o-X %s
	         -os shell -f chmod o-s %s
	         -ot shell -f chmod o-t %s
	         -ar shell -f chmod a-r %s
	         -aw shell -f chmod a-w %s
	         -ax shell -f chmod a-x %s
	         -aX shell -f chmod a-X %s
	         -as shell -f chmod a-s %s
	         -at shell -f chmod a-t %s
	          -r shell -f chmod u-r %s
	          -w shell -f chmod u-w %s
	          -x shell -f chmod u-x %s
	          -X shell -f chmod u-X %s
	          -s shell -f chmod u-s %s
	          -t shell -f chmod u-t %s
	    <delete> shell trash-put %s
	Keybindings in `console'
	       <c-i> eval fm.ui.console.tab()
	     <s-tab> eval fm.ui.console.tab(-1)
	    <escape> eval fm.ui.console.close()
	       <c-j> eval fm.ui.console.execute()
	       <c-l> redraw_window
	       <c-c> eval fm.ui.console.close()
	        <up> eval fm.ui.console.history_move(-1)
	      <down> eval fm.ui.console.history_move(1)
	      <left> eval fm.ui.console.move(left=1)
	     <right> eval fm.ui.console.move(right=1)
	      <home> eval fm.ui.console.move(right=0, absolute=True)
	       <end> eval fm.ui.console.move(right=-1, absolute=True)
	      <alt>b eval fm.ui.console.move_word(left=1)
	      <alt>f eval fm.ui.console.move_word(right=1)
	 <alt><left> eval fm.ui.console.move_word(left=1)
	<alt><right> eval fm.ui.console.move_word(right=1)
	      <alt>d eval fm.ui.console.delete_word(backward=False)
	 <backspace> eval fm.ui.console.delete(-1)
	    <delete> eval fm.ui.console.delete(0)
	       <c-w> eval fm.ui.console.delete_word()
	       <c-k> eval fm.ui.console.delete_rest(1)
	       <c-u> eval fm.ui.console.delete_rest(-1)
	       <c-y> eval fm.ui.console.paste()
	       <c-g> eval fm.ui.console.close()
	       <c-p> eval fm.ui.console.history_move(-1)
	       <c-n> eval fm.ui.console.history_move(1)
	       <c-b> eval fm.ui.console.move(left=1)
	       <c-f> eval fm.ui.console.move(right=1)
	       <c-a> eval fm.ui.console.move(right=0, absolute=True)
	       <c-e> eval fm.ui.console.move(right=-1, absolute=True)
	       <c-d> eval fm.ui.console.delete(0)
	       <c-h> eval fm.ui.console.delete(-1)
	<backspace2> eval fm.ui.console.delete(-1)
	<allow_quantifiers> false
	Keybindings in `pager'
	      <down> pager_move  down=1
	        <up> pager_move  up=1
	      <left> pager_move  left=4
	     <right> pager_move  right=4
	      <home> pager_move  to=0
	       <end> pager_move  to=-1
	  <pagedown> pager_move  down=1.0  pages=True
	    <pageup> pager_move  up=1.0    pages=True
	       <c-d> pager_move  down=0.5  pages=True
	       <c-u> pager_move  up=0.5    pages=True
	           k pager_move  up=1
	       <c-p> pager_move  up=1
	           j pager_move  down=1
	       <c-n> pager_move  down=1
	       <c-j> pager_move  down=1
	           h pager_move  left=4
	           l pager_move  right=4
	           g pager_move  to=0
	           G pager_move  to=-1
	           d pager_move  down=0.5  pages=True
	           u pager_move  up=0.5    pages=True
	           n pager_move  down=1.0  pages=True
	           f pager_move  down=1.0  pages=True
	       <c-f> pager_move  down=1.0  pages=True
	     <space> pager_move  down=1.0  pages=True
	           p pager_move  up=1.0    pages=True
	           b pager_move  up=1.0    pages=True
	       <c-b> pager_move  up=1.0    pages=True
	       <c-l> redraw_window
	    <escape> pager_close
	           q pager_close
	           Q pager_close
	           i pager_close
	        <f3> pager_close
	           E edit_file
	Keybindings in `taskview'
	        <up> taskview_move up=1
	      <down> taskview_move down=1
	      <home> taskview_move to=0
	       <end> taskview_move to=-1
	  <pagedown> eval -q fm.ui.taskview.task_move(-1)
	    <pageup> eval -q fm.ui.taskview.task_move(0)
	       <c-d> taskview_move down=0.5  pages=True
	       <c-u> taskview_move up=0.5    pages=True
	           k taskview_move up=1
	       <c-p> taskview_move up=1
	           j taskview_move down=1
	       <c-n> taskview_move down=1
	       <c-j> taskview_move down=1
	           g taskview_move to=0
	           G taskview_move to=-1
	           u taskview_move up=0.5    pages=True
	           n taskview_move down=1.0  pages=True
	           f taskview_move down=1.0  pages=True
	       <c-f> taskview_move down=1.0  pages=True
	     <space> taskview_move down=1.0  pages=True
	           p taskview_move up=1.0    pages=True
	           b taskview_move up=1.0    pages=True
	       <c-b> taskview_move up=1.0    pages=True
	           J eval -q fm.ui.taskview.task_move(-1)
	           K eval -q fm.ui.taskview.task_move(0)
	          dd eval -q fm.ui.taskview.task_remove()
	    <delete> eval -q fm.ui.taskview.task_remove()
	       <c-l> redraw_window
	    <escape> taskview_close
	           q taskview_close
	           Q taskview_close
	           w taskview_close
	       <c-c> taskview_close
	</pre>
</div>


Related application: [lf - file manager](https://github.com/gokcehan/lf)

