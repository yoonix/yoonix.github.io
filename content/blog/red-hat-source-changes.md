---
title: "Red Hat Source Changes"
date: 2023-07-03T12:14:44-07:00
draft: false
---

While everyone is taking the time to crap on Red Hat (for [VERY valid reasons](https://www.redhat.com/en/blog/furthering-evolution-centos-stream)), I thought I'd pitch in my two cents.

First, the latest development (the source distribution changes) doesn't surprise me in the slightest.  I don't know how anyone could've seen the previous 'CentOS Stream' change as anything more than one (or both) of two things:

1. Kill off the clone.  This obviously brings Red Hat financial incentives in the hopes of more sales.
2. A poorly executed attempt to turn the entire CentOS community into a free QA team for RHEL.  The lack of stability, and more importantly functionality breaking changes during point releases (I'm looking at you fapolicyd) make it clear the need for a proper QA system.  The nerve of you trying to coopt an entire community to do this for you, for free (you freeloaders),  without asking.

Killing off the clone has failed dramatically thanks to Rocky Linux and AlmaLinux coming forward to not only build replacement clones but also offer commercial support on these new clones.  This fail is entirely your fault Red Hat (IBM).  YOU took CentOS away.

One of Red Hat's biggest selling points is the support offered along with the 'free software' (which they are openly calling non-paying users of freeloaders now).

Let me just talk about my one and only experience calling Red Hat support 15 years ago, while my RHCE certification was still valid:

Our company was sold a combination of 'Red Hat Cluster Suite' and 'GFS (Global File System)' to replace a horribly performing NFS server my employer was using in production.  I had no say or involvement in the procurement of this software, it was done between the (100% hands off) 'Head Technologist' of the company and Red Hat's sales department.

The pitch was that we can set up RHCS and GFS on a pair of nodes and provide HA NFS services instead of having a single-node point of failure.  After digging through the severely lacking documentation and getting everything running, including the hardware fencing agents.. we would regularly (daily, at least) experience the lock manager daemon on the INACTIVE/STANDBY node crash.. which triggered the fencing, force rebooting the node...

I contacted support to report the issue of the lock manager crashing.  I told them I had an active RHCE certification which (at the time, I don't know now) would automatically skip you past level 1 (have you tried rebooting?) support.

Within ~10 minutes or so of talking to level 2, I was bumped up to an actual engineer that works on this product.  I proceeded to explain what I just said above and this was his response:

"When you pay for support that doesn't mean we're here to train you how to use this software."

After speaking with this engineer's manager, he reluctantly  listened to the problem.  It turned out there was a major bug in the lock manager it was entirely incapable of managing this workload. "You are supposed to run GFS on all of your nodes, not NFS."  Yeah, then this product doesn't meet a single requirement of ours then.

The 'fix' was to MANUALLY DISABLE THE LOCK MANAGER AND START IT BY HAND WHEN THE OTHER SYSTEM CRASHED.  All that time, all that money, to simply replace a poorly performing NFS server with one that I had to manage by hand and we still had no high availability to speak of.

Yeah, this is Red Hat. And this was long before IBM was involved.  I dread calling Red Hat support because I know I'm going to waste time, potentially be insulted, and probably not get the root problem actually addressed.

I may be nearly 20 years late to the party but hello Ubuntu!
