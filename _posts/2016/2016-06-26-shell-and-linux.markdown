---
layout: post
title:  "Shell script and Linux"
date:   2016-06-23 6:30:52 +1000
categories: Geek
---
Linux
============
- Manually installation
 - `configure`: check the system and collect dependency information of this system.
 - `make`: run the Makefile where keep the software installation info and system config.
 - `make install`: move the file to correct system location.

- Alias
{% highlight shell%}
#Personal alias
alias foo='git diff'
# Muti-command alias
alias bar='command1 xxxx; command2 xxxx'
{% endhighlight %}

Use `source <alias file>` to make the change take effect. 

- grep, pipe
{% highlight shell%}
# recursive search keyword in specific suffix files, list the file name as result.
grep -rl --include=\*.{php,inc} 'breadcrumb'
{% endhighlight %}

- find 
{% highlight shell%}
# search 'js' folder in current direcotry
find . -type d -name js
{% endhighlight %}

- sed
sed is the stream editor, but can edit files directly too, with the following:
{% highlight shell%}
sed -i -e 's/foo/bar/g' filename
{% endhighlight %}

- how to pass parameter

`$0` is the string value of command itself

`$1` is the 1st parameter

`$2` is the 2nd parameter and so on...

- package management: `yum install` and `apt-get`

- `curl` and `wget` to get the file from internet.

- Export/ echo

- Source

- Crontab

- which / whereis

- scp

- chmod and chown

- start service

- backup file

- shortcut: `ctrl + a` go to start of the command, `ctrl + e` go to the end of the command

- file structure

- inotifywatch

- system checking `free -m`
