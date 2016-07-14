---
layout: post
title:  "Vim"
date:   2016-06-23 6:30:52 +1000
categories: Programming
---
Shortcut Cheatsheet
===================
[A very simple reference](http://www.worldtimzone.com/res/vi.html).

- `Ctrl + v` switch column edit mode (visual block) , use 'up' and 'down' to choose column, `I` switch to insert mode, edit then `Esc`

- `v` in normal mode to switch to visual mode

- `gg` go to the top of the file, `G` go to the bottom of the file ,`zz` make the current line to the center.

- `dd` cut one line, `d` cut

- `cw`, `cc` delete and insert

- `yy` `yw` yank command

- `}` Go to the paragraph end
     
- `p` paste

- `%s\old\new\g` global replace, `%s\old\new\gc` replace with confirmation

How to install Plugin
=====================
- Pathogen use `git clone` command to get the source code

- Vunble use .vimrc to config and run `:PluginInstall`

- Some useful plugins: ctrlP, nerdtree, airline, syntastic

Multple File Editing
====================
- `:vsp` slip screen vertically

- `ctrl + w` and `ctrl + h` swap the slip, so we could add mapping like this:
{% highlight js%}
nmap <C + L> : <C + W> <C + L>
{% endhighlight %}

- `:bn`, `:bp`, `:b1`, `:b2`, `:b3` change buffer

- `ctrl + ^` swap buffer

- plugin `nerdtree`: help to show files in folders

- plugin `controlP` help to quick search by file name

- plugin `airline` help to organize tab

- plugin `vinegar` help you to get files in current directory

Linting
=======
- plugin `Syntastic` help to manager the linting checker

- `:SyntasticCheck` enable the linting

- `:SyntasticInfo` check the current checkers.