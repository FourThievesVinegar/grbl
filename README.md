
***
_Click the `Release` tab to download pre-compiled `.hex` files or just [click here](https://github.com/gnea/grbl/releases)_
***
This repository is a heavily modified [grbl](https://github.com/gnea/grbl) 1.1 adapted to be used as motor and GPIO controller for Four Thieves Winegar Collective Microlab.

Microlab uses stepper motors to control pumps and various pins on Arduino CNC Shield as GPIO to control relays. 

DO NOT USE THIS REPOSITORY TO CONTROL YOUR CNC MACHINE - YOUR MACHINE WILL MOST LIKELY GET DAMAGED!!

* [Licensing](https://github.com/gnea/grbl/wiki/Licensing): Grbl is free software, released under the GPLv3 license.

### Pin mapping

Arduino CNC Shield pins are remapped to change their original behaviour:

| CNC Shield pin  | Arduino Uno pin  | Microlab name  | 
|---|---|---|
| Endstop Z+  | _  | OUTPUT_1  |
| Endstop Y+  | _ |  OUTPUT_2  |
| Endstop X+  | _ |  OUTPUT_3  |
| SpnEn (Spindle Enable)  | _ |  OUTPUT_4  |
| SpnDir (Spindle Direction)  | _ |  OUTPUT_5  |






