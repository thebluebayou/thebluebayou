---
date: 2013-08-05
layout: post
title: "Browsing man pages in vim"
description: ""
category: tech
tags: 
- vim
---
 
  
What's it good for? The default key binding for K (that's "shift-k" I guess) in vim is to look up the word under the cursor using the man command. The sad thing about this process is that vim gets replaced by less (or whatever pager you happen to be using), and that once you're done reading the page, you have to press "Enter" one additional time to get back into vim and back to whatever you were doing. Kinda breaks your flow, you know?

Once you've added the three lines above to your .vimrc things are quite different. When you hit K, the man page opens as a new split window inside of vim so you're staying in the same environment. All the usual binds for switching between windows work, so you can keep the man page open while going back to your code. Better yet, the man page will be "syntax highlighted" using different colors for headings, text, and (you guessed it) references to other man pages. And the best thing? You can browse man pages the same way you browse tags: use "ctrl-]" to open another man page and use "ctrl-t" to "go back" to the previous one.

Stolen from http://nilisnotnull.blogspot.co.uk/2011/10/browsing-man-pages-in-vim.html

{{ more }} 
 
{% highlight bash %}
let $GROFF_NO_SGR=1
source $VIMRUNTIME/ftplugin/man.vim
nmap K :Man <cword><CR>
{% endhighlight %}
 
