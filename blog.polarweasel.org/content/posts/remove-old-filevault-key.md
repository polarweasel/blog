---
author: awball
date: 2025-02-25
title: Removing an ancient FileVault key
url: /2025/02/25/filevault-key-trouble/
---

When I tried to enable FileVault on a new machine today, I got a message I didn't like: `A recovery key has been set by your company, school, or institution.`

Turns out, it was a leftover from many laptop migrations ago. The clue was in an [Apple support forum post](https://discussions.apple.com/thread/253479157?answerId=256769041022&sortBy=rank#256769041022).

I deleted the following two files, dated 2007, then rebooted, and the problem was gone:

* `/Library/Keychains/FileVaultMaster.cer`
* `/Library/Keychains/FileVaultMaster.keychain`

Note that this is very unlikely to work on a machine that actually _does_ have an institutional recovery key set, but it works great when you have migration-cruft messing things up.
