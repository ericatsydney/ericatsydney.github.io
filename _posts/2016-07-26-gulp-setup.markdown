---
layout: post
title:  "Gulp Setup"
date:   2016-07-24 7:05:52 +1000
categories: Geek
---

My Gulp Resipe 
==============
[Please refer my gulpfile.js](#) 

Gulp
====
Gulp is the build script to stream line the process. We can use `gulp`` to convert sass, jsx, ES6, and minify, generate source map and so on. 

`broserify` is the plugin to make the browser could run node style js.

How to put the browserify into different bundles?

`watchify` is part of the `browserify` it will detect the change in the bundle, and only compile what's been updated.

`babelify` convert ES6 and React to vanilla JS, it could use plugin/ preset.

`vinly-source-stream`

`gulp-browserify` is out of maintenance.

`gulp-babel` is out of maintenance ?

webpack
=======
Both Browserify and Gulp try to convert the node.js to nativejs, they are quite different though.

Webpack is using config while Browserify is using coding, webpack could only use file patern to target the source file, while Browserify could read specific files.

In webpack's world we have 2 terms: loader and plugins.

- `Loader` try to solve all the transform tasks. Like working with Reactjs, we use babel as the loader.

- `plugin` try to do other automation tasks, like minify.



npm - Node Package Management
=============================

npm/Gulp is one of the most important skill set of front-end developer. It help us build our app making use of the open source library and on the other hand it setup a very good standard for the developer going to put their project as open source.

`npm install --save` 

- symlink error: use option `--no-bin-links`

- specify version: could add version like this `package_name@version` or update the package 

`npm update`

`npm list`

`npm rebuild` 'binding not found' may be caused by node version upgrade, we can use this command to fix

`npm uninstall`

`package.json` is the npm config file. In this file, we can use prefix to control which version of the package to install. e.g. '1.2.3' using '~' (same 1st and 2nd partition) or '^' (latest and same 1st partition) as prefix.


node
====

- stream

- read vs write

Reference
=========
[How to split bundle](https://www.snip2code.com/Snippet/462312/Browserify---separate-app-and-enternal-v) 
[Gulp Recipes](https://github.com/gulpjs/gulp/tree/master/docs/recipes) 
