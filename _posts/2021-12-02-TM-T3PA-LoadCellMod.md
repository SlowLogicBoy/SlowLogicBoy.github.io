---
title:  "Thrustmaster t3pa pedal Load Cell Mod"
categories:
  - Electronics
  - Sim Racing
tags:
  - Electronics
  - Sim Racing
  - Thrustmaster
  - t300
---

Hey,

based on some forum posts, blogs and this [Youtube Video](https://www.youtube.com/watch?v=KIldeuIU-jM) I made a load cell pedal mod.

However all these guides suggested to use this [load cell amplifier](http://www.leobodnar.com/shop/index.php?main_page=product_info&cPath=73&products_id=199&zenid=c003583f4bff2b00c1ae8caae99149e4) and it was too expensive for me and I haven't found any guides with anything cheaper, so I thought I will experiment with cheaper basic op-amps (because I think lc amplifier mentioned before is basically an op-amp).

Of course those guides do not require any soldering, well I had to do quite a bit, and required some other tools, that I already had because of my electronics hobby.

Parts I used:

- [2kg Load Cell (only)](https://www.aliexpress.com/item/1005002395846445.html?spm=a2g0s.9042311.0.0.1c804c4ddFzlKj)
- [AD623 op-amp](https://www.aliexpress.com/item/32834035813.html?spm=a2g0s.9042311.0.0.1c804c4ddFzlKj)
- Some wires
- 3pin male connector (sorry for no link, long time since I bought them)

Connecting load cell to op-amp:
- Red wire -> VS+
- Green -> IN+
- White -> IN-
- Black -> GND

Connecting to t3pa (you have to confirm these yourself):
- GND -> Connector Red wire
- OUT -> Yellow wire
- VS+ -> Black wire

for some reason my t3pa didn't follow wire coloring and black was v3.3 and red was ground, so check yours with multimeter before plugging it in.

Also there are REF and GND pads on op-amp solder them together.
You also need to solder GND to VS- on op-amp itself.
