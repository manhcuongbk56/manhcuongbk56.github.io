---
layout: post
title: Elixir Logger
date: 2019-07-22 20:00 +0700
categories: Elixir
---

# I. Elixir Logger
## Custom logger

Logger is an event manager powered by **:gen_event**. We can write new backend logger
by creating an event handler, like: 
[Console implement example](https://github.com/elixir-lang/elixir/blob/master/lib/logger/lib/logger/backends/console.ex)

## II. Typespecs and behaviour

[Document](https://elixir-lang.org/getting-started/typespecs-and-behaviours.html)