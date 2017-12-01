---
layout: post
title:  "React and Redux"
date:   2017-11-11 13:30:00 +1000
categories: Geek
---

Practice make perfect, along with the reading `React and Redux`, I created a sandbox to test and practice what I learnt from that book. And in here, my blog, I will keep the notes to highlight some concept and tricks in ES6, React and Redux.

What's a React component?
Component is a JS function, or a class in ES6 flavour. In this class, we will define a constructor, which will
 + execute the super's constructor (to get the parent's props)
 + clarify the state using object literal
 + clarify the function and bind the context

What's a ReactDom, what's behind the scence when we call its render function?
Render is converting a ReactDOM (virtual DOM, JSX) to a HTML DOM, then inserting into the DOM root.

What's JSX?
JSX = JS expression + XML style tag (customised HTML)
JSX is JS expression, so it can be use in JS statement block (e.g. if...else), and it could contain JS expression in curly bracket.

What's prop?
That's the components' input.

What's state?
That's the private resource maintained by component.

What's react basic rule?
Pure function.

