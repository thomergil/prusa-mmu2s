# Getting that #^@%# Prusa MMU2S to work smoothly

 As noted by [Tim Brodin](https://broddin.be/2021/07/13/troubleshooting-the-prusa-mmu2s/), the Prusa MMU2S can be infuriating and bring a grown-up to tears:

> I’m a grown-up man, but **this machine brought me to tears**. It was **infuriating** to get going. I can’t recall how often I’ve unscrewed everything,  fastened bolts, and loosened them again. I could not get this upgrade to print anything. Every filament would get stuck, would not load, or would fail to unload. I got really close to the point of just **reverting everything** and going back to my stock i3 MK3S+.

Tim provides [excellent suggestions](https://broddin.be/2021/07/13/troubleshooting-the-prusa-mmu2s/), some of which I repeat below. (Though I did not have to change too many PrusaSlicer settings.)

I report here what eventually led to success after three weeks of tinkering. With many thanks to my brother, Jonathan, various Reddit discussions, Prusa forum discussions, and Prusa support.

#### The MMU2S stops/crashes, blinking all LEDs red/green

This, too, is reported [by others](https://forum.prusa3d.com/forum/original-prusa-i3-mmu2s-mmu2-general-discussion-announcements-and-releases/mmu2s-crashes-constantly/) (and [here](https://www.reddit.com/r/prusa3d/comments/gf6065/mmu2s_keeps_crashing/)), but none of the solutions discussed there worked for me. I reached out to Prusa support, and they gave the mind-boggling solution:

> Unplug and replug the signal and power cable for the MMU. Both on the MMU itself and the mainboard. 
>
> If that does not help, **move the power cables on the board one pair to the right** so they're connected to the middle two terminal screw connectors.

### Learn to understand what the MMU2S buttons do

The [MMU2S handbook](https://help.prusa3d.com/downloads/mmu2/handbook) inexplicably does **not** explain what the buttons do. This [handy cheat sheet](https://forum.prusa3d.com/wp-content/uploads/2022/01/Cheat-Sheet.pdf) (as discussed [in this forum thread](https://forum.prusa3d.com/forum/original-prusa-i3-mmu2s-mmu2-hardware-firmware-and-software-help/mmu2s-what-do-the-buttons-do/)) explains it. Most importantly: the middle button tries to see if what you did solved the problem; the right button then proceeds the print.

### Don't overtighten the idler screws on the MMU2S

Screws should be tight, right? No, not the idler screws. As noted on the [MMU2S Setup and Inspection](https://help.prusa3d.com/ja/article/mmu2s-setup-and-inspection_2233) page, the tops of the MMU2S idler screws need to be flush with the cover.

### Don't overtighten the idler screws on the printer

As noted on the [Idler Screw Tension](https://help.prusa3d.com/article/idler-screw-tension_177367) page, this idler screw should also be flush or even protrude 0.5-1mm. If you tighten it, the gears will grind away at the filament, and the unload will fail.

### Replace the back of the MMU2S to use M10 PTFE holders

As suggested [in a Reddit thread](https://www.reddit.com/r/prusa3d/comments/u00mpf/mmu2s_is_pretty_great_with_some_easy_fixes/), you should replace the back of the MMU2S with one that [uses M10 PTFE holders](https://www.printables.com/model/6605-prusa-mmu2-ptfe-holder-m10-passthrough-adapter).

### Use 4mm OD x 3mm ID PTFE tubes

The standard 2mm ID x 3mm OD PTFE tubes provide too much resistance. Use [3mm ID x 4mm OD PTFE Tubes](https://www.amazon.com/dp/B07B8CT1YH/ref=twister_B07CXQKMVD?_encoding=UTF8&psc=1). If you really want to go out of your way, widen the opening using a [hole puncher](https://www.amazon.com/gp/product/B01EIH573K/ref=ppx_yo_dt_b_asin_title_o00_s00?ie=UTF8&psc=1). Make sure to clean up the plastic shards, or they'll end up in your hotend and clog it.

### Use a good, low-resistance filament buffer

There are many excellent and popular filament buffer designs out there, such as the [Universal Auto-Rewind Spool Holder](https://www.thingiverse.com/thing:3338467) and the [MMU Slot buffer](https://www.printables.com/model/30811-mmu-slot-buffer). I opted, instead, to remix and improve the [5 Wheel Buffer for MMU2](https://www.printables.com/model/4670-5-wheel-buffer-for-mmu2), solving a few problems it kept having.

 My own [Better 5-Wheel Filament Buffer](https://www.printables.com/model/394402-a-better-5-wheel-filament-buffer/comments) design uses [M10 PTFE holders](https://www.amazon.com/gp/product/B01KHN1HWY/ref=ppx_yo_dt_b_asin_title_o08_s00?ie=UTF8&psc=1) and 508 ball bearings.

### If you're going to upgrade the firmware, don't do it via OctoPrint

The latest firmware is [provided by Prusa](https://help.prusa3d.com/downloads/mmu2/firmware). Perform the upgrade by [following these instructions](https://help.prusa3d.com/article/firmware-updating-mmu2s_155118), connecting the USB cable to the side of the MMU2S. Do **not** use OctoPrint for this.

### You may want to consider factory resetting the MMU2S

I did it a dozen times. I'm not sure it helped anything, but [here are instructions to factory reset the MMU2S](https://help.prusa3d.com/article/factory-reset-mmu2s_1920).

### Print it hot

PrusaSlicer lowers the default temperature of PLA (from 215º C to 205º C). Don't. Print it at whatever temperature works best for you on a non-MMU printer.

### Perform the nylock upgrade

Really. Do it. It's worth it. It's finicky and annoying. [Follow the Nylock Mod upgrade instructions](https://www.reddit.com/r/prusa3d/comments/bp440f/full_guide_to_doing_nylock_mod_if_you_havent_you/), which also refer to a [YouTube video showing the Nylock Mod upgrade](https://www.youtube.com/watch?v=hDv73AdiBqM). Another [YouTube video shows the same upgrade](https://www.youtube.com/watch?v=v3Ih51AjLmE). It's annoying to have to do this, but it made half my problems disappear.