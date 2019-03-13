---
date: 2012-06-15
layout: post
title: "The X server will not be able to send the VDPAU driver name to libvdpau"
category: tech 
tags:
- computing
- gentoo
- linux
---

AFAIK that is because the dri and dri2 modules from xorg-x11(mesa) opengl setup are not in path. 
I worked around this by

{% highlight bash html linenos %}
Quote:
Section "Files" 
ModulePath "/usr/lib/xorg/modules" 
ModulePath "/usr/lib/opengl/xorg-x11/extensions/" 
... 
EndSection
{% endhighlight %}

