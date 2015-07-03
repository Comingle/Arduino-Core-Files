# Arduino-Core-Files
This repository contains changes to some core Arduino files that we have found helpful for doing Mod development.

* Our `boards.txt` creates a LilyPadUSB board that doesn't include code for USB HID. If your sketch needs a little extra room and isn't acting like a USB keyboard or mouse, this will save you 2 KB or so. This needs the arduino-noHID core.
* arduino-noHID is a core that's identical to the arduino core, but has one small change to the `USBDesc.h` file. Copy `hardware/arduino/cores/arduino` to `hardware/arduino/cores/arduino-noHID` and then drop in the new `USBDesc.h` file in to that folder.
* The `twi.c` and `twi.h` files prevent the Wire/I2C library from hanging up everything else when something fails. This commit is <a href="https://github.com/arduino/Arduino/pull/1842">waiting to be merged</a> in to the main Arduino branch, but isn't there yet.
