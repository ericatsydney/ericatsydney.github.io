---
layout: post
title:  "Gulp Setup"
date:   2016-07-24 7:05:52 +1000
categories: Programming
---

node
====

npm
===
`npm install --save` 
symlink error: use option `--no-bin-links`
specify version: could add version like this `package_name@version` or update the package 

`npm update`

`npm list`

`npm rebuild` 'binding not found' may be caused by node version upgrade, we can use this command to fix

`npm uninstall`

`package.json` is the npm config file. In this file, we can use prefix to control which version of the package to install. e.g. '1.2.3' using '~' (same 1st and 2nd partition) or '^' (latest and same 1st partition) as prefix.


Gulp
====

We can use gulp to automate the pre-process, e.g. convert sass, jsx, ES6, and minify, generate source map and so on. 

`broserify` is the tran

`gulp-babel` 

`babelify` 

`gulp-bundle` will output bab