---
layout: post
title:  "Shell script and Linux"
date:   2016-06-23 6:30:52 +1000
categories: Programming
---
Linux
============
- Alias
{% highlight shell%}
#Personal alias
alias foo='git diff'
{% endhighlight %}

- grep, pipe
{% highlight shell%}
# recursive search keyword in specific suffix files
grep -rl --include=\*.{php,inc} 'breadcrumb'
{% endhighlight %}

- find 
{% highlight shell%}
# search 'js' folder in current direcotry
find . -type d -name js
{% endhighlight %}

- package management: `yum install` and `apt-get`

- `curl` and `wget` to get the file from internet.

- Export

- Crontab

- which / whereis

- scp

- chmod and chown

- start service

- backup file

- shortcut: `ctrl + a` go to start of the command, `ctrl + e` go to the end of the command