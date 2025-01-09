---
author: awball
category:
  - regular
date: "2010-10-27T21:37:00+00:00"
guid: http://blog.polarweasel.org/post/1417716917
title: SSH environment variables
url: /2010/10/27/1417716917/

---
Just in case you want to know what IP address an SSH client is coming from, or what address they used to log in (such as internal vs. external addresses), the ssh daemon puts a bit of useful stuff in environment variables for you. `$SSH_CLIENT` and `$SSH_CONNECTION` are the most useful.
