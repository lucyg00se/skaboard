# Skaboard v3
This repository contains all the relevant files and instructions for making the Skaboard, a split stenographic keyboard.

There are a few changes I would still like to make that may come in the form of a version 4, but for now I'd just like to get a version of this made available.

![Skaboard v3](https://raw.githubusercontent.com/lucyg00se/skaboard/refs/heads/main/images/skaboard.JPG)

**This page is currently a work in progress**

---

## What's a Skaboard?
The Skaboard is my attempt to make a hobbyist stenographic keyboard that suits my own needs. I wrote a short blog post about this a while ago [here](https://www.lucydeacon.ie/my-keyboard/). It's my best-of-both-worlds solution between the [Polyglot](https://stenokeyboards.com/products/polyglot-keyboard) and the [Georgi](http://thedarnedestthing.com/georgi%27ous).
## How do I make one?
### Ingredients
For the regular ***Skaboard***, you will need:
- Baseplate PCB x2
- Top cover PCB x4
- Kailh low profile hotswap sockets x30
- Kailh low profile keyswitches x30
- Kailh low profile keycaps x30
- 16 (2x8) pin 2.54mm pitch IDC sockets x2
- 16 (2x8) pin 2.54mm pitch IDC cable x1
- Raspberry Pi Pico x1
- Raspberry Pi Pico headers x2
- Regular 2M screws x8
- ⌀7mm wide head 2M screws x8
- 5mm 2M standoffs x8
- ⌀7mm silicon feet x8
- 1mm foam sheet
- USB-C right angle connector (optional but.)

![Photo of the items needed to make a Skaboard](https://raw.githubusercontent.com/lucyg00se/skaboard/refs/heads/main/images/skaboardknoll.JPG)

For the ***Skaboard Lite***, you will need:
- Lite Baseplate PCB x2
- Kailh low profile hotswap sockets x30
- Kailh low profile keyswitches x30
- Kailh low profile keycaps x30
- 16 pin IDC sockets x2
- 16 pin IDC cable x1
- Raspberry Pi Pico x1
- Raspberry Pi Pico headers x2
- Silicon feet x8

![Photo of the items needed to make a Skaboard Lite](https://raw.githubusercontent.com/lucyg00se/skaboard/refs/heads/main/images/skaboardliteknoll.JPG)

You will also need a few tools:
- Soldering iron and solder
- 2M screwdriver
- Exacto knife or equivalent
- Wire cutter
- Superglue or similar

### Where to get the ingredients
The Gerber files for the PCBs are included in the GitHub. You can upload these to [JLCPCB](https://jlcpcb.com/), [PCBWay](https://www.pcbway.com/), or another PCB manufacturer to get them made. I got mine made by JLCPCB.

![Example of getting PCB made through JLCPCB](https://raw.githubusercontent.com/lucyg00se/skaboard/refs/heads/main/images/jlcpcb.jpg)

I got the rest of my parts from [The Pi Hut](https://thepihut.com/) and [AliExpress](https://www.aliexpress.com/).

### Recipe
1. Preheat oven to 200C. (this is a joke)
2. Cut two bottom pads from the 1mm foam and puncturing holes for the screws by using one of the PCBs as a template.

![Cutting the foam using the base plate as a template](https://raw.githubusercontent.com/lucyg00se/skaboard/refs/heads/main/images/cutfoam.JPG)

3. Glue the foam pads to the 'top' covers (this will function as the bottom of the case)

![The bottom of the case](https://raw.githubusercontent.com/lucyg00se/skaboard/refs/heads/main/images/foambottom.JPG)

4. Solder the Kailh sockets and the IDC sockets onto the PCBs

![The underside of the baseplate PCB after soldering](https://raw.githubusercontent.com/lucyg00se/skaboard/refs/heads/main/images/baseplateunderside.JPG)

5. Solder the Pico ***upside-down*** onto the ***right-hand board*** using the headers. The USB port on the Pico will make it ride up slightly and not sit flush - this is normal.

![The Pico riding up a little](https://raw.githubusercontent.com/lucyg00se/skaboard/refs/heads/main/images/picocloseup.JPG)

6. Snip the ends of the header pins flush with the PCB and the Pico.  This is the most finicky step, and you will probably not get it perfectly flush, but this is fine.

![Flush pins close-up](https://raw.githubusercontent.com/lucyg00se/skaboard/refs/heads/main/images/flushpins.JPG)

7. At this point, you may wish to attach the keyswitches and keycaps and flash your firmware.
8. Assemble the case. From the top down, the stack is:
   - Regular 2M screws
   - Top cover PCB
   - 5mm standoffs
   - Baseplate PCB
   - Top cover PCB again
   - Foam bottom 
   - ⌀7mm wide head 2M screws
   - ⌀7mm silicon feet (note that the silicon feet sit directly on the wide head screws)

![Exploded view of case](https://raw.githubusercontent.com/lucyg00se/skaboard/refs/heads/main/images/explodedview.JPG)

![Screw assembly seen from the side-on](https://raw.githubusercontent.com/lucyg00se/skaboard/refs/heads/main/images/screwstackfeet.JPG)

Then join the two sides with the IDC cable and you're done! You may also want to use a USB-C right angle adapter to make plugging in the keyboard easier.

For the Skaboard Lite, ignore steps 2, 3 and 8. Then directly attach the silicon feet to the PCB.

### Firmware
To access the Pico for flashing the firmware, you will need to unscrew the bottom section of the case. The underside of the baseplate PCB has small labeled holes for the <ins>U</ins>ser, <ins>R</ins>eset and <ins>B</ins>oot buttons.

To flash the firmware, you can plug in the Pico while holding down the Boot button. Alternatively, while already plugged in: hold Reset, hold Boot, release Reset, release Boot.

Included in this repository is a basic firmware that lets the keyboard connect to [Plover](https://opensteno.org/plover/) using Gemini PR.

Also included is a key map for building a firmware with [Javelin](https://github.com/jthlim/javelin-steno).
