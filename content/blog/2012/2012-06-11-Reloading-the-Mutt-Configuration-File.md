---
date: 2012-06-11
layout: post
title: "Reloading the Mutt Configuration File"
category: tech 
tags:
- linux
- computing
---

I find it a bit annoying that I have to re-enter my password twice every time I (re-)start mutt when I want to update my configuration file. Well, it appears I don't need to be doing restarting mutt. The MuttWiki describes a way to re-load the configuration after mutt is running. Type the following into mutt after you've changed your muttrc file:

:source /path/to/your/muttrc
Note that shell expansions may not work---you should spell out the full path.

