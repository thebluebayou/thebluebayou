---
date: 2013-07-29
layout: post
title: "Find and Replace"
description: ""
category: tech
tags:
- linux
---

{% highlight bash %}
find . -name '*.html' | xargs perl -pi -e 's/oldtext/newtext/g'
{% endhighlight %}

\n adds a new line

 finds  any text and replaces it with <!--start excerpt-->

{% highlight bash %}
find . -name '*.md' | xargs perl -pi -e 's/any text/<!--start excerpt--> /g'
{% endhighlight %}
finds any text and replaces it with a new line and {{ more }}  (\n being new line)

{% highlight bash %}
find . -name '*.md' | xargs perl -pi -e 's/any text/\n{{ more }} /g'
{% endhighlight %}

{% highlight bash %}
find . -type f -print0 | xargs -0 sed -i /KeyWord/d
{% endhighlight %}
**Deletes line containing KEYWORD**

First command find finds all the standard files (not directories, or pipes, or etc.), prints them separated by \0 (so filenames can contains spaces, newlines, etc.).

Second command xargs reads the output of find, grabs a list based on a separator (\0 because of -0), invokes sed -i [...] with added parameters from the list (sed will be called multiple times if there are a lot of files, as the maximum length of the parameters is limited in each invocation).

The sed command modifies in-place (-i).

As to /KeyWord/d, it'll delete lines containing the regular expression KeyWord
