blueberryMSX
============
![blueberryMSX](http://i.imgur.com/Tnq9vSY.png "blueberry")

**blueberryMSX** is a port of [blueMSX][1] to Raspberry Pi.

Emulator runs from the command line, with [same arguments as the Windows/SDL versions][2] and supports joysticks/joypads. Because it draws directly to framebuffer, it does not need a windowing environment and can be run without X.

Shortcuts:

* Press **F12** to quit
* Press **F11** to disable frame skipping
* Press **F10**, **F9**, **F8** to set frame skipping to 1, 2, 3, respectively

Current Status
--------------

On the original Raspberry Pi, the emulator performs best at 900MHz (Medium overclock setting in `raspi-config`). On Raspberry Pi 2, it runs full speed on the factory setting.
By default, MoonSound, MSX Audio, and MSX Music are disabled.

Download
--------

[Version 0.6](https://github.com/pokebyte/blueberryMSX/releases/tag/v0.6) is the latest.

Build
--------
To build blueberryMSX, install libSDL:

`sudo apt-get install libsdl-dev`

and libudev:

`sudo apt-get install libudev-dev`
 
To compile with GPIO support:

1. Download and install the [wiringPi library] (http://wiringpi.com/download-and-install/)
2. Add the `RASPI_GPIO` macro to the list of flags: `CFLAGS += -DRASPI_GPIO` by uncommenting line 45

For now, GPIO is limited to dedicated LED's for MSX Power, and FDD0/FDD1 activity. See the schematic in [Doc/GPIO_schema.png] (/Doc/GPIO_schema.png).

Note that the executables compiled with `RASPI_GPIO` **require superuser privileges to run** (e.g. `sudo bluemsx-pi`).

Current Goals
------------

* Add a simple game selection screen

[1]: http://bluemsx.com/
[2]: http://www.msxblue.com/manual/commandlineargs_c.htm
