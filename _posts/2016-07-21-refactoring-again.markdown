---
layout: post
title:  "Refactoring AGAIN"
date:   2016-07-21 9:05:52 +1000
categories: Programming
---

To a programmer, refactoring should never end. In the real-life project, the endless refactoring is impossible. But we could do it in our mind, read the old coding created by you, think any better solution or new way to implement.

Like setting up my `.vimrc`, that's a happy project will last forever. because I reckon it will help me better the work flow and make me more productive, and further more I can learn the new exciting stuff.

I have make a post about [refactoring](http://ericatsydney.github.io/programming/2016/05/23/refactoring.html). And in this post, I would like to make notes about some general rule or more idea in JS aspect.

Some general principle
======================
All of these aim to make the program **readable, extensible, efficient**.

- readable

-- Sufficient comment.

-- Semantic naming (variables, functions, ).

- [Linting](http://ericatsydney.github.io/programming/2016/07/15/linting.html)

- extensible

-- Slip / extract logic to separate functions/files.

-- Centralize: keep the similar functions, setting in one file.

-- Decoupling: observer design pattern

-- DRY: use iterator to repeat.

-- Use function's parameter  

Reference
=========
- [How to write self-document coding](https://www.sitepoint.com/self-documenting-javascript/) 
