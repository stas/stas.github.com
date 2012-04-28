---
layout: post
title: How we built Ink2Digital, StartupWeekend Cluj
tags:
  - Planet
  - Software
  - Thoughts
---

As I was writing, Cluj-Napoca needs more events like [Startup Weekend][2], and the proof of that could be spotted during last weekend. Just to make myself clear, while I enjoyed most of the aspects of this _contest_, here are some things I didn't like that much: 

  * A project can win just by having a nice pitch/presentation
  * A lot of time was wasted because there were no clear rules that no one wants projects designed for google ads revenue
  * Although people were talking a lot of MVP, it felt like no one cares if you achieve that during a weekend, so technical aspect is nothing
  * Weird/fuzzy contests

What was cool and I liked:

  * Nice mentors, people that literary achieved something in their life. A lot of sharing
  * The event is more or less a stress test, and if you can handle that, that makes you stronger
  * The team is everything, if you can't play with other kids, don't go there, you will waste people's time
  * Nice networking
  * Good chances to find mates that might help you in future

[![Ink2Digital][3]][4]{:.alignright}

About what we did there. We built [Ink2Digital][4],
[Ioana's][5] idea. And from a drawn piece of paper, at the end of 5pm Sunday,
we were live in production with a prototype built by [Mircea][6] and me, and
designed by [Titel][7] (these guys are awesome). Girls (Ioana + Ada) took care
of pitching and presentation, while [Robbert (Cluj Cowork)][8] hosted and
mentored us from every other aspect that was required (most of our team was
from Sibiu :P). We used Rails, [Resque][9] and [Bootstrap][10], and everything
sits on [an EC2 instance][11] (application) with an [RDS database][12]. About
the idea,

> Ink2Digital was built to solve the problem of books that will never be
published again, and instead of storing those on publishers servers, you can
upload those on our service and get a revenue from our subscribed readers.

Yeah, that simple: Last.fm for readers! Ending this, I can say: this was fun

   [1]: http://stas.nerd.ro/read/902
   [2]: http://cluj.startupweekend.org/
   [3]: https://fbcdn-profile-a.akamaihd.net/hprofile-ak-snc4/174571_174797459300654_1404844206_n.jpg
   [4]: http://ink2digital.com/
   [5]: https://www.facebook.com/profile.php?id=100000836478550
   [6]: http://mircea.me/
   [7]: https://twitter.com/#!/titel
   [8]: http://clujcowork.ro/
   [9]: https://github.com/defunkt/resque
   [10]: http://twitter.github.com/bootstrap/
   [11]: http://aws.amazon.com/ec2/
   [12]: http://aws.amazon.com/rds/

