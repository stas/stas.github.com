---
layout: post
title: Reviewing Pagoda Box Cloud Services
tags:
- Planet
- Software
- Thoughts
---

If you are familiar with [Google's App Engine][1], or [Heroku][2], well...
[Pagoda Box][3] is a cloud service to deploy PHP applications (be those CMSs, blogs or framework based apps).

![][4]{:.alignright}

I mentioned Heroku as the closest example of what does Pagoda Box because:

* You are deploying with [Git][5]
* It's very much integrated with [GitHub][6]
* You can scale in any ways (by adding more resources to current box or by cloning current box)
* You can enable and disable add-ons for every app you use (from dedicated MySQL to Memcache, though some are not yet available in private beta).
* Free plan for testing/deployment Pretty nice so far.

So what else gives you Pagoda Box:

* First of all, it doesn't ask you about your credit card!!! (It is a feature!)
* Writeable directories!!!
* SSH access to your writeable directories
* Custom rewrite rules, PHP version and PHP environment settings
* Team members!!!
* Free DNS aliases!!!
* Awesome UI for every tool you will deal with on Pagoda Box
* Awesome Stats Dashboard

I've been invited to a private beta recently (you can ask for an invite on twitter), so I tested their services on a [WordPress][7]/[BuddyPress][8] + [Courseware][9] deployment. The only problem I had was the lack of a tool like Bundler where I could specify from where what to pull ([git sparse checkout][10] might be an option I already recommended).

You can [clone my repository][11] or just have a look at `[wp-config.php][12]` (hint: follow the `$_SERVER` keywords) and `[.box][13]` files I had to change to make WordPress run on Pagoda Box.

Give it a shot [here: courseware.pagodabox.com][14]. By the way, looks like [Ubuntu][15] powers their boxes, I would love to find out more about what other free software they use. Disclaimer: I'm not affiliated in any ways with the guys behind Pagoda Box, and what I wrote was done just because it was fun.

   [1]: http://code.google.com/intl/en-US/appengine/
   [2]: http://www.heroku.com/
   [3]: http://www.pagodabox.com/
   [4]: http://dl.dropbox.com/u/20301790/blog/ui4tC.png
   [5]: http://git-scm.com/
   [6]: https://github.com/
   [7]: http://wordpress.org/
   [8]: http://buddypress.org/
   [9]: http://scholarpress.github.com/buddypress-courseware/
   [10]: http://www.kernel.org/pub/software/scm/git/docs/git-read-tree.html#_sparse_checkout
   [11]: https://github.com/stas/cw.nerd.ro
   [12]: https://github.com/stas/cw.nerd.ro/blob/master/wp-config.php
   [13]: https://github.com/stas/cw.nerd.ro/blob/master/.box
   [14]: http://courseware.pagodabox.com/groups/pagoda-box-crash-course/courseware/
   [15]: http://ubuntu.com/

