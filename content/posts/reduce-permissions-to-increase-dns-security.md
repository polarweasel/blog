---
author: awball
category:
  - link
date: "2007-07-27T16:57:06+00:00"
guid: http://blog.polarweasel.org/post/6958841
title: Reduce permissions to increase DNS security
url: /2007/07/27/6958841/

---
Link: [Reduce permissions to increase DNS security](http://bsdnews.com/view_story.php3?story_id=6999)

Every server process you run on your system provides another potential point of compromise. That's why it's so often recommended that you turn off unnecessary services on Windows machines and deactivate unneeded daemons on UNIX operating systems.

You can't simply turn off all services and daemons, however, as the ability to use your operating system environment would be severely crippled if you did. As a result, it becomes necessary to attempt to secure the operation of the server processes you need.

An example of such a case is a UNIX or Linux DNS server. Just like any other server software, the BIND server daemon named process may occasionally be subject to security vulnerabilities that may allow a malicious security cracker to gain unauthorized access to your system. It is thus important to configure your system to minimize the damage a security cracker can do when he or she exploits such a vulnerability.
