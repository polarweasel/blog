---
title: Bye, Wordpress
date: 2025-01-09T13:00:00-08:00
author: awball
draft: false
description: ""
showFullContent: false
readingTime: false
hideComments: true
url: /2025/01/09/bye-wordpress/
---

For reasons of Matt Mullenweg's recent terrible behaviour, I wanted to get rid of Wordpress.

The site is now running on Hugo, the static site generator. I exported the Wordpress site using [wp2hugo](https://github.com/ashishb/wp2hugo), and did some minor cleanup on the resulting files.

Source files are hosted on GitHub, and pushing a change to the repository causes the site to get rebuilt and synced up with the web host. Implementation details are the same as [on my main site](https://github.com/polarweasel/sewing/blob/main/README.md).
