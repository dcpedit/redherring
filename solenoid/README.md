# Solenoid Edition
This is an experimental version of the keyboard that supports a solenoid.  The files were created with KiCad 6.

## Additional components

| Ref     | Component              | Qty | Notes |
| ---     | ---------              | --- | ----- |
| Q1      | TIP120 Transistor      | 1   | [Link](https://www.amazon.com/gp/product/B08212F42Z/ref=ppx_yo_dt_b_search_asin_title?ie=UTF8&psc=1)
| R9      | 2.2k Resistor          | 1
| D95     | 1N4001 Diode           | 1
| SOL1    | 1x1 Pin Header         | 1   | [Link](https://www.digikey.com/short/fttzt8p9)
| J3      | 1x2 Pin Header         | 1   | Optional
| Solenoid| 4.5v Solenoid          | 1   | [Amazon link](https://www.amazon.com/dp/B013DR655A/ref=cm_sw_em_r_mt_dp_YHJRTZ5YY042HC7522VG?_encoding=UTF8&psc=1)
| Jumper   | 1x2 Pin Jumper        | 1   | [Link](https://www.digikey.com/short/zvbr03pr)
| M2x4mm   | Solenoid Screws       | 2
| Solenoid Spacer | Paper spacer | 1     | Optional

## Transistor, resistor, jumper (Q1, R9, SOL1)
Solder all the components but keep the jumper off until the bootloader has been flashed.  The solenoid components need to be kept disconnected until then because the MOSI pin is needed by the ISP programmer.  After you've programmed the bootloader, the MOSI pin will be repurposed by the firmware to control the solenoid.

The transistor heat sink needs to be on the left side. After soldering, fold it down towards the left side so that heat sink is against the PCB.

![transistor2](https://user-images.githubusercontent.com/800930/158442884-894592e6-f7e2-4889-8ce6-646156fae44f.jpg)

## 1N4001 Diode (D95)
Line on the diode needs to face the square pad (and match the line on the PCB)

![solenoid2](https://user-images.githubusercontent.com/800930/158442910-d3acf829-452f-4a17-b1ee-184f306e5d6a.jpg)

## Solenoid (J3)
You can solder the solenoid wires directly into J3, or you can optionaly use a female header and solder pins to wires.  I used Mill-Max low-profile headers and round pins since there's not that much clearance between the PCB and the case window.

You can optionally cut a paper spacer (~0.5mm) under the solenoid to add some dampening, as well as height so that the piston doesn't hit the boot button.  Without the spacer, you may also need shorter screws.

Side note:  I originally wanted to use the [SparkFun solenoid](https://www.digikey.com/short/ppr2c3z3), but it didn't work when I hooked it up.  I felt the solenoid trying to fire, but the pin wasn't able to move.  My guess is that there's not enough current supplied by the USB-C port to drive this solenoid.  But the more expensive Amazon one I found works fine.

## Photos
![rh_vintage-11](https://user-images.githubusercontent.com/800930/158265871-e8e6e615-ddaa-4600-be71-8b93424b6f1d.jpg)
![rh_vintage-6](https://user-images.githubusercontent.com/800930/158265941-7a7fcad3-11e5-4435-8e3d-8a9c6db260d9.jpg)
![rh_vintage-10](https://user-images.githubusercontent.com/800930/158443056-22bf56c3-5eb1-4f02-af20-23c6892d12ff.jpg)


## Video:
Here's a demo of the solenoid in action:

https://imgur.com/a/vGEALM3

## Manufacturing
I used JLCPCB.com to get this manufactured.  They have [a good tutorial](https://support.jlcpcb.com/article/149-how-to-generate-gerber-and-drill-files-in-kicad) on how to generate the Gerber files from KiCad. If the website is not able to calculate the dimensions, you can enter it in manually.  Here are the details

- Size: 364.4 mm x 167.2 mm
- Thickness: 1.6 mm FR4
- 2 Layers