---
layout: post
title:  "JS的代码审查"
date:   2016-05-29 6:05:52 +1000
categories: Thinking
---
下面这些技巧能帮助提高代码审查通过率

用上·use strict`来限制松散的语法审查，例如没有声明的变量赋值

创建变量来缓存jQuery的查找
用object literal来替代switch
将参数置顶并放到object literal里面，方便用jquery重写
使用jquery查找时尽量用上context

尽量不要将css带到JS里，用class来替代

将复杂的function拆分，将复杂的文件拆分成单一功能的文件

格式

PHP的代码审查
用 foreach （$array as $key => $value）, $key可以充当计数器$i

