---
layout: post
title:  "Java Garbage Collection"
date:   2021-09-06 8:15:00 +1000
categories: Geek
---

In order to know Java Garbage collection, we need to understand [how the JVM to memory and thread works](https://stackify.com/jvm-metrics/).

The Java profiler is a set metrics (cpu, memory and thread) in a certain period. The different performance monitoring products will provide the [different format profilers](https://stackify.com/java-profilers-3-types/).

[VisualVM](https://visualvm.github.io/) is one of them, it is a open source tool to provide the standard JVM profiling, it's very useful to do garbage collection.

In the VisualVM monitor tab, if we can see the big sawtooth pattern for memory usage (steadily increase and then drop suddenly), it means the garbage collection is working efficiently.

Another way to check the memory leaks is compare the different heapdump, make sure when the time passed by, there is no instance increasing the number and cannot be recycled.
