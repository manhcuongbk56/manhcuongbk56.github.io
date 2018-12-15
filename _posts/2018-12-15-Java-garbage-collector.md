---
layout: post
title: "Java Garbage collector"
date: 2018-12-15 09:03:00 +0700
categories: Java
tags: Java GC
---
## Some notes about Java garbage collector
1.  It contains `Young generation`, `Old generation` or sometimes call `Tenured generation`.
Divide to these generation cause of `the weak generational hypothesis`.
+ `Young generation` : newly created object will not live long.
+ `Old generation`: after object created, if it survives after some garbage collecion it will be moved from
`young generation` to `old generation`

2. Since it have some kinds of GC, we can make our choice to get a appropriate one.
+ `Serial collector`: run only on once core, pause time will be huge, for client style machine. It is default GC.
We can chose it by using `-XX:+UseSerialGC` command line option.
+ `Parallel collector`: utilize multi core of model PC. GC will run on multi core, reduce pause time.
Server machine should use it, use `–XX:ParallelGCThreads=n` command line option with n is number of core.
+ `Parallel compacting collector`: the left side of each generation is dense. The amount of space that can be recovered
is not worth compact. So, it will find the point in the right side of dense space to start compact.
=> eventually, it'll replace `parallel collector`. Command line option to use `-XX:+UseParallelOldGC`