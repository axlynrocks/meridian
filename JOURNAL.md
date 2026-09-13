---
title: "meridian"
author: "axie"
description: "a modular AUV"
created_at: "2026-09-13"
---

# september 13: one small commit for me, one giant leap for PROJECTKIND!!!

oookie so i made the repo, added the base stuff: a README, the JOURNAL you're lookin at rn, kicad project files, and the BOM

note: pitching in slack as t1, i hope i get accepted!!! (my plan B's to make this a t2 and upgrade after)

this project is going to have mutiple versions adding features successively, more on this later,

version 1 is only going to include the base AUV, SLAM, and water sampling

the base AUV's going to include 4 main PCBs

1. the main board with the SBC and breakouts to other peripherals and boards,
2. a motor controller board for movement and attachments (eg. robotic arms, water sampling),
3. a sensor controller board to process raw sensor input before feeding it into the SBC, and
4. a battery management board to control charging and power distribution

its hull will be made out of an acrylic tube (or tubes), O-rings, hemispheres on the front and back, and include some rails along its side for the modular attachments

the SLAM (aka. simultaneous localization & mapping), will use an array of sonar transceivers and a BLDC motor sweeping across a certain area underneath the AUV to map its surroundings
sonar array

the water sampling will use a peristaltic pump to extract water from its surroundings into a chamber for later analysis

(very) rough BOM: (for v1)
note: the stuff listed here includes the base AUV, water sampling, and recharging
hull and other enclosure bits: about 300

- SBC (lattepanda mu): 190
- mounting rods: 10\*4
- breakout PCBs: 50 (not including components
- gyro: 10
- depth sensor: 80
- propeller w motor: 30
- assorted CNC / 3D printed stuff (eg propellers, attachment parts, internal frames): about 100
- battery packs: 40
- camera: 50
- water sampling stuff - stepper motor: 15, tubes and chamber: 50
- recharging stuff - solar panels: 50
  wires and watertight connectors: 30

**total time spent: 2.2 hours**

# september 13: researching AUV components: enclosure edition

continuing to research the parts and features i'll have here to get a more accurate BOM with all the components i'll need for v1!

i'm planning to waterproof the hull (just the hull, not the arm or anything else, i wanna do that _myself_) with the following [watertight enclosure components from BlueRobotics](https://bluerobotics.com/store/watertight-enclosures/wte-vp/) ([datasheet](https://bluerobotics.com/wp-content/uploads/2026/05/WTE-DATASHEET-RevC.5-MAY2026.pdf)) also all the following BlueRobotics parts are for a 100mm dia. AUV

| part          | quantity | description              | cost / unit (USD) |
| ------------- | -------- | ------------------------ | ----------------- |
| BR-101052-200 | 1        | acrylic tube 200mm len.  | 170               |
| BR-100495     | 1        | clear polycarbonate dome | 42                |
| BR-100665     | 2        | o-ring flange            | 50                |
| BR-102993-002 | 1        | aluminum end cap 10x M10 | 42                |
| BR-100804     | 1        | pressure relief valve    | 32                |
| BR-100574     | 1        | o-ring pick              | 0                 |

total cost: 386

as well as their [RAILS set](https://bluerobotics.com/store/watertight-enclosures/locking-series/watertight-enclosure-rails/) ([datasheet](https://bluerobotics.com/wp-content/uploads/2025/01/WTE-RAILS-DATASHEET-RevA-FEB2025.pdf))

| part          | quantity | description       | cost / unit (USD) |
| ------------- | -------- | ----------------- | ----------------- |
| BR-103290-200 | 2        | narrow rails 200N | 29                |
| BR-103291-400 | 1        | rect. tray        | 24                |
| BR-103292-400 | 3        | circ. tray        | 27                |

~~| BR-103293 | 10 | 3 | mounting screws |~~
~~note: amount of screws is 4x / rect. tray, 2x / circ. tray~~

note: i realized the screws to connect the RAILS parts are included, and the mounting screws mentioned are generic phillips screws

total cost: 163

however...

i'm kinda broke so i might proceed to use the CAD models provided to make custom versions and 3D print them... i should ask BlueRobotics first (personally i don't exactly want to get in legal trouble for violating some kinda copyright law)

sooooo....

i went ahead and asked them if their files were open-source and available to 3D print, and i may or may not also have asked if i could get some parts free (i'm hoping they say yes to both or at least one of them!!!)

note: the 3D models are available under `technical details > 3D models` in their respective product pages

anywho, continuing to look at JLC3DP and JLCCNC quotes for the watertight enclosure parts, the cheapest functional quotes i could get are the following:

| 3D file:        | WTE4-P-DOME-RETAINING-RING-R1.STEP |
| --------------- | ---------------------------------- |
| Dimensions:     | 11.45×11.45×0.65cm                 |
| Volume:         | 13.1 cm3                           |
| Surface Area:   | 103.95 cm2                         |
| 3D Technology:  | SLA(Resin)                         |
| Material:       | 9600 Resin                         |
| Colors:         | White                              |
| Surface Finish: | 01 Sanding, General Sanding        |
| Thread:         | No thread                          |
| Build Time:     | 3 days                             |
| Gross Weight:   | 0.02 kg                            |
| Package Box:    | With JLC3DP Logo                   |
| Qty:            | 1                                  |
| Product Decs:   | Plastic Enclosure -HS Code 392690  |

BR-100495 retaining ring for $1.19

| 3D file:        | BR-101052-200_RevB.STEP           |
| --------------- | --------------------------------- |
| Dimensions:     | 20×11.43×11.43 cm                 |
| Volume:         | 406.6 cm3                         |
| Surface Area:   | 1392.47 cm2                       |
| 3D Technology:  | SLA(Resin)                        |
| Material:       | 9600 Resin                        |
| Colors:         | White                             |
| Surface Finish: | 01 Sanding,General Sanding        |
| Thread:         | No thread                         |
| Build Time:     | 3 days                            |
| Gross Weight:   | 0.74 kg                           |
| Package Box:    | With JLC3DP Logo                  |
| Qty:            | 1                                 |
| Product Decs:   | Plastic Enclosure -HS Code 392690 |

BR-101052-200 for $39.68

| 3D file:        | WTE4-M-END-CAP-10XM10-R2.step     |
| --------------- | --------------------------------- |
| Dimensions:     | 11.43×11.43×1cm                   |
| Volume:         | 78.6 cm3                          |
| Surface Area:   | 257.25 cm2                        |
| 3D Technology:  | SLA(Resin)                        |
| Material:       | 9600 Resin                        |
| Colors:         | White                             |
| Surface Finish: | 01 Sanding, General Sanding       |
| Thread:         | No thread                         |
| Build Time:     | 3 days                            |
| Gross Weight:   | 0.14 kg                           |
| Package Box:    | With JLC3DP Logo                  |
| Qty:            | 1                                 |
| Product Decs:   | Plastic Enclosure -HS Code 392690 |

BR-102993-002 for $7.15

| 3D file:        | BR-101040_RevC.step               |
| --------------- | --------------------------------- |
| Dimensions:     | 11.43x11.43×2.7cm                 |
| Volume:         | 38.71 cm3                         |
| Surface Area:   | 294.7 cm2                         |
| 3D Technology:  | SLA(Resin)                        |
| Material:       | 9600 Resin                        |
| Colors:         | White                             |
| Surface Finish: | 01 Sanding, General Sanding       |
| Thread:         | No thread                         |
| Build Time:     | 3 days                            |
| Gross Weight:   | 0.14 kg                           |
| Package Box:    | With JLC3DP Logo                  |
| Qty:            | 2                                 |
| Product Decs:   | Plastic Enclosure -HS Code 392690 |

BR-100665 without o-rings or locking cord system for $3.52 ($3.52 \* 2 = $7.04)

| 3D file:                 | WTE4-P-DOME-R4.step              |
| ------------------------ | -------------------------------- |
| Dimensions:              | 104.66 x 104.66×49.3mm           |
| Volume:                  | 54875.32 mm3                     |
| Qty:                     | 1                                |
| Material:                | Polycarbonate                    |
| Surface Finish:          | Blue-Tinted Vapor Polishing      |
| Tightest Tolerance:      | ISO 2768 medium                  |
| Appearance Requirements: | Standard                         |
| Threads:                 | No                               |
| Sub-assembly:            | No                               |
| Product Desc:            | plastic End Cap - HS Code 392350 |
| Build Time:              | 6 days                           |
| Gross Weight:            | 0.14kg                           |
| CNC Remark:              | -                                |

BR-100495 clear polycarbonate dome for 89.30

JLC estimates the price of the aforementioned parts at a merchandise total of $144.36 and an estimated shipping fee of $9.78 with UPS Worldwide Express Saver bringing the watertight enclosure's subtotal to $154.14

as for the RAILS parts (excluding screws):

| 3D file:        | BR-102784-200_RevA.step            |
| --------------- | ---------------------------------- |
| Dimensions:     | 14.9×1.5×0.62cm                    |
| Volume:         | 4.99 cm3                           |
| Surface Area:   | 57.59 cm2                          |
| 3D Technology:  | SLA(Resin)                         |
| Material:       | 9600 Resin                         |
| Colors:         | White                              |
| Surface Finish: | 01 Sanding, General Sanding        |
| Thread:         | No thread                          |
| Build Time:     | 3 days                             |
| Gross Weight:   | 0.02 kg                            |
| Package Box:    | With JLC3DP Logo                   |
| Qty:            | 2                                  |
| Product Decs:   | Plastic Connectors -HS Code 392690 |

BR-103290-200 for $0.45 ($0.45 \* 2 = $0.90)

| 3D file:        | BR-103130-400_RevB.step            |
| --------------- | ---------------------------------- |
| Dimensions:     | 8.7×6.8×0.6cm                      |
| Volume:         | 28.55 cm3                          |
| Surface Area:   | 134.47 cm2                         |
| 3D Technology:  | SLA(Resin)                         |
| Material:       | 9600 Resin                         |
| Colors:         | White                              |
| Surface Finish: | 01 Sanding, General Sanding        |
| Thread:         | No thread                          |
| Build Time:     | 3 days                             |
| Gross Weight:   | 0.05 kg                            |
| Package Box:    | With JLC3DP Logo                   |
| Qty:            | 1                                  |
| Product Decs:   | Plastic Base Plate -HS Code 392690 |

BR-103291-400 for $2.6

| 3D file:        | BR-103131-400_RevB.step            |
| --------------- | ---------------------------------- |
| Dimensions:     | 9.85×9.3×0.6cm                     |
| Volume:         | 35.43 cm3                          |
| Surface Area:   | 181.27 cm2                         |
| 3D Technology:  | SLA(Resin)                         |
| Material:       | 9600 Resin                         |
| Colors:         | White                              |
| Surface Finish: | 01 Sanding, General Sanding        |
| Thread:         | No thread                          |
| Build Time:     | 3 days                             |
| Gross Weight:   | 0.19 kg                            |
| Package Box:    | With JLC3DP Logo                   |
| Qty:            | 3                                  |
| Product Decs:   | Plastic Base Plate -HS Code 392690 |

BR-103292-400 for $3.22 (@3.22 \* 3 = $9.66)

JLC estimates the price of the aforementioned parts at a merchandise total of $13.16 and an estimated shipping fee of $6.74 with E-POST bringing the RAILS system subtotal to $19.90

note: on all of the JLCCNC parts listed here, you'll see ISO 2768 medium listed for the tolerances. that means that they follow [this standard](https://jlccnc.com/help/article/iso-2768-tolerance-standards-for-cnc-machining) and for most of the parts, they fall below the over 400 up to 1000 range for nominal lengths which are tighter than most of the equivalent parts cast acrylic variants straight from BlueRobotics at about +-2mm, but their aluminum variants have a roughly equivalent tolerance. however, the only part listed above getting CNCed is the polycarbonate dome, whose original tolerance is +-0.1mm which is tighter than the ISO 2768 medium tolerance so i just wasted a minute of your time lmao

another, more serious note: i asked around on the HC slack about if this would be alright to use, and what i got was more or less the following: i can use them, but it reduces complexity, and a t1 project needs to be pretty complex. so what i'm going to do is go ahead with it (because at the moment i'm just researching and then making the PCBs) while waiting for BlueRobotics' response

added the above BlueRobotics components to the BOM for now

![BlueRobotics circular plate dimensions](journal_images/bluerobotics_circular_plate_dimensions.png)

for the circular plates, each one can hold a maximum ~6x6cm PCB, based on its mounting holes on each side, flat against the plate if single sided, but will require standoffs or spacers if double sided

also, i looked around for connectors and i might consider using Samtec AccliMate connectors with an IP68 rating, but more on that later

note: just realized .csv files were included in the gitignore, removed that

**total time spent: 2.05 hours**
