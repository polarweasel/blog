---
author: awball
category:
  - link
date: "2007-07-14T01:06:17+00:00"
guid: http://blog.polarweasel.org/post/5720296
title: Fighting spam with pf
url: /2007/07/14/5720296/

---
Link: [Fighting spam with pf](http://bsdnews.com/view_story.php3?story_id=6847)

This article will show you how I am using PF (the the Packet Filter from the OpenBSD project) and spamd (also from OpenBSD) to implement greylisting and greatly reduce incoming spam. This solution is completely MTA agnostic. You do not have to make any changes to your existing mail server configuration to use spamd/pf. In fact, you can easily use pf and spamd to guard any SMTP mail server. Yes, even MS Exchange.
