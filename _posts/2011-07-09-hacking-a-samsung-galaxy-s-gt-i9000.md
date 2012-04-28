---
layout: post
title: Hacking a Samsung Galaxy S (GT-I9000)
tags:
- Linux
- Mint rubbing
- Planet
- Thoughts
---

Ok, so I have a friend that calls me today. He owns a Galaxy S, and his phone is totally locked, because he was using a visible pattern lock and some noob was trying to guess that pattern until the phone locked away.

The problem would not be a problem if he was using Google's service for backing up the data, but he was not using it. So he calls me and asks if I can help him recover his phone, ideally preserving the data on it.

Challenge accepted!

First I rooted the device, that can be done easy by downloading [SuperOneClick][1] (search for exploit folder, where you will find the binary to be uploaded and executed). Later I installed `su` and `busybox`, to get some tools available.

Samsung guys are smart, if you boot into recovery, you will only have access to the system file-system, and not anything else. What I was looking for, was the place where Android stores the settings values, later, I found that what I was looking is an sqlite database, but we are getting there soon.

On a standard Android, the settings database we are interested in, should be available in your `/data/data/com.android.providers.settings`, but that's not the case with Galaxy S, the Samsung engineers, created a dedicated partition for settings/contacts/etc databases, so all you are going to find using the standard path is a dummy place-holder. To get access to the real database, you will need to find the name of the device that has to be mounted.

The OS `init.rc` and `recovery.rc` files are the files that are "poked" when booting into normal and recovery modes. Knowing that recovery mode doesn't help me much, I consulted `init.rc`. The device name was `/dev/block/stl10`. If you mount it, inside databases folder, you will find the real settings provider database.

Download that file (`settings.db`), and change the value of key `lockscreen.lockedoutpermanently` from `1` to `0` using `sqlite3` tool. Once done, upload the file back to the phone. Replace the old file, `chmod` it to `0666` and `chown` it to the same `uid` and `gid` as it's parent directory.

Reboot the phone! Done!

In the end, I can say that it took me some hours, and saved a complete Android reinstall, with a big probability of loosing all the data. Anyway, it was nice playing with the device.


   [1]: http://shortfuse.org/?page_id=2

