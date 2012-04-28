---
layout: post
title: Publish git repository to svn easily
tags:
- Blogging
- Mint rubbing
- Planet
- Thoughts
---

I'm using git a lot, and lately I started to publish my WordPress stuff on [github][1]. Some of that code are plugins, and as you may know [WordPress.org][2] are using SVN a lot. I've googled a lot of solutions on how to publish code from git to svn, untill I discovered the steps below.

First you will need to know the revision of your initial repo (you can also call it repository creation commit). You can find it by searching [trac][3] or any other web interface that handles the SVN log. Let's say in my example I had to search for some-maps plugin creation commit. Go to this link, by replacing `KEYWORD` with your repo name:

[http://plugins.trac.wordpress.org/search?q=_KEYWORD_ ][4] ![][5]

The revision number you need is the one in squared brackets. Now it's easy. Open your .git/config file, and append/modify the `svn-remote` part:

~~~
[svn-remote "svn"]
  url = https://plugins.svn.wordpress.org
  fetch = KEYWORD/trunk:refs/remotes/trunk
  branches = KEYWORD/branches/*:refs/remotes/*
  tags = KEYWORD/tags/*:refs/remotes/tags/*
~~~

Once you're finished, use the git svn fetch command, like this: `git svn fetch
-r REVISION_NUMBER` Now all you need is to switch to svn branch, I suggest you
creating a new banch that will be synced with svn trunk: `git checkout trunk
-b svn` Now you can merge master to svn, commit and tag:

~~~
  git checkout svn
  git merge master
  git svn dcommit
  git svn tag TAG_NAME
~~~

Happy forking!

   [1]: https://github.com/stas
   [2]: http://WordPress.org
   [3]: http://trac.edgewall.org/
   [4]: http://plugins.trac.wordpress.org/search?q=
   [5]: http://stas.nerd.ro/blog/data/kep7P.png
