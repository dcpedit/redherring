# Red Herring Firmware

If you're flashing a brand new MCU, you need to first assemble the PCB, and then flash the ATmega32A with the USBaspLoader bootloader.

[QMK's ISP flashing guide](https://github.com/qmk/qmk_firmware/blob/master/docs/isp_flashing_guide.md)

## Flash Bootloader for the ATMEGA32A

You will need an ISP programmer to flash the Atmega32a chip with the USBaspLoader bootloader, so please refer to the QMK guide on what to use.  I had a spare Elite-C lying around, so I converted that to an ISP programmer using `pro_micro_ISP_B6_10.hex`, which was taken from the QMK guide.  Here's a pic of my makeshift setup.  (I put a small amount of solder on the wire pins and tacked them down onto the pads so that I could easily remove them later)

<img src="https://user-images.githubusercontent.com/800930/159964447-baf44270-d5fb-4b8e-aaa3-c2c775221c04.jpg" width="300">

Wire your ISP programmer up to the PCB header using the diagram below. Then connect your computer to the ISP programmer. The PCB should NOT be connected directly to your computer.

![redherring-isp-pins](https://user-images.githubusercontent.com/800930/159964496-9e8c598b-5344-4687-b6e2-8b20bfc25552.jpg)

Install `avrdude` or QMK MSYS for Windows:
- [MacOS avrdude](https://formulae.brew.sh/formula/avrdude)
- [Windows QMK MSYS](https://msys.qmk.fm/)

Use the `bootloader.hex` and flash with the following commands.  You will need to replace `<PORT>` with the location of your ISP's USB port.  You can look in your Device Manager (Windows ex: Ports -> `COM3`), or your `/dev` directory for `tty.usb*` (MacOS ex: `/dev/tty.usbmodem12345`).  You may need to change `avrisp` to the programmer that you're using.  Again, please check the [QMK docs](https://github.com/qmk/qmk_firmware/blob/master/docs/isp_flashing_guide.md) for more info.

### View attached device
```
avrdude -c avrisp -P <PORT> -b 19200 -p atmega32 -v
```

Example output:

<img width="300" alt="avrdude-verbose" src="https://user-images.githubusercontent.com/800930/162041817-e4a9338a-5266-49d1-8a73-11211430af65.png">

### Flash bootloader
```
avrdude -c avrisp -P <PORT> -b 19200 -p atmega32 -U flash:w:bootloader.hex:i
```

Example output:

<img width="300" alt="avrdude-flash" src="https://user-images.githubusercontent.com/800930/162043576-13a48c8b-9cdb-4fc3-b4e3-8cbba6186edc.png">

### Set fuses
```
avrdude -c avrisp -P <PORT> -p atmega32 -U lfuse:w:0x1f:m -U hfuse:w:0xc0:m
```

Example output:

<img width="300" alt="avrdude-fuse" src="https://user-images.githubusercontent.com/800930/162041912-8252818f-7424-48f0-bc7f-8fe16f5c51c1.png">

You can now disconnect your ISP programmer and connect the PCB directly to your computer via the USB-C port.  Make sure you have [QMK Toolbox](https://github.com/qmk/qmk_toolbox/releases) open so that you can monitor the status window and flash the firmware.  In order to put the board into bootloader mode you must first hold the boot button (labeled BOOT) and while holding the boot button, press the reset button (labeled RESET) and release it. Wait for another second, then release the boot button as well. The microcontroller will now be in bootloader mode if the bootloader is present and prepared correctly.

The QMK Toolbox status window should output: `USBAsp device connected`.

Continue to flash as you normally would from this point (ie. QMK Toolbox using `redherring_vial.hex`). If you have autoflash enabled on QMK Toolbox, it will do it automatically now. Reset the board once more in order to use the new firmware (you can do this by unplugging and replugging it or by pressing and releasing the reset button.)

## Vial Firmware

You'll need the [Vial software](https://get.vial.today) if you want to remap your keys.

Source:

https://github.com/dcpedit/vial-qmk/blob/dcpedit/keyboards/dcpedit/redherring

Use the `redherring_vial.hex` firmware.  Below is a list of commands to build.

```
git clone --recurse-submodules -b dcpedit https://github.com/dcpedit/vial-qmk.git
cd vial-qmk
make git-submodule
make dcpedit/redherring:vial
```
