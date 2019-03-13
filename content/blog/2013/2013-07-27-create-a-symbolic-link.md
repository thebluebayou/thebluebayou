---
date: 2013-07-27
layout: post
title: "Create a Symbolic Link"
description: ""
category: tech 
tags: 
- linux
- computing
---
 
{% highlight bash html %}
ln -s [TARGET DIRECTORY OR FILE] ./[SHORTCUT]
{% endhighlight %}

For example 

{% highlight bash html %}
ln -s /usr/local/apache/logs ./logs
{% endhighlight %}

This points a symbolic link "./logs" to "/usr/local/apache/logs" 

