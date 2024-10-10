
***
_Click the `Release` tab to download pre-compiled `.hex` files or just [click here](https://github.com/FourThievesVinegar/grbl/releases/)_
***
This repository is a heavily modified [grbl](https://github.com/gnea/grbl) 1.1 adapted to be used as motor and GPIO controller for Four Thieves Winegar Collective Microlab.

Microlab uses stepper motors to control pumps and various pins on Arduino CNC Shield as GPIO to control relays. 

DO NOT USE THIS REPOSITORY TO CONTROL YOUR CNC MACHINE - YOUR MACHINE WILL MOST LIKELY GET DAMAGED!!

* [Licensing](https://github.com/gnea/grbl/wiki/Licensing): Grbl is free software, released under the GPLv3 license.

### Pin mapping

Arduino CNC Shield pins are remapped to change their original behaviour:

| CNC Shield pin  | Arduino Uno pin  | Microlab name  | 
|---|---|---|
| Endstop Z+/Z-  | 11  | OUTPUT_1  |
| Endstop Y+/Y-  | 10 |  OUTPUT_2  |
| Endstop X+/X-  | 9 |  OUTPUT_3  |
| SpnEn (Spindle Enable)  | 12 |  OUTPUT_4  |
| SpnDir (Spindle Direction)  | 13 |  OUTPUT_5  |

OUTPUT_4 AND OUTPUT_5 are not yet supported!!


### Compiling

#### Arduino IDE

Open `grbl/examples/GrblUpload.ino` in Arduino IDE and compile + upload it from the editor.

For this to work you need to copy grbl directory into Arduino IDE libraries dir.

#### Linux command line / WSL2

Install compiler:

`sudo apt-get install gcc-avr binutils-avr avr-libc gdb-avr avrdude`

Compile:

`make`

### Uploading firmware

Use [avrdude](https://github.com/avrdudes/avrdude) for uploading hex file to the board. Avrdude supports native Arduino USB bootloader to program the board. Both Linux and Windows versions work fine.

On Debian/Ubuntu/etc install using:
`sudo apt-get install avrdude`

Command line example:

`avrdude -c arduino -P COM8 -b 115200 -p atmega328p -D -U flash:w:grbl.hex:i`


### GPIO control

Microlab-grbl implements M64-M65 g-code commands (turn on/off digital output immediately) to preserve compatibility with other CNC boards/firmware that may be used in the future with microlab.

`M64 P1` - switch OUTPUT_1 high

`M65 P1` - switch OUTPUT_1 low

