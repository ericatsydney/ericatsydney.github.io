---
layout: post
title:  "Refactoring AGAIN"
date:   2016-07-21 9:05:52 +1000
categories: Geek
---

To a programmer, refactoring should never end. 

In a real-life project, we cannot afford the endless refactoring. But we could do it in mind, have the chance to read some old coding created by yourself and rethink. Any other solution? Any better way to implement?

Just like setting up my `.vimrc`, that is a happy project probably lasting forever. Because I reckon it will help me better the work-flow and then make me more productive, and further more I could learn some cool stuff from that.

I have made a post about drupal [refactoring](http://ericatsydney.github.io/programming/2016/05/23/refactoring.html) in my daily life.
 
And here I would like to make some notes about the rules in JS aspect or the general ideas.

Some general principle
======================
All the refactoring aim to make the program **readable, extensible, efficient**.

- readable

  * Sufficient comment.

  * Semantic naming (variables, functions, nameSpace).

  * [Linting](http://ericatsydney.github.io/programming/2016/07/15/linting.html)

- extensible

  * Extract logic to separate functions / files.

  * Centralize: keep the similar functions, setting in one file.

  * Decoupling: observer design pattern

  * DRY: use iterator to repeat.

  * Use function's parameter

Reference
=========
- [How to write self-document coding](https://www.sitepoint.com/self-documenting-javascript/) 
