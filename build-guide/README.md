# Build Guide
This guide is based off the Basketweave guide by null-ll.  The components are layed out in a similar fashion.

## Required Components
You will need the following tools and components to build the keyboard (not included in the kit):
- Soldering iron and solder
- Flush side cutters
- No-clean flux
- 5 PCB mount 2u stabilizers
- USB Type C cable
- 1.5mm allen wrentch (black screws, knob screw)
- 1.27mm allen wrentch (silver screws)

## Components
| Ref     | Component              | Qty | Notes |
| ---     | ---------              | --- | ----- |
| C1, C2  | 22pF Capacitor         | 2   | [Link](https://www.mouser.com/ProductDetail/81-RCE5C2A220J0A2H3B)
| C3, C4  | 0.1uF Capacitor        | 2   | [Link](https://www.mouser.com/ProductDetail/81-RDER71H104K0M1H3A)
| C5      | 4.7uF Capacitor        | 1   | [Link](https://www.mouser.com/ProductDetail/Nichicon/UMT1H4R7MDD?qs=jeFazJX0ZRzElcQ8UcwUoQ%3D%3D)
| D1-92   | 1n4148 Diode           | 92  | [Link](https://www.mouser.com/ProductDetail/512-1N4148TR)
| D93, D94| 3.6V Zener Diode       | 2   | [Link](https://www.mouser.com/ProductDetail/78-TZX3V6A)
| FUSE    | 500mA Resettable fuse  | 1   | [Link](https://www.mouser.com/ProductDetail/652-MFR050)
| ISP     | 6 pin header           | 1   | [Link](https://www.mouser.com/ProductDetail/649-1012938190601BLF)
| OLED    | 4 pin header           | 1   | [Link](https://www.mouser.com/ProductDetail/517-929850-01-04-RA)
| USB     | GCT USB4085 USB C port | 1   | [Link](https://www.digikey.com/short/249pdt21), [Link](https://mou.sr/3Dgb4TO)
| POWER   | 3mm LED                | 1   | [Link](https://www.mouser.com/ProductDetail/859-LTL-4222)
| Capslock| 1.8mm LED (3mm rev 2)  | 1
| R1, R7  | 1.5k Resistor          | 2   | [Link](https://www.mouser.com/ProductDetail/603-MFR-12FTF52-1K5)
| R8      | 470 Resistor           | 1   | [Link](https://www.mouser.com/ProductDetail/603-CFR-12JT-52-470R)
| R2, R5  | 5.1k Resistor          | 2   | [Link](https://www.mouser.com/ProductDetail/603-MFR-12FTF52-5K1)
| R3, R4  | 75 Resistor            | 2   | [Link](https://www.mouser.com/ProductDetail/603-CFR-12JR-52-75R)
| R6      | 10k Resistor           | 1   | [Link](https://www.mouser.com/ProductDetail/YAGEO/MFR-12FTF52-10K?qs=oAGoVhmvjhzLlUYKKBtdYQ%3D%3D), [Link](https://mou.sr/3xgqcNf)
| U1      | ATmega32A              | 1   | [Link](https://www.digikey.com/short/2d8502n2), [Link](https://mou.sr/3RYkSGt)
|         | 40 pin IC socket       | 1   | [Link](https://www.mouser.com/ProductDetail/571-1-2199299-5)
| RESET, BOOT | 6mm push button    | 2   | [Link](https://www.mouser.com/ProductDetail/642-MJTP1230A)
| Y1      | 16MHz Crystal          | 1   | [Link](https://www.mouser.com/ProductDetail/520-ECS160-18-4X-CKM)
|         | 0.96in 64x128 OLED | 1   | [Link](https://www.aliexpress.us/item/3256801406424682.html?spm=a2g0o.cart.0.0.5d9838da4zVNT5&mp=1&gatewayAdapt=glo2usa&_randl_shipto=US)
|         | EC11 Rotary encoder    | 1   | [Link](https://www.digikey.com/short/90v3w37p), [Link](https://mou.sr/3QyXFcA)
|         | 48mm Knob              | 1   | [Link](https://www.aliexpress.com/item/4001316125393.html?spm=a2g0o.order_list.0.0.21ef1802wSwYcm)
|         | M2 24mm standoff       | 5   | Upper edge, [Link](https://www.aliexpress.com/item/32968906213.html?spm=a2g0o.order_list.0.0.21ef1802wSwYcm)
|         | M2 18mm standoff       | 1   | Middle left
|         | M2 15mm standoff       | 1   | Middle right
|         | M2 13mm standoff       | 5   | Lower edge
|         | M2 6mm screw           | 12  | Bottom, [Link](https://www.aliexpress.com/item/4001072025844.html?spm=a2g0o.order_list.0.0.21ef1802wSwYcm), [Link](https://www.aliexpress.com/item/1005002357962115.html?spm=a2g0o.order_list.0.0.21ef1802wSwYcm)
|         | M2 8mm screw           | 12  | Top
|         | Rubber Feet            | 4   | [Link](https://smile.amazon.com/gp/product/B088T7XMCY/ref=ppx_yo_dt_b_search_asin_title?ie=UTF8&th=1)
|         | Red Herring PCB        | 1
|         | Switch plate           | 1
|         | Plate foam (2mm)       | 1
|         | Case foam (1mm)        | 1
|         | Acrylic case layers    | 7

## Standoff Positions
||Left | | | |Right|
|:--|:--:|:--:|:--:|:--:|:--:|
|**Top**   |24mm|24mm|24mm|24mm|24mm|
|**Middle**|18mm|    |    |    |15mm|
|**Bottom**|13mm|13mm|13mm|13mm|13mm|


## Instructions
Some things to keep in mind is that there's very little clearance under the PCB, which is why the bottom foam is only 1mm.  Make sure you keep things low-profile by clipping pins flush with the solder joints, and/or folding then down flat against the PCB before soldering whenever possible.

One general tip is to bend the legs of the diodes/resistors/capacitors/LEDs outward after insterting them into the holes so that they stay in place when the PCB is flipped over.  This also reduces the height of the protruding legs, espeically if you also clip them flush with the solder joints.

### USB Port
I like doing the USB port first because I get lots of space to work with.  Heat resistant tape will be useful here to keep the usb port in place.
Solder one of the large legs first and check that the port is flat against the PCB and not crooked before soldering the other three legs. \
Solder the smaller pins by applying no-clean flux across the pins, then drag a small amount of solder across the pins until all the holes are filled.  If you accidentally bridge some pins, just clean all the solder off your solding iron tip, and try to "pick up" the extra solder with it.  If that doesn't work, you can use solder wick.

![usbc](https://user-images.githubusercontent.com/800930/144701028-55195723-9e37-4ee0-8cce-97262775312a.jpg)

### Zener Diodes (D93, D94)
**This part has specific orientation** - black line on the diode lines up with the square pad (right side).

![d93-d94](https://user-images.githubusercontent.com/800930/144701106-048eda11-7555-440f-929f-435d162cf98d.jpg)

### Resistors (R1-7)
Orientation does not matter. Solder based on the labeled values.
| Ref    | Value |
| ------ | ----- |
| R1, R7 | 1.5k  |
| R2, R5 | 5.1k  |
| R3, R4 | 75    |
| R6     | 10k   |

![r7-r1](https://user-images.githubusercontent.com/800930/144701127-c6f712bb-3042-41db-84a1-cedace2d651b.jpg)
![r5-r2](https://user-images.githubusercontent.com/800930/144701131-21c64dd1-7633-416c-bf8a-428160addf06.jpg)
![r3-r4](https://user-images.githubusercontent.com/800930/144701132-2d692214-4e4f-490f-b0d4-2cc8aeacc0c6.jpg)
![r6](https://user-images.githubusercontent.com/800930/144701138-a02562c5-93ca-4123-86c0-234244662661.jpg)

### Capslock LED (optional)
Check your switch before doing this.  You may need to solder the LED **after** you solder the switch, especially if the switch does not have a large opening on the bottom for the LED.  Short leg \
goes in the square pad.  Use the left holes for a stepped keycap.

![caps-led](https://user-images.githubusercontent.com/800930/144701449-40d33008-8b8e-45d1-aa4d-8b70a19723bb.jpg)

### Capslock 470 resistor (R8)
Orientation does not matter.

![r8](https://user-images.githubusercontent.com/800930/144701182-67c8341a-5e76-4710-a43c-32560f133122.jpg)

#### Rev 2 Capslock
The resistor and LED for rev 2 was moved up to the top of the PCB above the MCU, so look for the labels there.  The kit may come with a 470Ω resistor, but you can test the brightness before soldering.  I've found that with white colored LEDs, a higher resistance was needed to make it less bright (ie. 10kΩ)

![caps_lock_r2](https://user-images.githubusercontent.com/800930/156900795-03beda56-8229-49b9-a1f9-ccb663375e88.jpg)

### Capacitors (C1-4)
Orientation does not matter. Solder based on the labeled values.
| Ref    | Value |
| ------ | ----- |
| C1, C2 | 22pF  |
| C3, C4 | 0.1uF |

![c1](https://user-images.githubusercontent.com/800930/144701002-f5a47306-cd93-4175-97ea-28e250d62aed.jpg)
![c2](https://user-images.githubusercontent.com/800930/144701004-8d5d2d50-50b2-4205-bff3-0730f8d4b878.jpg)
![c3](https://user-images.githubusercontent.com/800930/144701008-4307959c-b4df-4e8c-a564-a3cc2c44e350.jpg)
![c4](https://user-images.githubusercontent.com/800930/144701014-9e5c1946-0949-499e-ae38-582e0e030e89.jpg)

### Capacitor (C5)
**This part has a specific orientation** - longer leg goes in square pad (white mark on the capacitor points up)

![c5](https://user-images.githubusercontent.com/800930/144701035-6b10fdfd-59bd-486b-b245-1fbae8491f38.jpg)

### Fuse
Orientation does not matter. Fold down after soldering.

![fuse](https://user-images.githubusercontent.com/800930/144701037-a6d2cf3c-e2dc-4c4a-9479-6570e64dee23.jpg)

### Crystal (Y1)
Orientation does not matter.

![y1](https://user-images.githubusercontent.com/800930/144701040-a7468eaf-cea2-4d13-ba39-6dadd62de752.jpg)

### Power LED
**This part has a specific orientation** - shorter leg and flat side of the LED line up with the square pad

![power](https://user-images.githubusercontent.com/800930/144701055-2c84b223-0c63-4b7f-9664-c3106bba74f7.jpg)

### Push Button (RESET, BOOT) and IC Socket
Push buttons have no specific orientation. \
Align the notch on the IC Socket with the markings on the PCB. Fold the pins inward against the PCB before soldering.

![reset-boot](https://user-images.githubusercontent.com/800930/144701061-e5c8209f-8070-471a-a7a6-63bdfa80daea.jpg)
![mcu-socket](https://user-images.githubusercontent.com/800930/144701085-cd923aeb-6c7e-4874-a35e-32b6a685cbe9.jpg)

### ISP Pin Header
Orientation does not matter, but the longer pins go on top so that you can solder the shorter bottom pins.

![isp1](https://user-images.githubusercontent.com/800930/144701062-1a878a6f-ad83-4e97-842a-774bb77d88d0.jpg)

### OLED Header
There's only about 10mm of space between the PCB and the top window.  I had to file my header down to about 7mm in height (basically right when the metal connectors started to show through, which you can see in the picture below).  I also removed the plastic spacer from the pins on the OLED so that it was just the 4 bare pins, which I had to clip down so that the OLED would sit flush against the shorter header.  (Tip: clip the pins at an angle so that they're easier to insert into the header).  After inserting it into the header, and making sure that there's no gaps, the total height from the top of the OLED pins (highest point) to the bottom of the header was just a tad over 9mm.

Once you're confident that you won't have any clearance issues, insert the OLED display into the header.  This is important because you want to align the display to look perfectly vertical and parallel to the PCB.  With the display firmly seated into the header, insert the header pins into the holes on the PCB.  Using as little solder as possible, tack down only **one** pin so that it holds the display in place.  Look straight down onto the display screen and make sure that it's vertical.  Now tilt the PCB onto its side and make sure the display is parallel to the PCB.  If it looks off in any way, heat the solder up again and make minor adjustments while the solder is still molten.  Then hold it in place until the solder solidifies.  Once the position of the display looks correct, solder the **other** pins that don't have solder yet, and then finally, the pin that had a minimal amount of solder.

![oled-header](https://user-images.githubusercontent.com/800930/144702052-e8cfc8cd-1268-4091-b99a-a7bb67b7605b.jpg)

### ATmega32A
Insert ATmega32A into the IC socket. Make sure the notch on the microcontroller aligns with the notch in the IC socket and the markings on the PCB.

### 1n1418 Diodes (D1-D92)
**This part has a specific orientation** - black line on the diode lines up with the square pad (points up)

![d1-d44](https://user-images.githubusercontent.com/800930/144701156-b7adb07b-b1fe-4656-922f-2ad8b8ffb0b7.jpg)
![d45-d92](https://user-images.githubusercontent.com/800930/144701163-18f6352d-16f1-49ce-b1bf-5cd31e75b652.jpg)

###  Encoder
Install the stabilizers, then place the plate on top. \
Fold the pins inward against the PCB before soldering.

![rotary-encoder](https://user-images.githubusercontent.com/800930/144701095-f28bb927-d644-4fd2-b83b-c39da5a0bfc4.jpg)

### PCB Mount Stabalizers (x5)
This is also a high resolution image of the completed PCB.

![full_board](https://user-images.githubusercontent.com/800930/144729033-c1ff4f3c-ff49-4ce4-8191-3a6c88df637b.jpg)

### Plate Foam & Switch plate

The 2mm plate foam goes between the PCB and switch plate.  Make sure those are in place before placing your switches in.  As you insert switch one at a time, make sure they snap into switch plate completely.  You man need to wedge a finger or tool in between the PCB and plate to push the plate upwards while pushing the switch downwards.

![IMG_3048 (1)](https://user-images.githubusercontent.com/800930/144715808-5441f024-4c31-4cf4-8151-d7efeb58badb.jpg)

## Case Assembly
Double check that the protective paper masking has been peeled off the front **and** back of eacy acrylic layer.  Try to find a dust-free area to work in, and have a microfiber cloth handy to wipe of dust that collects on the acrylic.  Best to keep the masking on until needed to minimize dust and scratches.

### Feet #1 - 6mm screws (x5) & 24mm standoffs (x5)

![IMG_3010](https://user-images.githubusercontent.com/800930/144702072-3dcd0fef-d6bb-42ae-84b5-3d1e8edf7058.jpg)

### Feet #2

![IMG_3011](https://user-images.githubusercontent.com/800930/144702075-837352fe-0678-4ef9-91e7-a16be9d48472.jpg)

### Feet #2 - 6mm screw & 18mm standoff

![IMG_3012](https://user-images.githubusercontent.com/800930/144702078-c1acdc79-5fe5-4557-a374-d3e1daf51d71.jpg)

### Feet #4 - 6mm screw & 15mm standoff

![IMG_3013](https://user-images.githubusercontent.com/800930/144702081-bcd66dcb-7b2f-49f9-b565-dbf64f8a94f1.jpg)

### Bottom - 6mm screws (x5) & 13mm standoffs (x5)

![IMG_3014](https://user-images.githubusercontent.com/800930/144702084-7680bce3-54d9-4b60-84f0-760ba9e5e735.jpg)

### Spacer #1

![IMG_3015](https://user-images.githubusercontent.com/800930/144702087-6e7cede8-f8d6-4e22-97cb-9dcbfdbea09b.jpg)

### 1mm Foam

![IMG_3016](https://user-images.githubusercontent.com/800930/144702090-180a1e91-910a-4c2f-9901-e82bb78b438c.jpg)

### Spacer #2

![IMG_3017](https://user-images.githubusercontent.com/800930/144702092-a48e1149-e481-4907-8348-4cbebf39155d.jpg)

### Assembled PCB with stabalizers, 2mm plate foam, switch plate, & switches
Make sure your OLED display has been inserted into the OLED header. 2mm plate foam goes inbetween the PCB and switch plate.

![IMG_2982](https://user-images.githubusercontent.com/800930/144715823-a4e80411-b0ec-420b-a25a-0015eba6a05f.jpg)

### PCB top layer
The acrylic areas that extend inward on this layer need to fit into the open areas in the switch plate.  The fitment is tight in order to keep the PCB from shifting, so make sure this layer is pushed all the way down with no gaps and that it's not caught onto an edged of the switch plate.  The PCB basically sits on top of the 1mm foam, and is held in position by the 2mm foam and this acrylic layer.

![IMG_3019](https://user-images.githubusercontent.com/800930/144702097-8040aab9-7b8b-45c5-9991-6125a6cbd798.jpg)

### Top layer #1

![IMG_3021](https://user-images.githubusercontent.com/800930/144702099-e8d70c54-8e8f-493c-9f87-66212344c26c.jpg)

### Top layer #2

![IMG_3022](https://user-images.githubusercontent.com/800930/144702101-c941351d-d69b-4a6d-94e6-7f3dbef8ffd2.jpg)

### Clear top: 8mm screws (x12)

![IMG_3023](https://user-images.githubusercontent.com/800930/144702103-6c3f5b47-84c4-4367-88dd-210a8e24e82b.jpg)

#### Rev 2 top with Windows
This revision uses a top layer that matches the rest of the case, but with cutouts for clear acrylic pieces over the top components and OLED screen.  The windows are held in place by the natural taper of the acrylic edges, so it's easiest to insert/remove the pieces from the bottom.  I've found that the easiest way is to place the clear windows down first, and then placing the top layer down while shifting the window pieces into position before finally pressing everything into place.

![RH_v3_windows](https://user-images.githubusercontent.com/800930/156900540-bbadc8cf-01bc-42d5-a429-14b40074b5e9.jpg)

### Rotary Knob
You may need to tighten the knob screws (one one each side) slightly before the knob hits the bottom.  Otherwise, you may not have engough clearance below the knob for the rotary knob "button" to be depressed (when you push straight down on the knob).

![IMG_3025](https://user-images.githubusercontent.com/800930/144702105-8c7c3258-5ced-4c9f-ab02-6bb14084bd6a.jpg)

### Rubber feet

Peel paper off the adhesive rubber feet and place one on each corner of the bottom of the keyboard.
