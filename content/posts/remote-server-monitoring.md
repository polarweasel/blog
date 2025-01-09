---
author: awball
category:
  - regular
date: "2011-01-26T05:05:04+00:00"
guid: http://blog.polarweasel.org/?p=2607082928
summary: 'Background: [BES](http://www.bes-rescue.org/) has an exceedingly flaky T1 router, and I''m getting tired of pinging it all the time to see if it''s alive (it is remotely rebootable). Also, I have [Prowl](http://prowl.weks.net/) (normally used for Growl notifications, but has a nice API of its own) installed on my phone.'
title: Remote server monitoring
url: /2011/01/25/remote-server-monitoring/

---
Background: [BES](http://www.bes-rescue.org/) has an exceedingly flaky T1 router, and I'm getting tired of pinging it all the time to see if it's alive (it is remotely rebootable). Also, I have [Prowl](http://prowl.weks.net/) (normally used for Growl notifications, but has a nice API of its own) installed on my phone.
The solution I came up with was a small cron job that runs every hour. In its entirety:

> ```
> #!/bin/bash
> if ! ping -c 10 -t 100 x.x.x.x | grep ' 0% packet loss' >/dev/null 2>&1
> then
>   php -f ~/bin/prowlnotify.php
>   echo BES T1 router has packet loss
> fi
> ```

`prowlnotify.php` is similarly small:

> ```
> <?php
> include('ProwlPHP.php');
> $prowl = new Prowl('API key goes here');
> $prowl->push(array('application'=>'server-ping','event'=>'BES T1 down',
>         'description'=>'BES router down','priority'=>1),true);
> ?>
> ```

Note that Prowl priorities run from -2 (very low) to 2 (emergency). I have Prowl set to stay quiet overnight, except for emergency-level notifications. Since it mostly just affects members' web surfing, the router going down doesn't rank as an actual emergency, but during the day, Prowl will make some noise to let me know about it.

All you need to make it work is a free Prowl account, the $3 [Prowl app](http://itunes.apple.com/app/prowl-growl-client/id320876271?mt=8), and a server on which to run the cron job.

(And yes, I realize that replacing the router would be good, and I'm waiting to hear back from the ISP's support staff. But I think it's safe to assume the replacement will be a POS, too...)
