---
date: 2012-07-22
layout: post
title: "Remove Spaces in File Names"
category: tech
tags:
- computing
- linux
---

Removes spaces in file names and replaces them with

{% highlight bash html %}
for file in *; do mv "$file" `echo $file | sed -e 's/  */-/g' -e 's/_-_/-/g'`; done
{% endhighlight %}
or
{% highlight bash html %}
find . -depth -name '* *' | while IFS= read -r f ; do mv -i "$f" "$(dirname "$f")/$(basename "$f"|tr ' ' _)" ; done
{% endhighlight %}
