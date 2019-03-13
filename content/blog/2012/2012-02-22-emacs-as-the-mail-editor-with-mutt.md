---
date: 2012-02-22
layout: post
title: "To use emacs as the mail editor with mutt"
category: tech 
tags:
- linux
---

Add the following line to your muttrc file:
{% highlight bash %}
set editor = "/usr/bin/emacs -nw %s"
{% endhighlight %}

Add the following line to your .emacs file:
{% highlight bash %}
(load "~/post.el")
{% endhighlight %}
