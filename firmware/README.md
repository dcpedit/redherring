# Red Herring Firmware

If you're flashing a brand new MCU, you need to first assemble the PCB, and then flash the ATmega32A with the USBaspLoader bootloader.

[QMK's ISP flashing guide](https://github.com/qmk/qmk_firmware/blob/master/docs/isp_flashing_guide.md)

## Flash Bootloader for the ATMEGA32A

You will need an ISP programmer to flash the Atmega32a chip with the USBaspLoader bootloader, so please refer to the QMK guide on what to use.  I had a spare Elite-C lying around, so I converted that to an ISP programmer using `pro_micro_ISP_B6_10.hex`, which was taken from the QMK guide.  Here's a pic of my makeshift setup.  (I put a small amount of solder on the wire pins and tacked them down onto the pads so that I could easily remove them later)

<img src="https://user-images.githubusercontent.com/800930/159964447-baf44270-d5fb-4b8e-aaa3-c2c775221c04.jpg" width="300">

Wire your ISP programmer up to the PCB header using the diagram below.

![redherring-isp-pins](https://user-images.githubusercontent.com/800930/159964496-9e8c598b-5344-4687-b6e2-8b20bfc25552.jpg)

Install `avrdude`:
- [MacOS](https://formulae.brew.sh/formula/avrdude)
- [Windows](https://github.com/mariusgreuel/avrdude)

Use the `bootloader.hex` and flash with the following commands.  You will need to replace `<PORT>` with the location of your ISP's USB port.  You can look in your Device Manager (Windows ex: `COM3`), or your `/dev` directory for `/dev/tty.usb*` (MacOS ex: `/dev/tty.usbmodem12345`)

Flash bootloader
```
avrdude -c avrisp -P <PORT> -p atmega32 -U flash:w:bootloader.hex:i
```

Set fuses
```
avrdude -c avrisp -P <PORT> -p atmega32 -U lfuse:w:0x1f:m -U hfuse:w:0xc0:m
```

## Vial Firmware

You'll need the [Vial software](https://get.vial.today) if you want to remap your keys.

Source:

https://github.com/dcpedit/vial-qmk/blob/dcpedit/keyboards/dcpedit/redherring

Use the `redherring_vial.hex` firmware.
