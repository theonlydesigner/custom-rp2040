# week 1: rp2040 dev board & mini hackpad

## project goals
* **Target Specs:** custom RP2040 microcontroller board using the QFN-56 package, 16MB QSPI flash, 12MHz crystal oscillator, USB-C connector with 5.1k CC pull-down resistors, and dual-row breakout headers for all GPIO pins to drive a mini hackpad.
* **Design Philosophy:** build a functional dev board from absolute ground zero using the hack club stasis guide so i finally understand what goes on under the hood of a raspberry pi pico [instead of treating microcontrollers like magic black boxes].
* **Why I'm building this:** week 1 theme is PCB, and i needed a custom board to integrate with an old mini hackpad design i had lying around. also i wanted to suffer through routing 0402 passives and tiny IC pins.

## bill of materials (BOM)

| Part | Quantity | No of items in 1 unit | Price w/o shipping | Price |
| :--- | :---: | :---: | :---: | :---: |
| 1uF Capacitor | 1 | 2 | 0.1 | 0.1 |
| 0.1uF Capacitor | 1 | 11 | 0.1 | 0.1 |
| 10uF Capacitor | 1 | 2 | 0.1 | 0.1 |
| 33pF Capacitor | 1 | 2 | 0.2 | 0.2 |
| USB_C_Receptacle_USB2.0_14P | 1 | 1 | 0.3 | 0.3 |
| Conn_01x20 | 1 | 2 | 0.6 | 0.6 |
| Conn_01x03 | 1 | 1 | 0.16 | 0.16 |
| 5.1K Resistor | 1 | 2 | 0.1 | 0.1 |
| 27 Resistor | 1 | 2 | 0.1 | 0.1 |
| 1K Resistor | 1 | 2 | 0.1 | 0.1 |
| 10K Resistor | 1 | 1 | 0.1 | 0.1 |
| SW_Push | 1 | 1 | 0.11 | 0.11 |
| RP2040 Chip | 1 | 1 | 0.84 | 1.3 |
| MCP1700x-330xxTT | 1 | 1 | 0.5 | 0.5 |
| W25Q128JVS | 1 | 1 | 5.02 | 5.02 |
| 12MHz Crystal | 1 | 1 | 0.39 | 0.39 |
| PCB w/ Stencil | 1 | 1 | 6 | 10 |
| Solder Paste | 1 | 1 | 2.3 | 3 |
| Tweezers | 1 | 1 | 1.8 | 1.8 |
| Solder Iron and stuff related to that | 1 | 1 | 3.2 | 3.2 |


## dev journal - part 6: left-side GPIO routing (the lost footage)
* **Time spent:** 2 hours
* **Recorded on lapse:** no [because my brain shut off and i forgot to hit record]

this was easily the most painful part of the entire week. of course, this is the exact 2-hour block where i forgot to start the lapse recording, so you'll just have to take my word for it that i was working and not staring blankly at a wall.

since this was my first time designing an RP2040 board from scratch, trying to connect the RP2040 pins to the left-side GPIO headers turned into a complete trace-routing nightmare. i was following the hack club stasis guide (`stasis.hackclub.com/starter-projects/devboard`), but making clean connections for GPIO0 through GPIO15 without crossing traces or creating illegal angles felt like playing a high-stakes game of snake. 

i had to pause every 5 minutes to watch multiple youtube tutorials on KiCad trace routing, net classes, and how to use vias without making the PCB look like cheese. i kept triggering Design Rule Check (DRC) errors because my traces were either too close to the ground plane or running over decoupling capacitors. after two hours of tearing my hair out, re-routing lines three times over, and wrestling with via placements, the left side is finally connected and fully routed. 

## visual showcase

![complete pcb layout preview](images/preview.png)
*(the fully routed RP2040 dev board before sending it off to the fab house)*