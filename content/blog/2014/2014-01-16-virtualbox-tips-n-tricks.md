---
date: 2014-01-16
layout: post
title: "VirtualBox Tips 'N' Tricks"
description: ""
category: tech
tags: 
- virtual
---
 
To change the resolution

{% highlight bash %}
VBoxManage controlvm "MACHINE NAME" setvideomodehint WIDTH HEIGHT BPP
{% endhighlight %}
Replacing "MACHINE NAME", WIDTH, HEIGHT and BPP (bits per pixel - 24 or 32) with your values
