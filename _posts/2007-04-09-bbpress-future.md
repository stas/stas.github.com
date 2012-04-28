---
layout: post
title: bbPress Future!
tags:
- Open Source
---

This days a new thread was opened on [bbPress.org][1]. The subject is really interesting bbPress being a production of [WordPress team][2] and everybody is waiting from this [BBS][3] the same results WordPress achieved! That is strange... for the last month I received a proposition from [Mediash City Town Hall][4] for redesign of their website. The website is really giant. I counted approximately 700 posts, uncategorized and almost impossible to be easily converted to modern [CMSs][5]. As a solution for the project I decided to use the famous [WordPress][2] and for their forum [bbPress][6]. The problems I crushed on working with these two were:

  1. Integrating bbPress and WordPress in another language is impossible, at least for the moment. I'm getting an error with classes. The problem can be solved joining both the bbPress .mo file contents into WordPress .mo file. Next you'll have to define only `WPLANG` in the `wp-config.php` and leave `BBLANG` intact in the bbPress `config.php`. The class will use only the first file this way translating both.
  2. Developing a new template based on another ajax libs than prototype (the bbs uses this library, in the core) is also impossible. You have to follow the [Valerio Proietti][7] [advices on forum.mootools.net][8] if you want to modify the ajax functions and use another library.

The most interesting thing is that guys from bbPress left my question almost
uncommented. Even on [bbPress Russia][9] the subject was ignored. In the end I
understand that their #1 priority is far from redesigning the forum, so for
the moment we'll have to wait a bit. More infos and questions you'll be able
to ask and answer on the [official bbPress forums subject][10].

   [1]: http://bbpress.org/forums/topic/1023?replies=3
   [2]: http://wordpress.org
   [3]: http://en.wikipedia.org/wiki/Bulletin_board_system
   [4]: http://primariamedias.ro
   [5]: http://en.wikipedia.org/wiki/CMS
   [6]: http://bbpress.org
   [7]: http://mad4milk.net
   [8]: http://forum.mootools.net/viewtopic.php?id=2337
   [9]: http://bbpress.ru
   [10]: http://bbpress.org/forums/topic/1023

