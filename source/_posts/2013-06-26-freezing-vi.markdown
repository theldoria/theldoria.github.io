---
layout: post
title: "Freezing vi"
date: 2013-06-26 10:29
comments: true
categories: unix
tags: vi 
---

Today I stumbled over an frozen vi, after using `ctrl-s` (from a remote session). To resolve it simply use `ctrl-q`.

This can easily happen if you switch from emacs, where `C-x C-s` saves the buffer, to vi, where you have to use `ESC :w`.

The reason for this is the [XON/XOFF protocol](http://en.wikipedia.org/wiki/XON XON/XOFF). Sending `ctrl-s` is XOFF, stopping the communication (in one direction), and `ctrl-q` sends XON, reenabling the data exchange.
