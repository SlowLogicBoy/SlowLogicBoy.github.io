---
title:  "Thrustmaster t3pa pedal Load Cell Mod"
categories:
  - Electronics
  - Sim Racing
tags:
  - Electronics
  - Sim Racing
  - Thrustmaster
  - t3pa
---

Based on some forum posts, blogs and this [Youtube Video](https://www.youtube.com/watch?v=KIldeuIU-jM) I made a load cell pedal mod.

However all these guides suggested to use this [load cell amplifier](http://www.leobodnar.com/shop/index.php?main_page=product_info&cPath=73&products_id=199&zenid=c003583f4bff2b00c1ae8caae99149e4) and it was too expensive for me and I haven't found any guides with anything cheaper, so I thought I will experiment with cheaper basic op-amps (because I think lc amplifier mentioned before is basically an op-amp).

Of course those guides do not require any soldering, well I had to do quite a bit, and required some other tools, that I already had because of my electronics hobby.

I will mostly cover how to connect AD623 op-amp instead of Load Cell amplifier, everything else can be found in other guides.

Parts I used:

- [20kg Load Cell (only)](https://www.aliexpress.com/item/1005002395846445.html) 
- ~~[AD623 op-amp](https://www.aliexpress.com/item/32834035813.html)~~ Out of Stock
- [AD623 op-amp](https://www.aliexpress.com/item/32817544729.html)
- Some wires.
- 3pin male connector.

Connecting load cell to op-amp:
- Red wire -> VS+
- Green -> IN+
- White -> IN-
- Black -> GND

You might need to change Green to IN- and White to IN+ because not all loadcells are the same.

Connecting to t3pa (you have to confirm these yourself with multimeter):
- GND -> Connector Red wire
- OUT -> Yellow wire
- VS+ -> Black wire

for some reason my t3pa didn't follow wire coloring. So check yours with multimeter before plugging it in.

This is connector I made:

![Connector Image](/assets/images/t3pa-loadcell/Connector.PNG)

So Red -> v3.3, Black -> GND, and Yellow -> OUT, however Thrustmasters connector to potentiometer was Black -> v3.3, Yellow -> Sense/Out, and RED -> GND in my case, again check with multimeter.

Also there are REF and GND pads on op-amp solder them together.
You also need to connect GND to VS-, but since we connected REF with GND we can just solder VS- and REF pins together:

![AD623 Underside Image](/assets/images/t3pa-loadcell/Soldered%20AD623%20Underside.PNG)
![AD623 Image](/assets/images/t3pa-loadcell/Soldered%20AD623.PNG)

Last thing is to connect load cell to t3pa open Thrustmaster control panel and adjust potentiometer on op-amp until it reads load cell correctly from 0 to 100%.

Result:

![Mounted Load Cell](/assets/images/t3pa-loadcell/LoadCellMount.PNG)

Update:
Eliminated Deadzone and increased travel by adding some nuts:

![Mounted Load Cell Update](/assets/images/t3pa-loadcell/Result_Eliminated_DeadZone.jpg)
