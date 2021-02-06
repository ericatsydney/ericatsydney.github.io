---
layout: post
title:  "Java Multi Thread"
date:   2021-02-01 17:05:00 +1000
categories: Geek
---

Before explaining multi thread, we must know what's process. 

We can think of process is the a task in the OS. Thread is the subtask in the tasks.

A task can contain one or more than one subtask. See this chart:

Multi Thread Programing is to make sure the multiple subtask cannot work efficiently without conflict with other subtasks.

Then we will get into the concept of thread safety. To achieve this goal, several things we can do

- Immutable variable, we can use `private final` to define the variable.

- Use stateless method, pure function, the output only rely on input but not the environment.



