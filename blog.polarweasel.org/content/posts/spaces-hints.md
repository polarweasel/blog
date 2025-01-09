---
author: awball
category:
  - regular
date: "2007-11-14T20:14:12+00:00"
guid: http://blog.polarweasel.org/post/19449709
title: Spaces hints
url: /2007/11/15/19449709/

---
[Two very useful tricks:](http://www.macosxhints.com/article.php?story=20071025140916203)

_defaults write com.apple.dock workspaces-edge-delay -float 0.5; killall Dock_

(to change the delay, in seconds, between hitting the edge of the screen with a dragged window and moving into the neighboring Screens desktop)

``_defaults write com.apple.dock workspaces-wrap-arrows -boolean NO; killall Dock_

(toggles whether moving to the next Space wraps around when you get to the last Space; i.e., keep going left and you’ll wind up in the rightmost Space)Â
