---
date: 2012-03-08
layout: post
title: "Portable Emacs "
category: tech
tags:
- linux
- emacs
---

<!--start excerpt--> 
While reading gmane.emacs.help I came accross this post where somebody asked how he could make a portable app out of Emacs' Windows version.

So since I'm still at my internship (where they use Windows) and just recently obtained an iAudio X5L portable media player which behaves like an USB2 harddisk to the OS I wondered if I could manage to make Emacs portable.

Short version: I could, the "hardest" part was in fact not even Emacs related, but my sheer lack of knowledge about Windows batch script.

I started by creating a "SOFT" folder on my external drive (named E: by Windows on this box) and extracted the altest Emacs build from the ntemacs project in this directory, thus creating "E:\SOFT\emacs" with all the usual subfolders.

Next I created a site-lisp/site-start.el file and added the following as suggested on usenet:

{{ more }} 

{% highlight bash %}
(let ((home (concat (substring (car command-line-args) 0 2) "/SOFT")))
  (setq user-init-file (concat home "/config/.emacs"))
  (setq auto-save-list-file-prefix (concat home "/config/.emacs.d/auto-save-list/.saves-")))
{% endhighlight %}

You'll need to adapt this to your particular environment of course.

This makes Emacs load my user-init-file (aka ".emacs") from "E:/SOFT/config/.emacs" and moves the auto-save-list to the external device as well, this should be superfluous though as I change the location of HOME as described later, but it accounts for the cases that you don't want to change your HOME.

This is in fact the entire Emacs side of the story, though you will probably have some work making your elisp packages work with relative paths if you didn't take that into account before.

Now you need to redefine HOME in Windows (well, you don't need to but I find it useful), you can either do that globally with the System Properties or autoexec.bat in DOS based Windows versions, but I preferred to make it dynamic by writing a wrapper batfile that sets this variable and then launches Emacs. I named it runemacs.bat (how appropriate;)) and put it in Emacs' bin directory, the content looks like this:

{% highlight bash %}
set HOME=%CD%\..\..\config
runemacs
{% endhighlight %}
