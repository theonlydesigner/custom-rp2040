---
title: "RP2040 Custom Devboard"
author: "Pratham Rupera aka theonlydesigner"
description: "This is a custom devboard which is used in a hackpad."
created_at: "2026-10-01"
---

PS: Please ignore the dates as the timeline might be weird. This is because this project was initially meant for Half Life but I did not ship there. I have Timelapses for 85% of my work which i'll link instead of the images.

# October 1: Getting the KiCad ready
i kicked off the design process today by diving straight into the schematic editor on kicad to lay down the absolute foundation of the board. i placed the core rp2040 chip along with essential support components like the ldo voltage regulator and the w25q128 flash memory. mapping out the power pins and assign gpio lines to their corresponding nets took a while because i wanted to make sure i did not mix up any crucial connections [my schematic looked like a chaotic spiderweb by the end of it, but every pin had its rightful place].

[Timelapse](https://lapse.hackclub.com/timelapse/koFGrANDHxOM)

**Total time spent: 0.8hrs**

# October 1(Part 2): Working on the Schematic
this session was all about making sure the board can actually talk to external hardware and modules. i selected and placed the dual-row header connectors for all the breakout pins and spent a good chunk of time double-checking physical pitch dimensions. lining up the connectors cleanly while making sure the ground, power and gpio lines matched my planned hackpad matrix was tricky because the grid snap kept jumping around [getting header pins perfectly parallel is way more frustrating than it has any right to be].

[Timelapse](https://lapse.hackclub.com/timelapse/AStz1b4Fhh6p)

**Total time spent: 0.25hrs**

# October 2: Fixing labels
i opened up the project today only to realize i had made a complete mess of my net labels and misassigned a bunch of critical gpio pins. i spent the entire two hours carefully tracing each wire back to the rp2040 chip, deleting invalid connections and re-labeling every single net to avoid subtle bugs down the line. it was tedious work, but fixing these silly mistakes early in the schematic saved me from total disaster during routing [nothing brings you back to reality faster than auditing your own broken logic].

[Timelapse](https://lapse.hackclub.com/timelapse/vmYe6KXH--Wi)

**Total time spent: 0.23hrs**

# October 3: Finding the right parts and assigning footprints
today was dedicated to footprint assignment which is basically matching every virtual component to its real-world physical package. i spent time sifting through footprint libraries to find the precise 0402 models for all my passive resistors and capacitors as well as the exact qfn-56 footprint for the rp2040. double-checking land patterns and pad spacings was exhausting, but choosing the wrong package size would mean parts hovering off the board or shorting out [i never want to look at another 0402 capacitor datasheet ever again].

[Timelapse](https://lapse.hackclub.com/timelapse/lolXFzOe4yQK)

**Total time spent: 0.17hrs**
