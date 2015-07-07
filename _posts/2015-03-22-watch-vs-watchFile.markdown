---
layout: post
author: Jim Tunnessen
title:  "fs.watch vs fs.watchFile"
date:   2015-03-22 15:15:22
categories: Programming
permalink: fsWatchFile
tags: JavaScript, node.js, programming, watchFile, file system, node package manager
published: true
---
I have been playing around with node.js lately and found an issue with fs.watch() which used to be the *go to or somewhat more stable* function for file watching.

I wrote up a script that used fs.watch and it kept throwing an error.

{% highlight ruby %}
Error: watch ENOSPC 

***meaning there was no space on the drive***
{% endhighlight %}

This was incorrect. I switched over to _fs.watchFile_ and everything works just fine.
Here is the link to the [node file system documentation](https://nodejs.org/docs/latest/api/fs.html)

This was using node v0.10.37.
