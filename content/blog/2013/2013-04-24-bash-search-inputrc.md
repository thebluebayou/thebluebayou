---
date: 2013-04-24
layout: post
title: "Bash Search .inputrc"
description: ""
category: tech 
tags:
- computing
- linux
---
 
   
With four lines, you'll be able to type the beginning of the command (e.g. "cd") and press the up arrow to see the most recent command containing the text you typed (e.g "cd ~/Library"). 


{{ more }} 

This makes it much easier to find what you're looking for. To make this happen, create a text file called .inputrc in your home folder and put the following four lines inside:

{% highlight bash html linenos %}
"\e[A": history-search-backward
"\e[B": history-search-forward
set show-all-if-ambiguous on
set completion-ignore-case on
{% endhighlight %}
 
