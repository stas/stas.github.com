---
layout: post
title: Migrating ZFS pools from FreeBSD to (Open)Solaris
tags:
- OpenSolaris
- Software
- Thoughts
---

I had some issues with the pools created on FreeBSD (7.2-8) with ZFS (version 6 to 13) when I tried migrating those to (Open)Solaris/Nexenta. Something like this:

~~~
# zpool import -f
pool: tank
id: 2794438138141825953
state: UNAVAIL
status: One or more devices contains corrupted data.
action: The pool cannot be imported due to damaged devices or data.
see: http://www.sun.com/msg/ZFS-8000-5E
config:
tank UNAVAIL insufficient replicas
raidz1 UNAVAIL corrupted data
c0t1d0p0 ONLINE
c0t2d0s8 UNAVAIL corrupted data
c0t3d0s2 ONLINE
# zpool import -f tank
cannot import 'tank': no such pool or dataset
~~~

The point is that `c0t2d0s8` is actually a slice device along with `c0t3d0s2` and the only real device is actually `c0t1d0p0`.
So (re)moving, the slice devices from `/dev/rdsk/` should leave anything but real devices (which should actually represent the real raidz arrays).

Something like this should help:

~~~
mkdir /tmp/bad_devs
cd /tmp/bad_devs
for i in /dev/rdsk/c7t[0123456789]d0s*; do mv $i ./; done
zpool import -f tank
zpool upgrade -V 14 tank
~~~

Still, I can't explain how it came up like this in FreeBSD. :(
