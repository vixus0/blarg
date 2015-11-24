Random Linux Fix #1
@date: 24-11-2015 13.15
@tags: linux arch kms intel xorg

Some flavour of Linux has been my operating system of choice for well over a decade now. I run it on my aging Thinkpad X60 and a homemade desktop. I haven't had Windows running on a personal machine since my [favourite game](http://www.teamfortress.com) was ported to Linux. For the last 5 years the distribution I've grown attached to is [Arch](https://archlinux.org). It's clean, simple(ish) to work with and doesn't hold your hand. Without a doubt I've learned a lot more about how Linux works than if I'd stuck with something like Ubuntu. In fact I've probably learned more than I want to.

Arch is "bleeding-edge", meaning frequent updates which should mean stuff breaks more often. Actually I haven't really had stuff go wrong much more than on Ubuntu/Debian and the payoff is more up-to-date software. Every so often though, I'll run into some horrendous problem that offers no clues as to what went wrong. When this happens it's time to head on over to Google and start angrily mashing keys.

Last night, I rebooted my laptop (I rarely ever shut it down, since suspend/resume works perfectly ...for now) and found that X just wouldn't get going. After the boot messages, all I'd see onscreen was this:

    _
    
    
    
    
    
    

The cursor wasn't blinking and I couldn't switch ttys with Ctrl+F#. Hitting the power button wouldn't shut down normally. This had happened a couple of times previously and I blamed LightDM for it. It was a rare occurrence and never reproducible. I had added the `logind-check-graphical=true` line to `lightdm.conf` and all seemed well. Until last night. I kept power-cycling the poor thing and nothing worked. I continued staring into the inky blackness of Linux's soul. After stress-Googling for half an hour or so I gave up and went to bed. But I did find Florian Berger's [post][fb] on this very issue.

Bullet point #5 caught my eye because I had seen it mentioned elsewhere. It's also mentioned on the Arch Wiki [here][aw] though not as a fix to my problem. Basically, add the following kernel parameter to your boot options:

    video=SVIDEO-1:d

Here, SVIDEO-1 refers to some display out port. I don't even think my laptop has one of those. It only has a VGA out. Either way, this flag disables it I guess. I found an interesting [bug report][bug] that involves the same graphics chip and fix. Worryingly the bug was reported fixed in kernel 3.8 and I'm now running 4.2. So clearly not fixed. Maybe I have to file my own bug report...

So though I don't really know what the problem was, it works... for now.

[fb]: http://florian-berger.de/en/articles/i915-black-screen-on-boot-issue/

[aw]: https://wiki.archlinux.org/index.php/Intel_graphics#KMS_Issue:_console_is_limited_to_small_area "Arch Wiki: Intel graphics"

[bug]: https://bugs.debian.org/cgi-bin/bugreport.cgi?bug=697741 "Debian bug #697741"
