---
author: awball
category:
  - regular
date: "2012-08-19T21:28:07+00:00"
guid: http://blog.polarweasel.org/?p=2607082991
title: How to un-break HP printing on Mountain Lion (and Lion)
url: /2012/08/19/how-to-un-break-hp-printing-on-mountain-lion/

---
**UPDATE** A subsequent update fixed the problem. Or at least didn't _re-create_ the problem.

HP software update 2.10 came out recently for Lion and Mountain Lion, and causes apps to crash when you try to print. If this is happening to you, here's what to do about it.

Delete this:

```
/Library/Printers/hp/PDEs/hpPostScriptPDE.plugin
```

(You'll need to provide authorization, either with `sudo` or by giving an administrator password to Finder.)

There is no step 2.
