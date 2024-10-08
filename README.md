
# Ender 3 Pro AWD-Y

Hi, this "AWD" mod adds second stepper motor onto your Y axis, doubling the torque available. As you probably noticed stock bed assembly is quite heavy which significantly limits accelerations. 

With double the torque you will be able to print much faster without compromising on quality!

This mod has been heavily inspired by [LH Stinger](https://github.com/lhndo/LH-Stinger/tree/main)

![Image of Y axis with two stepper motors](Images/cover.png)  

[![CC BY-NC-SA 4.0][cc-by-nc-sa-shield]][cc-by-nc-sa]

[cc-by-nc-sa]: http://creativecommons.org/licenses/by-nc-sa/4.0/
[cc-by-nc-sa-image]: https://licensebuttons.net/l/by-nc-sa/4.0/88x31.png
[cc-by-nc-sa-shield]: https://img.shields.io/badge/License-CC%20BY--NC--SA%204.0-lightgrey.svg

## Features
- More torque on Y axis -> better acceleration
- Easy tensioning
- Maximize Y axis travel, as mounts are very low profile (+-280mm)
- Support feet to reduce vibrations and prevent [this issue](https://youtu.be/1tBwaWnOHKY?si=pGgoMI5P9Bu9fiOg&t=324).
- Toothed idlers
- Compatible with [LH Stinger - Ender 3 - CF Carriage](https://discord.com/channels/1167067314781429831/1209625504425054271) as they are very low profile

### Changes over BETA
- 20T GT2 Idlers are now default. I found significant rubbing when using F623 bearings. Belt path has been adjusted.

## FAQ

> Are there build instructions ? 

I am working on them, but for now consult the CAD.

> Can I use single driver / stepper cable splitter ?

This doesn't really make sense, single driver usually does not provide enough to drive two steppers. Same applies to boards with two Z axis cable slots.

> Can I use v-wheels ?

Yes, v-wheels still work. 

> Can I use rigid motor mount to gain clearance for bigger stepper.

Yes, rigid motor mount is designed so that it can be used with stock ender tensioner at the front.

## Rigid Mount 

### BOM

| Part                            | Quantity | Comment                                                                                                                     |
| ------------------------------- | -------: | --------------------------------------------------------------------------------------------------------------------------- |
| 20T GT2 Idler (**3mm bore**)    |        1 | toothed, make sure bore is 3mm                                                                                              |
| 20T GT2 Pulley (**5mm bore**)   |        1 |                                                                                                                             |
| 625 Bearing                     |        1 | required for double shear, highly recommended (don't confuse with f625)                                                     |
| M3x30 SHSC                      |        4 |                                                                                                                             |
| M3x7x0.5 Washer/Shim            |        6 | 3mm ID x 7 OD x 0.5 Thickness                                                                                               |
| M5x10 BHSC                      |    4 + 2 | 4 button head screws are required to fit into mounting slots, 2 for support foot                                            |
| M5 T-Nut                        |        2 | for support foot                                                                                                            |
| M5x7x0.5 Washer/Shim            |        1 | outer diameter about 7 mm, can be printed as well, needed to prevent pulley rubbing on bearing outside housing which is stationary |
| GT2 2GT Belt                    |          | any of those mods will require longer than stock belt                                                                       |

## Tensioned Mount

has integrated tensioning mechanism to easily achieve ideal belt tension.

### BOM
| Part                            | Quantity | Comment                                                                                                                            |
| ------------------------------- | -------: | ---------------------------------------------------------------------------------------------------------------------------------- |
| 20T GT2 Idler (**3mm bore**)    |        1 | toothed, make sure bore is 3mm                                                                                                     |
| 20T GT2 Pulley (**5mm bore**)   |        1 |                                                                                                                                    |
| 625 Bearing                     |        1 | required for double shear, highly recommended (don't confuse with f625)                                                            |
| M3x30 SHSC                      |        4 |                                                                                                                                    |
| M3x35 SHSC                      |        3 |                                                                                                                                    |
| M3x10 SHSC                      |        2 | required for support foot                                                                                                          |
| M3x5L4 heatserts                |    3 + 2 | "voron spec" heatserts, 3 for frame rigidity, 2 required for support foot                                                          |
| M3x7x0.5 Washer/Shim            |        9 | 3mm ID x 7 OD x 0.5 Thickness                                                                                                      |
| M5x7x0.5 Washer/Shim            |        1 | outer diameter about 7 mm, can be printed as well, needed to prevent pulley rubbing on bearing outside housing which is stationary |
| M5x10 BHSC                      |        4 |                                                                                                                                    |
| M5 (Self Locking Nut)           |        2 | for tensioning mechanism and knob                                                                                                  |
| M5x30 BHSC/SHSC                 |        1 |                                                                                                                                    |
| GT2 2GT Belt                    |          | any of those mods will require longer than stock belt                                                                              |


## Accessories / Mods

- Bed carriage belt clamps: 
  - https://www.printables.com/model/202019-gt2-belt-fastener (prefer this one as it's stronger)
  - https://www.printables.com/model/250178-gt2-belt-clip-for-kingroon-kp3s (if belt is too short, make sure to clamp with ziptie firmly)

## Important Notes

1. Don't tighten pulley grub screws on rigid mount, until you are sure both steppers turn in right direction. It's safer to configure second driver with one pulley slipping.
2. Do AWD Sync. [macro](https://github.com/lhndo/LH-Stinger/blob/main/Config/Klipper_Config/mymacros.cfg#L773)
3. If motor/belt skips, you need to redo the AWD Sync.
4. After a few days **redo** the tension and AWD Sync, especially if using new belt since it will stretch a bit during first week, resulting in de-synced motors

## Troubleshooting and Build Notes

- Fully tightening the M5x30mm tensioner screw can cause it to scrape the belt, do not overtighten it and check it before running the printer. Use the knob to tension, not the screw itself.
- 5x7x0.5mm shims __or__ 625 *Deep Groove* bearings are required. If using deep groove bearings, larger shims such as 5x10x0.5mm are fine. The goal is for the shim to not rub on the static wall of the bearing.
- Ensure there is a small gap (roughly 1.3mm) between the pulleys and the base of the motors. For the rigid mount, tighten the grub screws and install the motor, and then re-loosen the grub screws for syncing and testing. This ensures the pulley does not get forced up against the motor.
- If you experience periodic resistance when moving the bed, make sure the pulleys are not rubbing on any printed parts.
- Belt tension should be roughly 150hz. [Calculator from LH Stinger](https://docs.google.com/spreadsheets/d/1mgBJEO6Ef19EgX-LgE-lGDI9BayG98oX33mT0myVEUg/edit?gid=1590186229#gid=1590186229)
- Some belt end clips are too loose for the tension/torque of this setup, make sure your belt does not slip through the clip and lose tension.
- If using the printed support feet, make sure they sit evenly. If one is not bearing any weight, shim the bottom with something like electrical tape or reprint it.
- For sensorless homing, use _one_ motor to set up the values. At least in Klipper, stepper_y1 will follow stepper_y by default.

## Credits

- inspiration [LH Stinger](https://github.com/lhndo/LH-Stinger/tree/main) 
- tensioning knob from [KevinAkaSam BeltedZ Mod](https://github.com/kevinakasam/BeltDrivenEnder3)
