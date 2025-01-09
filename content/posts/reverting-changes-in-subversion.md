---
author: awball
category:
  - regular
date: "2011-03-03T20:12:56+00:00"
guid: http://blog.polarweasel.org/?p=2607082937
summary: |-
  Let's assume you've got a file (or a directory full of files, doesn't matter) that you've been working on, and have committed it to the repository. Whoops, you've just overwritten something good with something bad. How to get the old one back?

  I thought it would be a variation on the `svn revert` command, but no. It's `svn merge`. This makes sense on some level, but not _a lot_ of sense.
title: Reverting changes in Subversion
url: /2011/03/03/reverting-changes-in-subversion/

---
Let's assume you've got a file (or a directory full of files, doesn't matter) that you've been working on, and have committed it to the repository. Whoops, you've just overwritten something good with something bad. How to get the old one back?

I thought it would be a variation on the `svn revert` command, but no. It's `svn merge`. This makes sense on some level, but not _a lot_ of sense. It's now too late to use `revert` to get back to the previous state, since that only works on local changes, _before_ you commit them. If the repository is at revision 439, and you checked in the right version of the file in revision 401, here's the command you want:

```sh
svn merge -r439:401 ./myfile.txt
```

(Apparently you can also use `HEAD` as the first revision number, but that didn't work for me this morning.)
