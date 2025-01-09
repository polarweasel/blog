---
author: awball
category:
  - regular
date: "2016-03-01T23:49:35+00:00"
guid: https://blog.polarweasel.org/?p=2607083002
title: Moving to HTTPS-only
url: /2016/03/01/moving-to-https-only/

---
All the web stuff at polarweasel.org should be encrypted-only now. In other words, when you visit a page on the blog, or on the [main site](https://polarweasel.org/), you should see the little lock-icon thingy — or whatever your browser uses — in the address bar.

For my own future reference, and maybe yours too, here's what I did.

These sites are hosted on Dreamhost, which makes it really easy (two clicks) to get a [Let's Encrypt](https://letsencrypt.org/) certificate. So I did that for the various sites.

Then, I forced the web server (Apache, in this case) to redirect all non-encrypted requests to the encrypted site instead. To do that, I added this sort of thing to each site's `.htaccess` file:

```sh
# Force all connections to go over SSL
RewriteEngine On
RewriteCond %{SERVER_PORT} 80
RewriteRule ^(.*)$ https://sitename.org/$1 [R,L]
```

(Writing it that way, with no conditions, should guarantee a 500 error if `mod_rewrite` is disabled for some reason.)

That's all you need to do for a static site. For the Wordpress sites, you need to do a couple more things: set the site URLs in the Settings - General menu to **https** instead of **http**, and add the following to the site's `wp-config.php` file, right above the "stop editing here" line:

```php
define('FORCE_SSL', true);
define('FORCE_SSL_ADMIN', true);
```

And that's it. More or less.

**Note**: If any of your pages have hard-coded (http://something) links in them, including calls to CSS stylesheets or Javascript, instead of relative (/something) links, you'll need to update those. Relative links are your friends; use them.
