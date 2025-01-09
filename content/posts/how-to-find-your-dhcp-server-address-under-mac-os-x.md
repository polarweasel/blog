---
author: awball
category:
  - link
date: "2009-08-08T17:30:39+00:00"
guid: http://blog.polarweasel.org/post/158646166
title: How to find your DHCP Server Address under Mac OS X
url: /2009/08/08/158646166/

---
Link: [How to find your DHCP Server Address under Mac OS X](http://automatica.com.au/blog/2009/07/how-to-find-your-dhcp-server-address-under-mac-os-x/)

From “Automatica Blog â€“ Specialist Apple Mac support for creative professionals, Melbourne Australia”, edited slightly for clarity and grammar:

Use this command to determine the IP address of the DHCP server your Mac is currently using:

```
ipconfig getoption en0 server_identifier
```

You can also do more with ipconfig, such as determine the router address for an interface:

```
ipconfig getoption en0 router
```
