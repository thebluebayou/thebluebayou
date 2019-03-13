---
date: 2013-04-26
layout: post
title: "Delete Trailing White Space"
description: ""
category: tech 
tags:
- vim
---
 
   
Delete all trailing whitespace (at the end of each line) with:

{{ more }} 
{% highlight bash html linenos %}
:%s/\s\+$//
{% endhighlight %}
 
