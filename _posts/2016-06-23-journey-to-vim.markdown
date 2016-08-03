---
layout: post
title:  "Vim"
date:   2016-06-23 6:30:52 +1000
categories: Programming
---
Mode
=====
- Column edit mode: `Ctrl + v` switch column edit mode (visual block) , use 'up' and 'down' to choose column, `I` switch to insert mode, edit then `Esc`

- Insert Mode: <tbc>

- Normal Mode: <tbc>

- View Mode: `v` in normal mode to switch to visual mode

Moving Around
============
`motion`

- `gg` go to the top of the file, `G` go to the bottom of the file ,`zz` make the current line to the center.

- `{` & `}` move by paragraph

- `(` & `)`, `[` & `]`  move by parentesis and square bracket

- `vf_` & `vt_` move to the next `_`, first one will include search key and second one will stop before the key

- `-` Go to first non-space character in last line, `+` in next line

Mapping
=======
{% highlight shell%}
nmap <C + L> : <C + W> <C + L>
{% endhighlight %}


AutoScript
==========
{% highlight shell%}
TBC
{% endhighlight %}

Productive
==========
- `%s\old\new\g` global replace, `%s\old\new\gc` replace with confirmation

Plugin
======
- Pathogen use `git clone` command to get the source code

- Vunble use .vimrc to config and run `:PluginInstall`

- Some useful plugins: ctrlP, nerdtree, airline, syntastic


Multple File Editing
====================
- `:vsp` slip screen vertically

- `ctrl + w` and `ctrl + h` swap the slip, so we could add mapping like this:

- `:bn`, `:bp`, `:b1`, `:b2`, `:b3` change buffer

- `ctrl + ^` swap buffer

- Open multiple files
{% highlight shell%}
$ vim *.php
{% endhighlight %}


- plugin `nerdtree`: help to show files in folders

- plugin `controlP` help to quick search by file name

- plugin `airline` help to organize tab

- plugin `vinegar` help you to get files in current directory

Linting
=======
- plugin `Syntastic` help to manager the linting checker

- `:SyntasticCheck` enable the linting

- `:SyntasticToggle` switch from the passive and active mode

- `:SyntasticInfo` check the current checkers.


Appendix
========
[A very simple reference](http://www.worldtimzone.com/res/vi.html).

My [config files](https://gist.github.com/ericatsydney/b5e62ef00b4eb80c2b0bd3d80d9b1932) on Gist. 