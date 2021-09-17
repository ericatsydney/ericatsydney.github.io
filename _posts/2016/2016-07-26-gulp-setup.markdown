---
layout: post
title:  "Gulp Setup"
date:   2016-07-24 7:05:52 +1000
categories: Geek
---

My Gulp Resipe 
==============

Gulp
====
Gulp is the build script to stream line the process. We can use `gulp`` to convert sass, jsx, ES6, and minify, generate source map and so on.
 
`gulpfile.js` is where the streamline coding stored.

Gulp define the step as task:
{% highlight js%}
// jsx task run before jsx:build.
gulp.task('jsx:build', ['jsx'], function() {
  var bundler = browserify({
    entries: [paths.reactComponentsOutput + '/app.js'],
    paths: ['./node_modules'],
    debug: true
  })
  .transform(babelify, {
    presets: [es2015Preset, reactPreset],
    moduleRoot: './'
  });

  return bundler.bundle()
    .pipe(source('fcf.app.js'))
    .pipe(buffer())
    .pipe(plugins.uglify({ mangle: true }))
    .pipe(plugins.rename('fcf.app.min.js'))
    .pipe(gulp.dest(paths.reactComponentsOutput));
});
{% endhighlight %}


`browserify` is the plugin to make the browser could run node style js.

How to put the browserify into different bundles?

`watchify` is part of the `browserify` it will detect the change in the bundle, and only compile what's been updated.

`babelify` convert ES6 and React to vanilla JS, it could use plugin/ preset.

`vinly-source-stream` 

`gulp-browserify` and `gulp-babel` is out of maintenance

css pre-prossor: less, sass

css post-prossor: minify, ,cssnano, auto-prefixer

webpack
=======
Both Browserify and Gulp try to convert the node.js to nativejs, they are quite different though.

Webpack is using config while Browserify is using coding, webpack could only use file patern to target the source file, while Browserify could read specific files.

In webpack's world we have 2 terms: loader and plugins.

- `Loader` try to solve all the transform tasks. Like working with Reactjs, we use babel as the loader.

- `plugin` try to do other automation tasks, like minify.

Here's a wepack config [file](https://github.com/ericatsydney/mybabyjournal/blob/master/webpack.config.js) 


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
