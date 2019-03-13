---
date: 2013-05-30
layout: post
title: "Mutt Marking all New messages for deletion and clears all flags"
category: tech
tags: 
- mutt
---
 
   
It first selects all messages marked “New” and untags them. Then, it selects all messages marked “Old” but unread and untags them as well. Finally, it marks them all as deleted

{{ more }} 

{% highlight bash html %}
macro index <esc>m "T~N<enter>;WNT~O<enter>;WO\CT<enter><tag-prefix>d" "mark all messages read"
{% endhighlight %}

{% highlight bash html %}
<tag-prefix> = ; 
{% endhighlight %}
