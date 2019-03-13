---
date: 2012-02-22
layout: post
title: "Print From Mutt"
category: tech 
tags:
- linux
---

To print from Mutt install enscript and add the following lines to muttrc

{% highlight bash %}
set print="yes"
set print_split
set print_command="enscript --portrait --header='%n@%M:%d|%F %C|Page ($%/$=)' --media=A4 --silent --encoding=88591 --pretty-print=mail --printer=HP-Deskjet-USB"
set print_decode
{% endhighlight %}
