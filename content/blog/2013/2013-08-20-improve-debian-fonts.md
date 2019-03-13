---
date: 2013-08-20
layout: post
title: "Improve Debian Fonts"
description: ""
category: tech
tags:
- linux
---

  
I put the following into ~/.fonts.conf, restarted Xorg, and now everything looks good.

{{ more }} 

{% highlight html %}
<?xml version="1.0"?>
<!DOCTYPE fontconfig SYSTEM "fonts.dtd">
<fontconfig>
    <match target="font">
        <edit name="antialias" mode="assign">
            <bool>true</bool>
        </edit>
        <edit name="hinting" mode="assign">
            <bool>true</bool>
        </edit>
        <edit name="rgba" mode="assign">
            <const>rgb</const>
        </edit>
        <edit name="autohint" mode="assign">
            <bool>false</bool>
        </edit>
        <edit name="hintstyle" mode="assign">
            <const>hintslight</const>
        </edit>
        <edit mode="assign" name="lcdfilter">
            <const>lcddefault</const>
        </edit>
    </match>
</fontconfig>
{% endhighlight %}
