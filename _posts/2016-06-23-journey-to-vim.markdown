---
layout: post
title:  "Vim"
date:   2016-06-23 6:30:52 +1000
categories: Programming
---
Shortcut Cheatsheet
===================

- `Ctrl + v` switch column edit mode (visual block) , use 'up' and 'down' to choose column, `I` switch to insert mode, edit then `Esc`

- in normal mode, press `v` switch to visual mode

- `dd` cut line

- `d` cut

- `p` paste

- `%s\old\new\g` global replace, `%s\old\new\gc` replace with confirmation

- yank `yy` `yw`

- `gg` go to the top of the file, `zz` make the current line to the center.
     
- Go to the paragraph end


Multple File Editing
====================
- `:vsp` slip screen vertically

- `ctrl + w` and `ctrl + h` swap the slip, so we could add mapping like this:
{% highlight js%}
nmap <C + L> : <C + W> <C + L>
{% endhighlight %}

- `:bn`, `:bp`, `:b1`, `:b2`, `:b3` change buffer

- `ctrl + ^` swap buffer

- plugin `vundle`, `vinegar`, `nerdtree`: help to show files in folders

- plugin `controlP` help to quick search by file name

Linting
=======

Plugin
======
ctrlP, nurtree


