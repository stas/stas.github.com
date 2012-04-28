---
layout: post
title: A not so bad CUBRID feedback
tags:
- Open Source
- Planet
- Romania
- Software
---

I took a chance to play around with [CUBRID][1] today (well it's kinda new Open Source RDBMS, partially developed by Romanian engineers, claiming to be very fast and mostly compatible with MySQL solution). Reason for that was:

  1. I didn't do something like this for years, lately, most of my research interests got away from servers administration and all the stuff that's happening around it
  2. [They started a contest][2] that touched my feelings because of PHP being used and their nice [WordPress support page][3] (WordPress has nothing to do with the contest, but it uses PHP and MySQL and that connected the dots)

If you are still reading this article in the hope to find the contest answers,
go away, it's not about it. It's about how ready is CUBRID for development and
my experience with it on Ubuntu (Natty).

First of all kudos to the team for great set of pre-compiled builds and tools,
but the lack of debs is a problem right now. Searching for CUBRID PPA took me
to their [Launchpad page][4], that is way outdated and that kinda pisses off
developers that use Debian/Ubuntu, and a lot of them do! So even though the
software looks easy to install, having a debs repo is a no excuse thing that
should be done.

Also on this topic, none of the PDO or PHP driver packages worked for me (I'm
using PHP 5.3.5-1ubuntu7.2 from Natty repos) so I had to install PEAR and
compile one. From that point, the Nginx+PHP5-FPM+CUBRID_8.4.0 development
environment was ready.

The contest problem itself is not a hard one, but reading it's statement
should lead you to discover interesting features of the CUBRID, along which I
was pretty impressed with:

  * [SQL tool][5] Client-Server, Standalone execution mode
  * [Cleaner SQL syntax][6], though [pretty-much compatible with MySQL][7] (no storage engines, encoding... just like the new <html> tag)
  * Service and user management tools (users are stored in plain text files, everything has a tool for it, servers are started per database, well defined ACL, all very clean and well designed)
  * Databases can have the home you want for them (you can create databases of what size you want and wherever you want inside your filesystem) and the renaming is a snap, also you can define an SQL file for those to use and so on... very smart!
  * Not the last, it was a pleasure to work with their latest "[implicit type conversion][8]" feature ([More details here...][9]).

Per all, it was worth spending a couple of hours playing with the technology,
more than that, I also submitted a solution for their contest, so It might be
fun too. Give it a try if you're searching for a self hosted RDBMS solution
for your start-up [or just to hack][10].

   [1]: http://www.cubrid.org/
   [2]: http://www.cubrid.org/cubrid_it
   [3]: http://www.cubrid.org/about_wordpress
   [4]: https://launchpad.net/~cubrid/+archive/cubrid
   [5]: http://www.cubrid.org/manual/840/en/CSQL%20Execution%20Mode
   [6]: http://www.cubrid.org/manual/840/en/CUBRID%20SQL%20Guide
   [7]: http://blog.cubrid.org/cubrid-life/cubrid-vs-mysql/
   [8]: http://www.cubrid.org/manual/840/en/Implicit%20Type%20Conversion
   [9]: http://blog.cubrid.org/news/cubrid-8-4-0-has-arrived-w-x2-faster-database-engine/
   [10]: http://sourceforge.net/apps/trac/cubrid/report/1

