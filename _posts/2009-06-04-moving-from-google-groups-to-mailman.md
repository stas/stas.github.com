---
layout: post
title: Moving from Google Groups to Mailman
tags:
- Open Source
- Planet
- Software
---

Recently we moved our mailing list from [Google Groups][1] to [Mailman][2] Free Software mailing list manager. The decision was taken cause we need more control on our mailing list and Google Groups is proprietary software. [Setting up mailman][3] wasn't that hard. The hardest part is to get our whole archive transfered from Google Groups to our Mailman server. The point was to get an mbox of all our messages, which will later be copied above the new .mbox file in Mailman. To get the messages, I used an IMAP server which has a directory with the stored threads from our mailing list, and the [getmail tool][4].

First install getmail: `apt-get install getmail4`

Create the getmail rc file in `~/.getmail/getmail.rc`:

~~~
[retriever]
type = SimpleIMAPSSLRetriever
server = imap.gmail.com
username = username
password = password
mailboxes = ("MAILING-LIST-DIRECTORY-NAME",)
[destination]
type = Mboxrd
path = ~/your-mailing-list-name.mbox
~~~

Create the mbox file: `touch ~/your-mailing-list-name.mbox `

Then run the getmail tool: `getmail -r ~/.getmail/getmail.rc`

The resulted mbox file should be copied to your Mailman server (on Debian/Ubuntu I believe it's in `/var/lib/mailman/archives/private/` ), after it just run `mmarc` with `--wipe`. `mmarch --wipe your-mailing-list-name /var/lib/mailman/archives/private/your-mailing-list-name.mbox`

That's all folks, now your archives should be totally transfered.

   [1]: http://groups.google.com
   [2]: http://list.org
   [3]: https://help.ubuntu.com/community/Mailman
   [4]: http://pyropus.ca/software/getmail/

